# E-Commerce Retail Sales: Pure Python Exploratory Data Analysis (EDA)

---

## Business Problem & Project Overview
In modern e-commerce retail operations, unsustainable discounting, logistical delivery delays, and high Return-to-Origin (RTO) rates significantly erode net profit margins[cite: 7]. 

This project conducts an end-to-end, **100% Python-based Exploratory Data Analysis (EDA)** across transaction logs to uncover core operational bottlenecks, examine discount-to-margin sensitivity, and isolate root drivers behind product returns[cite: 7].

> **Audit Compliance Note:** This repository is implemented strictly in **Pure Python** using **Pandas, NumPy, and Matplotlib**, completely independent of third-party BI software (Power BI / Tableau)[cite: 7].

---

## Data Pipeline & Cleaning Methodology
- **Deduplication:** Applied `df.drop_duplicates()` across transactional keys to eliminate redundant records[cite: 7].
- **Missing Value Imputation:** Handled missing numeric attributes via grouped median imputation across respective retail verticals[cite: 7].
- **Outlier Treatment:** Implemented Interquartile Range (IQR) filtering rules to detect and treat skewed extreme values in order sizes and pricing[cite: 7].
- **Statistical Transformations:** Evaluated scale relationships using `np.log10()` transformations and fitted parametric trends via polynomial OLS regressions[cite: 7].

---

## Exploratory Analysis & Key Findings

### 1. Revenue Concentration by Vertical
- **Apparel** represents the primary revenue generator at **₹210M**, followed by **Electronics** at **₹170M**[cite: 7].
- **Home (₹140M)**, **Beauty (₹105M)**, and **Sports (₹67M)** comprise the remaining distribution[cite: 7].

### 2. Payment Modes & The COD Return Crisis (RTO)
- **UPI** dominates checkout frequency with over **4,400 orders**, followed by Credit Cards (~2,200 orders) and Cash on Delivery (~2,200 orders)[cite: 7].
- **Return Rate Breakdown:**
  - **Cash on Delivery (COD):** **17.5% RTO rate** (nearly 3x higher return rate compared to prepaid transactions)[cite: 7].
  - **Debit Card:** 6.3% RTO rate[cite: 7].
  - **Credit Card:** 6.2% RTO rate[cite: 7].
  - **UPI:** **5.6% RTO rate** (lowest return rate across all modes)[cite: 7].

### 3. Discount Sensitivity & Profit Margin Floor
- Statistical correlation proves that **every 1% increase in discount erodes profit margin by -0.55%**[cite: 7].
- Offering discounts exceeding **15%–20%** breaches the baseline **15% operational margin floor**, leading to margin degradation[cite: 7].

### 4. Delivery SLAs vs. Customer Cancellations
- **<= 4 Days Delivery:** Maintains an RTO rate of **5.2%**[cite: 7].
- **5–7 Days Delivery:** RTO rises moderately to **9.8%**[cite: 7].
- **> 7 Days Delivery:** Severe SLA breaches cause returns to jump to **22.5%** (+14% increase) due to buyer disengagement[cite: 7].

---

## Strategic Recommendations

| Focus Area | Operational Challenge | Recommended Business Strategy |
| :--- | :--- | :--- |
| **Discount Guardrails**[cite: 7] | Margin erosion (-0.55% per 1% discount)[cite: 7] | Cap universal storefront discounts at **15%–20%** maximum[cite: 7]. |
| **Payment Incentives**[cite: 7] | COD drives 18.5% RTO returns[cite: 7] | Offer instant cashback or checkout incentives for **UPI/prepaid** to reduce COD orders[cite: 7]. |
| **Logistics SLAs**[cite: 7] | Delivery delays past 7 days spike returns by +14%[cite: 7] | Enforce a strict **<= 4-day regional dispatch SLA** through local micro-warehouses[cite: 7]. |

---

## Repository Structure
```text
ecommerce-retail-sales-eda/
│
├── data/
│   └── ecommerce_retail_data.csv        # Transaction dataset
│
├── screenshots/
│   ├── ecommerce_univariate_audit.png   # Matplotlib distributions & RTO charts
│   └── ecommerce_multivariate_eda.png   # OLS regressions & correlation heatmaps
│
├── Ecommerce_Retail_Sales_EDA.py        # Complete Pure Python pipeline script
├── Ecommerce_Retail_Pure_Python_EDA.pptx # Executive presentation deck
└── README.md                            # Project documentation
