# Olist Performance Optimization | Power BI

An end-to-end **Business Intelligence & E-Commerce Analytics project** built with **Power BI** to analyze Olist's Brazilian marketplace performance across revenue, logistics, product categories, sellers, and customer behavior.

The project transforms raw Olist e-commerce data into an interactive **4-page executive dashboard** designed to support data-driven commercial and operational decisions.

---

## 📊 Project Overview

This project simulates a real-world **Executive Analytics Initiative** for Olist Marketplace.

The analysis focuses on four major business areas:

* 💰 **Commercial Performance** — revenue, orders, AOV, payment methods, and market performance
* 🚚 **Operations & Logistics** — delivery time, delays, seller performance, and shipping routes
* 📦 **Product & Category Performance** — product prices, freight costs, product weight, and category revenue
* 👥 **Customer Insights** — customer acquisition, loyalty, CLV, demographics, and review scores

### Key Dataset Statistics

| Metric                |      Value |
| --------------------- | ---------: |
| Orders                |     99,441 |
| Sellers               |      3,095 |
| Unique Customers      |     96,096 |
| Product Records       |     32,951 |
| Revenue               | 15.42M BRL |
| Average Review Score  |   4.09 / 5 |
| Average Delivery Time | 12.43 days |
| Freight Cost Ratio    |     14.21% |

---

## 🎯 Business Objectives

The dashboard was designed to answer key business questions such as:

* What are the main revenue and growth drivers?
* Which product categories generate the most revenue?
* Where are delivery delays concentrated?
* Which seller-to-customer routes experience the highest delays?
* How significant is freight cost relative to product value?
* Which regions and cities have the highest customer concentration?
* How satisfied are customers?
* What does customer purchasing frequency look like?

---

## 🗂️ Dataset

The project uses the publicly available **Brazilian E-Commerce Olist Dataset (2016–2018)**.

Eight CSV files were integrated into Power BI:

* `olist_orders_dataset.csv`
* `olist_order_items_dataset.csv`
* `olist_order_payments_dataset.csv`
* `olist_order_reviews_dataset.csv`
* `olist_customers_dataset.csv`
* `olist_sellers_dataset.csv`
* `olist_products_dataset.csv`
* `product_category_name_translation.csv`

The dataset was transformed and modeled to support both executive-level KPIs and detailed operational analysis.

---

## 🏗️ Data Model

The Power BI model follows a **Star Schema** with `fact_order_items` as the central fact table.

### Main Tables

**Fact Tables**

* `fact_order_items`
* `fact_payment`
* `fact_reviews`

**Dimension Tables**

* `dim_order`
* `dim_customer`
* `dim_sellers`
* `dim_product`
* `dim_geolocation`
* `Date Dim`

A dedicated **Date Dimension** was created using DAX to support time-intelligence analysis.

The model also uses an inactive delivery-date relationship activated through `USERELATIONSHIP()` for the On-Time Delivery calculation.

---

## 🧹 Data Transformation

Power Query was used to prepare the raw datasets for analysis.

Main transformations included:

* Merging order-level information into the main order-item fact table
* Translating Portuguese product categories into English
* Renaming columns for consistency
* Setting appropriate data types
* Removing null records from key columns
* Creating seller and customer analytical fields
* Preparing date/time fields for delivery and time-series analysis

---

## 🧮 DAX & Analytics

The project contains **28 DAX measures** and **7 calculated columns**.

### Key Measures

* Total Revenue
* Total Orders
* Average Order Value (AOV)
* Active Sellers
* On-Time Delivery %
* Delayed Orders
* Average Delivery Time
* Average Delay Duration
* Top Delay Route
* Freight Cost
* Freight Cost Ratio
* High Freight Order %
* Average Product Price
* Total Customers
* Average CLV
* Average Orders per Customer
* Average Review Score

### Advanced DAX Techniques

The project demonstrates:

* `CALCULATE()`
* `FILTER()`
* `DISTINCTCOUNT()`
* `AVERAGEX()`
* `VALUES()`
* `TOPN()`
* `SUMMARIZE()`
* `RELATED()`
* `USERELATIONSHIP()`
* `CALENDARAUTO()`
* Time-intelligence concepts
* What-if parameters for dynamic Top N analysis

---

## 📈 Dashboard Pages

### 1. Commercial Overview

Provides an executive-level view of marketplace performance.

**KPIs**

* Total Revenue
* AOV
* On-Time Delivery %
* Total Orders
* Average Review Score

**Visuals**

* Revenue trend
* Payment method distribution
* Top product categories
* Geographic order distribution
* Black Friday revenue peak

---

### 2. Operations Intelligence

Focuses on logistics and seller performance.

**KPIs**

* Active Sellers
* On-Time Delivery %
* Average Delivery Time
* Delayed Orders
* Top Delay Route

**Analysis**

* Delivery time trends
* Delay duration by state
* Geographic delay patterns
* Seller performance
* Seller-to-customer shipping routes

---

### 3. Category Analysis

Analyzes product and freight performance.

**KPIs**

* Freight Cost Ratio
* Average Freight Cost
* Average Product Price
* Total Orders
* High Freight Order %

**Analysis**

* Orders vs. freight cost by category
* Product weight by category
* Price vs. review score
* Revenue by category
* Top N category analysis

---

### 4. Customer Insights

Analyzes customer behavior and geographic distribution.

**KPIs**

* Total Customers
* Average CLV
* Average Orders per Customer
* Average Review Score

**Analysis**

* Customer acquisition over time
* Customer distribution by state
* Customer concentration by city
* Loyalty and purchasing frequency

---

## 💡 Key Findings

The dashboard identified several important business patterns:

### 🚚 Logistics

* Around **7K orders** were identified as delayed.
* Average delivery time is approximately **12.43 days**.
* Certain North and Northeast states show substantially higher average delivery delays.
* The analysis identifies specific seller-to-customer routes associated with higher delay durations.

### 📦 Freight

* Total freight cost is approximately **2.25M BRL**.
* Freight represents approximately **14.21%** of total transaction value.
* **35.62%** of orders have freight costs exceeding 30% of product price.

### 👥 Customers

* The dataset contains approximately **96K unique customers**.
* Average orders per customer are approximately **1.03**.
* Average review score is **4.09 / 5**.

### 💰 Commercial Performance

* Total payment-based revenue is approximately **15.42M BRL**.
* Average Order Value is approximately **160.99 BRL**.
* Health & Beauty is among the leading revenue-generating categories.
* A visible revenue spike occurs around **Black Friday 2017**.

---

## 🎯 Business Recommendations

Based on the dashboard findings, the analysis suggests several areas for business action:

* Improve logistics coverage in regions with consistently higher delivery delays.
* Review carrier performance and high-delay shipping routes.
* Investigate categories with disproportionately high freight costs.
* Recalibrate estimated delivery dates to improve delivery expectations.
* Develop customer retention and post-purchase engagement strategies.
* Strengthen seller recruitment in high-performing categories.
* Prepare inventory and logistics capacity ahead of major seasonal peaks.

---

## 🛠️ Tools & Technologies

| Tool            | Purpose                                              |
| --------------- | ---------------------------------------------------- |
| **Power BI**    | Data modeling, visualization & dashboard development |
| **Power Query** | Data cleaning & transformation                       |
| **DAX**         | Measures, calculated columns & business logic        |
| **Excel / CSV** | Raw data sources                                     |
| **Star Schema** | Data warehouse / BI modeling                         |

---

## 📁 Project Structure

```text
Olist-Performance-Optimization_PowerBi-project/
│
├── README.md
├── Documentation.md
├── Olist_Performance_Optimization.pbix
│
├── data/
│   ├── olist_orders_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   ├── olist_customers_dataset.csv
│   ├── olist_sellers_dataset.csv
│   ├── olist_products_dataset.csv
│   └── product_category_name_translation.csv
│
└── screenshots/
    ├── commercial-overview.png
    ├── operations-intelligence.png
    ├── category-analysis.png
    └── customer-insights.png
```

---

## 📚 Documentation

For the complete technical breakdown, including:

* Data sources
* Data model & relationships
* Power Query transformations
* Calculated columns
* Full DAX library
* Dashboard specifications
* KPI validation
* Design decisions
* Business recommendations

See **[Documentation.md](Documentation.md)**.

---

## 👩‍💻 Project Team

* Rawda Hesham
* Shaza Yasser
* Ismail Mahmoud
* Hamza Ahmed
* Omar Zakria
* Wadie Tofiek

---

## 📌 Project

**Olist E-Commerce — Performance Optimization & Customer Journey Intelligence**

**Dataset:** Brazilian E-Commerce Olist Dataset · 2016–2018
**Tool:** Microsoft Power BI
**Dashboard:** 4 Interactive Pages
**DAX:** 28 Measures · 7 Calculated Columns
