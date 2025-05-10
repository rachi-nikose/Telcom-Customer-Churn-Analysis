# Telco Customer Churn Analysis 

## 📊 Project Overview

This project aims to explore and analyze customer churn behavior at a fictional telecom company, **TelcoCorp**. 
The dataset includes demographics, account information, services subscribed, and billing data for over 7,000 customers. 
The objective is to uncover churn drivers and suggest actionable business strategies to reduce churn using Exploratory Data Analysis (EDA) in Python.

---

## 🎯 Goal

To identify **key factors** contributing to customer churn and provide **data-driven recommendations** to improve customer retention.

---

## 🧰 Tools & Technologies

- **Python**  
- **Pandas** – for data manipulation  
- **NumPy** – for numerical operations  
- **Matplotlib & Seaborn** – for data visualization  
- **Jupyter Notebook** – for interactive analysis  
- **VS Code** – development environment

---

## 📂 Dataset

- **Source**: IBM Sample Dataset (publicly available)
- **File**: `WA_Fn-UseC_-Telco-Customer-Churn.csv`
- **Rows**: 7,043  
- **Columns**: 21  

Features include:
- Customer demographics: gender, SeniorCitizen, etc.
- Services subscribed: InternetService, TechSupport, etc.
- Billing details: MonthlyCharges, TotalCharges
- Target variable: `Churn` (Yes/No)

---

## 🧹 Data Cleaning Process

1. **Data type corrections** – Converted `TotalCharges` from object to numeric  
2. **Missing values** – Handled blank values in `TotalCharges` by filling with 0  
3. **Column formatting** – Removed irrelevant columns like `customerID`  
4. **Categorical conversions** – Converted binary fields (e.g., `SeniorCitizen`) to categorical types  

---

## 📈 Key Insights from EDA

- 📉 **Churn Rate**: ~26.5%
- 🧾 Customers using **Electronic Check** had the highest churn.
- 📅 **Month-to-month contract** customers were more likely to churn than annual plan users.
- 🔐 Lack of **Online Security** and **Tech Support** correlated with high churn.
- 💰 Customers with **high MonthlyCharges** and **short tenure** showed higher churn risk.
- 👥 Surprisingly, **younger (non-senior) customers** churned more than seniors.

---

## 🧠 Business Recommendations

- 💳 **Improve Payment Methods**: Encourage auto-payment to reduce electronic check churn.
- 📆 **Promote Long-Term Contracts**: Offer incentives for yearly plans.
- 🛠️ **Bundle Value-Added Services**: Offer Online Security and Tech Support packages.
- 🧑‍💼 **Target Non-Senior Customers**: Design engagement campaigns for younger users.

---

#Model Building

The model-building notebook (Churn Analysis - Model Building.ipynb) imports the cleaned tel_churn.csv and 
develops predictive models using Scikit-learn and imblearn:

##Data Preparation:
Removed an unnecessary index column (Unnamed: 0).



Split features and target (Churn).



Addressed class imbalance using SMOTEENN to balance the dataset.



#Models Tested:
###Decision Tree Classifier: Achieved 78.18% accuracy on the imbalanced dataset but poor recall (0.49) for churned customers. 
###With SMOTEENN, accuracy improved to 93.44%, with 0.98 recall for churn.



##Random Forest Classifier: Outperformed Decision Tree, achieving 94.27% accuracy and 0.96 recall for churn with SMOTEENN.

##PCA Attempt: Applied PCA for dimensionality reduction, but accuracy dropped to 72.39%, so it was discarded.

###Final Model: The Random Forest Classifier with SMOTEENN was selected for its superior performance (94.27% accuracy, 0.94 precision, 0.96 recall for churn).

###Model Saving: The final model was saved using Pickle (model.sav) for deployment.

#Results
EDA Insights:
##Streamline electronic check payments to reduce churn.
#Promote longer contracts with discounts.
#Bundle online security and tech support to enhance retention.
#Target non-senior citizens with retention campaigns.
#Predictive Model: The Random Forest model accurately identifies 96% of churned customers, enabling proactive retention strategies.



Business Impact: The model and insights can help TelcoCorp reduce churn, saving revenue by targeting at-risk customers.

