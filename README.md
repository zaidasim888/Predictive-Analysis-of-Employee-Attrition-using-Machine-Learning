# Employee Attrition Prediction using Machine Learning

## Project Overview

Employee attrition is one of the most significant challenges faced by organizations. High attrition rates increase recruitment costs, reduce productivity, and result in the loss of experienced employees. The objective of this project is to build a machine learning model that predicts whether an employee is likely to leave the organization based on demographic, professional, and workplace-related attributes.

The project follows a complete data science workflow, including data preprocessing, exploratory data analysis (EDA), feature engineering, model building, evaluation, and interpretation of business insights.

---

# Problem Statement

Develop a machine learning classification model capable of predicting employee attrition based on employee-related characteristics.

Target Variable:

**Attrition**

* Yes (Employee Leaves)
* No (Employee Stays)

Since the target variable contains two classes, this is a **Binary Classification** problem under **Supervised Machine Learning**.

---

# Objectives

* Understand employee data through exploratory analysis.
* Identify important factors contributing to employee attrition.
* Build multiple machine learning models.
* Compare model performance using appropriate evaluation metrics.
* Generate actionable business insights that could assist HR departments in reducing employee turnover.

---

# Dataset

**Dataset Used:** IBM HR Analytics Employee Attrition & Performance Dataset

The dataset contains employee demographic information, job-related details, compensation, satisfaction scores, and attrition status.

Examples of features include:

* Age
* BusinessTravel
* Department
* DistanceFromHome
* Education
* EducationField
* EnvironmentSatisfaction
* Gender
* JobInvolvement
* JobLevel
* JobRole
* JobSatisfaction
* MaritalStatus
* MonthlyIncome
* NumCompaniesWorked
* OverTime
* PercentSalaryHike
* PerformanceRating
* RelationshipSatisfaction
* StockOptionLevel
* TotalWorkingYears
* TrainingTimesLastYear
* WorkLifeBalance
* YearsAtCompany
* YearsInCurrentRole
* YearsSinceLastPromotion
* YearsWithCurrManager

Target Variable:

* Attrition

---

# Technologies Used

Programming Language:

* Python

Libraries:

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

Development Environment:

* Jupyter Notebook

---

# Data Preprocessing

The following preprocessing steps were performed:

* Loaded the dataset using Pandas.
* Examined dataset dimensions.
* Checked data types.
* Verified missing values.
* Verified duplicate records.
* Examined unique categorical values.
* Confirmed data consistency.

Observations:

* No missing values were found.
* No duplicate records were found.
* Data types were consistent.
* The dataset was already clean and required minimal preprocessing.

---

# Feature Engineering

The following transformations were applied:

* Converted the target variable:

  * Yes → 1
  * No → 0

* One-Hot Encoded categorical variables using `pd.get_dummies()`.

* Split the dataset into:

  * Features (X)
  * Target (y)

---

# Train-Test Split

The dataset was divided into:

* Training Data: 80%
* Testing Data: 20%

`stratify=y` was used during splitting to preserve the original class distribution because employee attrition is an imbalanced classification problem.

---

# Exploratory Data Analysis (EDA)

The following analyses were performed:

## Dataset Overview

* Dataset Shape
* Data Types
* Missing Values
* Duplicate Records
* Descriptive Statistics

## Univariate Analysis

* Employee Attrition Distribution
* Age Distribution
* Monthly Income Distribution
* Years at Company Distribution

## Categorical Analysis

* Attrition by Department
* Attrition by Gender
* Attrition by Job Role
* Attrition by Overtime
* Attrition by Business Travel
* Attrition by Marital Status
* Work-Life Balance Distribution

## Numerical Analysis

* Monthly Income vs Attrition
* Age vs Attrition
* Years at Company vs Attrition

## Correlation Analysis

* Correlation Heatmap
* Feature Relationships

Visualizations were created using both Matplotlib and Seaborn, with appropriate data labels added to improve readability.

---

# Machine Learning Models

Three supervised learning algorithms were implemented.

## 1. Logistic Regression

Purpose:

* Baseline classification model.

Advantages:

* Fast
* Easy to interpret
* Produces probability estimates

Result:

Accuracy: **85.37%**

Observation:

Although the model achieved high overall accuracy, it produced a very low recall (11%) for employees who actually left, making it unsuitable as the final model for identifying attrition.

---

## 2. Decision Tree Classifier

Purpose:

* Capture non-linear relationships through rule-based decisions.

Advantages:

* Easy to interpret
* Handles both numerical and categorical data
* Captures complex decision boundaries

Result:

Accuracy: **80.27%**

Observation:

The Decision Tree achieved the highest recall (38%) among the evaluated models, making it more effective at identifying employees likely to leave despite having a lower overall accuracy.

---

## 3. Random Forest Classifier

Purpose:

* Ensemble learning using multiple Decision Trees.

Advantages:

* Reduced overfitting
* Better generalization
* Feature importance estimation

Result:

Accuracy: **84.01%**

Observation:

Although Random Forest achieved good overall accuracy, its recall for the attrition class remained low (11%). This indicates the model favored the majority class and may require further tuning or class balancing.

---

# Model Comparison

| Model               | Accuracy | Precision (Attrition) | Recall (Attrition) | F1-Score (Attrition) |
| ------------------- | -------: | --------------------: | -----------------: | -------------------: |
| Logistic Regression |   85.37% |                  0.83 |               0.11 |                 0.19 |
| Decision Tree       |   80.27% |                  0.38 |               0.38 |                 0.38 |
| Random Forest       |   84.01% |                  0.50 |               0.11 |                 0.18 |

---

# Evaluation Metrics

The following evaluation metrics were used:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report

Reason:

Since employee attrition is an imbalanced classification problem, relying solely on accuracy would be misleading. Recall and F1-score were also considered to evaluate how effectively the models identified employees who actually left the organization.

---

# Business Insights

The analysis provided several useful business insights:

* Employees working overtime exhibited higher attrition.
* Lower job satisfaction was associated with increased attrition.
* Employees with shorter tenure were more likely to leave.
* Salary appeared to influence employee retention.
* Certain departments and job roles experienced higher turnover.
* Employee satisfaction metrics were valuable predictors of attrition.

These findings can help HR teams identify at-risk employees and implement retention strategies.

---

# Challenges

* The dataset was imbalanced, with significantly more employees staying than leaving.
* Logistic Regression and Random Forest achieved high accuracy but low recall for the minority class.
* Improving minority class prediction remains an area for future work.

---

# Future Improvements

Potential enhancements include:

* Hyperparameter tuning using GridSearchCV or RandomizedSearchCV.
* Handling class imbalance using SMOTE or class weighting.
* Evaluating additional algorithms such as XGBoost, LightGBM, and CatBoost.
* Deploying the model using Streamlit.
* Building an interactive HR dashboard integrating predictions and business insights.

---

# Conclusion

This project demonstrated the complete machine learning workflow for solving a binary classification problem. Data preprocessing, exploratory data analysis, feature engineering, model training, and evaluation were successfully performed.

Among the evaluated models, the Decision Tree provided the most balanced performance for detecting employee attrition due to its higher recall, despite having a lower overall accuracy than Logistic Regression. The project also highlighted the importance of evaluating multiple performance metrics rather than relying solely on accuracy when working with imbalanced datasets.

The developed solution provides a foundation for HR analytics by enabling organizations to identify employees at risk of leaving and take proactive measures to improve retention.
