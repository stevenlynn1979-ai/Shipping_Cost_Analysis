# # Data-Driven Logistics: Optimizing E-Commerce Shipping Profitability

## 📊 Business Impact Summary
> ### 💶 Net Margin Lift: **€184,733**
> The analysis **strongly recommends** transitioning from the linear baseline to the proposed tiered shipping model. Implementing this change is projected to significantly increase profitability, especially when combined with high-volume customer bundling incentives.

---

## 🎯 Project Objective
The goal of this project was to analyze e-commerce transaction data, model a new tiered multi-item shipping strategy against the current baseline, and determine its direct impact on business profitability over a standard **1,000-mile distribution radius**.

---

## 🛠️ The Data Challenge & ETL Pipeline
The raw dataset was highly fragmented, containing mixed capitalizations, inconsistent formatting, and critical missing values across transactional, geographic, and product dimensions. 

To preserve data integrity without compromising row volume, data cleaning was executed using **Python** and **Excel** under the following strategic engineering assumptions:

* **Zero/Missing Quantities:** Since rows represent valid web transactions, there could be no 0 or blank quantities. All null or `0` quantities were defaulted to **`1`**.
* **Imputed Order Dates:** For dates that could not be determined, it was assumed the product was ordered just after the row above. The timestamp was sequentially copied from the **previous row**.
* **Customer ID Resolution:** Missing IDs were backfilled by mapping them against known `Order ID` relationships, assuming that every order ID was unique. 
* **Unidentifiable Users (`UID: 99999`):** A group of user IDs that could not be determined were grouped together under a fallback ID of **`99999`**. The geographical distribution of existing clients was analyzed, and these newly created users were spread proportionally across those geographic locations to maintain accurate regional shipping density.
* **Product Anonymization:** A valuable section of products could not be determined through unit cost or order ID. These were grouped together into a category named **`Unknown`** to ensure all sales data was fully accounted for.

---

## 📈 Key Insights & Recommendations
* **Adopt the New Model:** Retrospective simulation shows that if the proposed model had been implemented last year, it would have decreased shipping costs and delivered a net margin lift of **€184,733**.
* **Launch A/B Testing:** Before rolling this out company-wide, a controlled **A/B test** should be conducted to evaluate real-world customer checkout behavior against the simulated data.
* **Volume-Based Incentives:** The data reveals that the sharpest logistics cost savings trigger at **5 or more items** per order. The business should implement a slight discount model (the more items a person buys, the greater their discount) to actively steer consumer carts toward these high-margin thresholds.

---

## 💻 Tech Stack
* **Data Cleansing & Modeling:** Python (Pandas/NumPy), Microsoft Excel
* **Data Visualization:** Tableau Dashboard (`https://public.tableau.com/app/profile/steve.lynn6910/viz/Pet_Supply_Test/Dashboard1`)

