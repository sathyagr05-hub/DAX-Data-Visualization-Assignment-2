# Power BI Sales Analysis Dashboard

## 📊 Project Overview

This project focuses on analyzing sales performance using **Microsoft Power BI**. The objective is to transform raw sales data into meaningful insights through DAX calculations, calculated columns, measures, and interactive visualizations.

As an aspiring Data Analyst, I developed this project to strengthen my skills in data modeling, DAX, business intelligence, and data visualization while building my professional data analytics portfolio.

## 🎯 Project Objectives

- Analyze sales, profit, quantity, and order performance.
- Create calculated columns and measures using DAX.
- Compare actual sales with sales targets.
- Identify monthly sales trends and product performance.
- Analyze geographical sales distribution by city and state.
- Build an interactive dashboard to support data-driven decision-making.

## 🛠️ Tools and Technologies

- **Microsoft Power BI Desktop** – Dashboard development and data visualization.
- **DAX (Data Analysis Expressions)** – Calculated columns and measures.
- **Data Modeling** – Organizing data for effective analysis.
- **GitHub** – Project documentation and portfolio management.

## 🧮 DAX Calculations

### 1. Calculated Columns

**Category Type**

Combines the Category and Sub-Category columns into a single column.

```dax
Category Type =
'Order Details'[Category] & " - " &
'Order Details'[Sub-Category]
```

**Revenue per Order**

Calculates revenue using Amount multiplied by Quantity.

```dax
Revenue per Order =
'Order Details'[Amount] *
'Order Details'[Quantity]
```

**Sales Category**

Classifies each order as Above Average or Below Average based on its Amount compared with the average Amount across all orders.

```dax
Sales Category =
IF(
    'Order Details'[Amount] >=
        CALCULATE(
            AVERAGE('Order Details'[Amount]),
            ALL('Order Details')
        ),
    "Above Average",
    "Below Average"
)
```

*Note: This formula classifies amounts equal to the average as Above Average.*

### 2. Calculated Measures

**Order Count**

Calculates the total number of orders. This version counts rows in the Order Details table.

```dax
Order Count =
COUNTROWS('Order Details')
```

If the dataset contains multiple rows per order, use `DISTINCTCOUNT` on the order ID column instead.

**Average Profit in Delhi**

Calculates the average profit for orders placed in Delhi.

```dax
Average Profit in Delhi =
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'Order Details'[City] = "Delhi"
)
```

**Year-to-Date (YTD) Sales**

Calculates cumulative sales from the beginning of the year through the current date in the report context.

```dax
YTD Sales =
TOTALYTD(
    SUM('Order Details'[Amount]),
    'Order Details'[Order Date]
)
```

*Note: A dedicated Date table marked as a date table is recommended for reliable time-intelligence calculations. Replace column names if your dataset uses different names.*

## 📈 Data Visualizations

The project includes the following Power BI visualizations:

| Visualization | Purpose |
|---|---|
| Clustered Column Chart | Compare actual sales and sales targets by category. |
| Donut Chart | Analyze maximum profit margin by sub-category. |
| Line Chart | Track monthly sales trends over time. |
| Scatter Chart | Compare profit and quantity across sub-categories. |
| Cards | Display total sales amount and sales target. |
| Multi-Row Card | Display the minimum target for each segment. |
| Matrix | Compare actual sales against targets by category and month. |
| Map | Analyze total sales by city and identify regional patterns. |
| Treemap | Show sales distribution across sub-categories. |
| Funnel Chart | Analyze order counts across states. |

## 🔍 Key Business Questions

- Which product categories generate the highest sales?
- How do actual sales compare with sales targets?
- Which sub-categories contribute the most to sales and profit?
- What are the monthly sales trends?
- Which cities and states generate the highest sales?
- How does quantity sold relate to profit?
- Which segments have the lowest sales targets?
- How many orders are recorded across different states?

## 💡 Skills Demonstrated

- Data analysis and business intelligence
- DAX calculated columns and measures
- Sales and profitability analysis
- Time-intelligence calculations
- Data visualization and dashboard design
- Geographic and trend analysis
- Business performance monitoring
- Analytical thinking and problem-solving

## 📂 Project Files

- `Power BI Assignment 2.pbix` – Power BI report containing the DAX calculations and visualizations.
- `README.md` – Project documentation.

## 🚀 Learning Outcomes

Through this project, I gained practical experience in creating DAX calculations, building interactive visualizations, comparing sales against targets, and interpreting business performance data. This project represents one of my practical steps toward becoming a Data Analyst.

## 👤 About Me

I am an **aspiring Data Analyst** passionate about working with data, discovering meaningful insights, and supporting business decisions through analytics and visualization.

I am continuously developing my skills in Excel, SQL, Power BI, and data analysis while building hands-on projects for my professional portfolio.

---

**Thank you for visiting my project!**

