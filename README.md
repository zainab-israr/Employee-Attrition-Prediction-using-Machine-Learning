# Employee Attrition Prediction

This project is an end-to-end **Employee Attrition Analysis and Prediction** pipeline using Machine Learning and Explainable AI. The goal is to help HR identify high-risk employees and implement targeted retention strategies.

---

## Project Overview
The notebook covers:

- Data Understanding & Preprocessing
- Exploratory Data Analysis (EDA)
- Handling Class Imbalance (SMOTE / Class Weights)
- Model Training & Evaluation
- Hyperparameter Tuning using GridSearchCV
- Model Explainability with SHAP
- Final Insights and Actionable Recommendations for HR

**Goal:** Predict employee attrition and understand key drivers behind it.

---

## Dataset
- Contains employee demographic, job, and performance data
- Features include Age, Gender, Department, JobRole, JobLevel, MonthlyIncome, OverTime, WorkLifeBalance, DistanceFromHome, YearsAtCompany, etc.
- Target variable: `Attrition` (Yes / No)

---

## Key Insights from EDA
- Higher attrition among **younger employees (<35 years)**
- Employees with **OverTime = Yes** are more likely to leave
- Low **JobLevel** and **MonthlyIncome** correlate with higher attrition
- Poor **WorkLifeBalance (1–2)** increases risk
- Departments **Sales & R&D** show higher attrition
- Longer **DistanceFromHome** increases churn
- **Single employees** show higher attrition

---

## Models Trained
- Logistic Regression
- Decision Tree
- **Random Forest (Best Performing)**
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)

**Evaluation Metrics:**
- Accuracy, Precision, Recall, F1-Score, Confusion Matrix, ROC-AUC

**Best Model:** Tuned Random Forest Classifier with strong performance and explainability via SHAP.

---

## Hyperparameter Tuning
- Used **GridSearchCV** on Random Forest
- Parameters tuned: `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`
- **5-fold Cross-validation** for optimal accuracy
- Improved generalization and reduced overfitting

---

## Explainability with SHAP
- **Global Explanation:** Identified top drivers of attrition  
  `OverTime, MonthlyIncome, JobLevel, Age, WorkLifeBalance, YearsAtCompany, DistanceFromHome`
- **Local Explanation:** SHAP waterfall plots provide employee-specific insights
- Helps HR justify decisions and design targeted retention actions

---

## Final Conclusions
- Key factors influencing attrition: high overtime, low income, younger age, poor work-life balance, low job level, long commute, certain departments
- Random Forest is the most suitable model with explainable results
- Actionable recommendations for HR provided

---

## Next Steps
**For HR:**
- Weekly identification of high-risk employees
- Use SHAP explanations for root-cause analysis
- Reduce overtime, review compensation, improve work-life balance
- Mentorship programs for younger employees (<3 years)

**Technical:**
- Deploy prediction + SHAP pipeline
- Monitor performance quarterly
- Risk segmentation:
  - High: ≥0.70
  - Medium: 0.40–0.69
  - Low: <0.40

---

## Technologies Used
- Python 3.x
- Pandas, NumPy
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Matplotlib & Seaborn
- SHAP (Explainable AI)
- Jupyter Notebook
