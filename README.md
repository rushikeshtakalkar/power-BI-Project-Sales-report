
# 📊 Sales Analysis Report – Power BI

## 📌 Overview

This **Sales Analysis Report** is an interactive dashboard built using **Microsoft Power BI** to analyze sales performance across different dimensions such as **time, region, segment, category, and geography**.
The report helps stakeholders quickly understand **business performance, trends, and key insights** for better decision-making.

---

## 🎯 Objectives of the Report

* Track **overall sales, profit, quantity, and discounts**
* Identify **top-performing segments and regions**
* Analyze **sales trends over time**
* Understand **product-wise and category-wise performance**
* Visualize **geographical distribution of sales**

---

## 📈 Key Performance Indicators (KPIs)

| Metric                  | Value                | Description                  |
| ----------------------- | -------------------- | ---------------------------- |
| **Total Sales**         | **2.30M**            | Total revenue generated      |
| **Total Quantity Sold** | **38K**              | Total items sold             |
| **Total Profit**        | **286.4K (approx.)** | Net profit earned            |
| **Total Discount**      | **1.56K**            | Discounts given to customers |

➡️ These KPIs provide a **quick snapshot of business health**.

---

## 📊 Visualizations Explained

### 1️⃣ Sales by Segment (Pie Chart)

**Segments:**

* Consumer
* Corporate
* Home Office

**Insight:**

* The **Consumer segment contributes the highest share (~50.56%)** of total sales.
* Corporate and Home Office segments follow.

📌 *This shows where the main customer base lies.*

---

### 2️⃣ Sales Trend by Order Date (Line / Area Chart)

* Displays **sum of sales over time (2019–2021)**
* Shows **growth trends, spikes, and seasonal fluctuations**

**Insights:**

* Sales show an **overall increasing trend**
* Some sharp spikes indicate **high-volume orders or peak seasons**

📌 *Useful for forecasting and identifying seasonal demand.*

---

### 3️⃣ Sales by Sub-Category (Bar Chart)

Top sub-categories include:

* Phones
* Chairs
* Storage
* Tables

**Insights:**

* **Phones** generate the highest sales
* **Fasteners and Labels** contribute the least

📌 *Helps identify best-selling and underperforming products.*

---

### 4️⃣ Sales by Region (Donut Chart)

**Regions:**

* West – 31.58%
* East – 29.55%
* Central – 21.82%
* South – 17.05%

**Insights:**

* **West region is the top-performing region**
* South region has the lowest contribution

📌 *Helps in region-wise strategy and expansion planning.*

---

### 5️⃣ Sales by State (Map Visualization)

* Shows **sales distribution across U.S. states**
* Each bubble represents sales volume in a state

**Insights:**

* High concentration of sales in **economically active states**
* Highlights regional demand patterns

📌 *Very useful for logistics, supply chain, and regional marketing.*

---

## 🧠 Business Insights Summary

* Consumer segment drives the majority of revenue
* Phones and Chairs are the most profitable sub-categories
* West and East regions dominate overall sales
* Sales have steadily increased over time, indicating business growth
* Low-performing products and regions can be targeted for improvement

## 📐 DAX Measures Explanation

DAX (Data Analysis Expressions) is used in this project to create **calculated measures** that dynamically respond to filters and slicers in Power BI.
All KPIs and aggregated values in the dashboard are powered by DAX measures.

---

### 1️⃣ Total Sales

```DAX
Total Sales = SUM(Orders[Sales])
```

**Explanation:**

* Calculates the **total revenue** by summing the `Sales` column from the Orders table.
* This measure updates dynamically based on filters such as **Region, Segment, Date, or Category**.

**Used In:**

* KPI Card (Total Sales)
* Sales by Segment
* Sales by Region
* Sales by Sub-Category
* Sales Trend over Time

---

### 2️⃣ Total Quantity

```DAX
Total Quantity = SUM(Orders[Quantity])
```

**Explanation:**

* Calculates the **total number of products sold**.
* Helps analyze sales volume irrespective of revenue.

**Used In:**

* KPI Card (Total Quantity)
* Trend and performance comparison visuals

---

### 3️⃣ Total Profit

```DAX
Total Profit = SUM(Orders[Profit])
```

**Explanation:**

* Computes **net profit** by summing the Profit column.
* Helps evaluate business profitability instead of only revenue.

**Used In:**

* KPI Card (Total Profit)
* Profit-based analysis (if added later)

---

### 4️⃣ Total Discount

```DAX
Total Discount = SUM(Orders[Discount])
```

**Explanation:**

* Calculates the **total discount given** across all orders.
* Useful to understand how discounts impact revenue and profit.

**Used In:**

* KPI Card (Total Discount)

---

### 5️⃣ Sales by Year (Optional – Time Intelligence)

```DAX
Sales by Year = 
CALCULATE(
    [Total Sales],
    YEAR(Orders[Order Date])
)
```

**Explanation:**

* Aggregates sales based on **year-wise order dates**.
* Helps in analyzing yearly growth patterns.

📌 *(In practice, Power BI handles this automatically when Order Date is placed on the axis.)*

---

### 6️⃣ Sales Percentage by Segment / Region

```DAX
Sales % = 
DIVIDE(
    [Total Sales],
    CALCULATE([Total Sales], ALL(Orders)),
    0
)
```

**Explanation:**

* Calculates the **percentage contribution** of each segment or region.
* `ALL()` removes filters to calculate grand total sales.
* `DIVIDE()` prevents divide-by-zero errors.

**Used In:**

* Pie Chart (Sales by Segment)
* Donut Chart (Sales by Region)

---

### 7️⃣ Running Total Sales (Optional Advanced Measure)

```DAX
Running Total Sales =
CALCULATE(
    [Total Sales],
    FILTER(
        ALLSELECTED(Orders[Order Date]),
        Orders[Order Date] <= MAX(Orders[Order Date])
    )
)


## ✅ Conclusion

This Sales Analysis Report provides a **comprehensive, visual, and interactive view of business performance**.
It enables quick identification of **strengths, weaknesses, trends, and opportunities**, making it valuable for both **business users and analysts**.
080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/f89c02d8-08c3-4744-b89d-65cb0c8198ed" />
