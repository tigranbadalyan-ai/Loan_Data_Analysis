# 🏦 Banking Risk & ALM Analysis: Credit Default Prediction

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

This project presents a **Strategic Loan Portfolio Analysis & Risk Management** framework developed for a banking **ALM (Asset and Liability Management)** department. It combines data engineering, SQL management, and Machine Learning to predict credit defaults.

## 📊 Project Structure
* **`DATA/`**: Source datasets containing loan contract details.
* **`SQL/`**: Database scripts and `alm_database` file for relational data experiments.
* **`notebooks/analytics.ipynb`**: Main Jupyter Notebook with data cleaning and ML models.
* **`for_power_bi/`**: Exported data for financial dashboarding.

---

## 🎯 Objective
The goal is to build an analytical pipeline that provides:
1. **Credit Risk Assessment**: Identifying "Default" cases using FICO, DTI, and financial history.
2. **Profitability Analysis**: Benchmarking customer rates against the **Cost of Funds (7.25%)**.
3. **Liquidity Planning**: Mapping cash inflows based on loan tenors (36-60 months).

---

## 🛠 Implementation Steps

### 1. Data Cleaning & Integrity
* Removed over 1 million rows of structural noise and empty artifacts.
* Converted financial strings (Interest Rates, Revolving Utilization) into numeric floats.
* Applied **Smart Outlier Cleaning** based on logical banking bounds (e.g., FICO 300-850).

### 2. Feature Engineering
Created specialized financial indicators to improve model signal:
* **Installment-to-Income (ITI)**: Monthly debt burden relative to actual income.
* **Credit History Years**: Standardized credit age from days to years.
* **Credit Stress Index**: A combined metric of inquiries and FICO scores.
* **One-Hot Encoding**: Transformed loan purposes into numeric vectors.

### 3. Predictive Modeling
I implemented two distinct models to compare performance:
* **Logistic Regression**: Used as a transparent baseline for banking regulations.
* **XGBoost**: An advanced ensemble model to capture non-linear risk patterns.

---

## 📈 Model Performance Results

| Metric | Logistic Regression (Baseline) | XGBoost Classifier |
| :--- | :--- | :--- |
| **Accuracy** | **83.73%** | **83.88%** |
| **ROC-AUC** | **0.6785** | **0.6601** |

**Observations:** Both models show high accuracy, but suffer from class imbalance (low Recall for defaults). Interestingly, the Logistic Regression baseline performed slightly better in terms of ROC-AUC, while XGBoost showed higher precision for specific risk segments.

---

## 💻 Tech Stack
* **Language:** Python (Pandas, NumPy, Matplotlib, Seaborn)
* **ML Library:** Scikit-Learn, XGBoost
* **Database:** SQL (SQLite) for data persistence experiments
* **Visualization:** Power BI for executive reporting
