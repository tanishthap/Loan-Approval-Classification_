# Hands-on Exercise 3: Loan Approval Classification
---
## Main Notebook

[Open Notebook](./Loan-Approval-Classification_Fin.ipynb)

## Project Overview

This project builds a machine learning model to predict whether a loan application will be approved. Because the target variable, `approved`, has two possible outcomes, this is a **binary classification problem**.

The notebook includes a full machine learning workflow:
- data loading and inspection
- exploratory data analysis
- preprocessing
- model training
- hyperparameter tuning
- model evaluation
- comparison of multiple classification algorithms

---

## Problem Statement

The goal of this project is to predict loan approval decisions using applicant financial and demographic information.

This is important because loan approval decisions affect:
- bank profitability
- risk exposure
- customer experience
- consistency in decision-making

A good predictive model can help reduce manual work, support faster decisions, and improve the overall lending process.

---

## Stakeholders

Several groups may benefit from this model:

- **Bank management** — to improve profit and manage risk
- **Loan officers** — to support decision-making
- **Customers** — to receive faster and more consistent decisions
- **Compliance and legal teams** — to monitor fairness and lending practices

---

## Ethical Considerations

This project also highlights fairness concerns. Some variables in the dataset, such as age and ethnicity, may introduce bias if used improperly.

Even when sensitive variables are available, they must be handled carefully to avoid discrimination and to support fair lending practices. In a real-world setting, the model should be reviewed for fairness and used with human oversight.

---

## Dataset Information

The dataset contains **690 records** and **17 columns**.

### Target Variable
- `approved`

### Main Predictor Variables
- `gender`
- `age`
- `debt`
- `married`
- `bank_customer`
- `ethnicity_white`
- `ethnicity_black`
- `ethnicity_latino`
- `ethnicity_asian`
- `ethnicity_other`
- `years_employed`
- `prior_default`
- `employed`
- `credit_score`
- `drivers_license`
- `Income`

The dataset is already clean, with no missing values.

---

## Exploratory Data Analysis

The notebook includes:
- target distribution analysis
- missing value checks
- numeric feature histograms
- correlation heatmap
- categorical feature visualizations

### Key EDA Findings
- The target is slightly imbalanced, with more rejected applications than approved ones.
- There are no missing values.
- Strong positive relationships with approval include:
  - `prior_default`
  - `employed`
  - `credit_score`
- Many other variables have weaker relationships with the target.

---

## Preprocessing

The notebook uses a preprocessing pipeline with:

- **StandardScaler** for numeric variables
- **OneHotEncoder** for categorical variables
- **SimpleImputer** for missing values

Since there were no missing values in the dataset, imputation was not needed in practice, but the pipeline is still structured correctly for general use.

The data was split using:
- **train-test split**
- **stratification** to preserve class balance

---

## Models Compared

Three classification models were trained and evaluated:

- **Logistic Regression**
- **K-Nearest Neighbors (KNN)**
- **Support Vector Machine (SVM)**

Each model was tuned using **GridSearchCV** and evaluated using:
- confusion matrix
- classification report
- ROC curve
- ROC AUC
- K-fold cross-validation

---

## Results Summary

### Logistic Regression
- Best ROC AUC: **0.9568**
- Accuracy: **0.8841**
- Mean CV ROC AUC: **0.9175**

### KNN
- Best ROC AUC: **0.9385**
- Accuracy: **0.8841**
- Mean CV ROC AUC: **0.8930**

### SVM
- Best ROC AUC: **0.9451**
- Accuracy: **0.9130**
- Mean CV ROC AUC: **0.9171**

---

## Final Model Selection

The best overall model is **Logistic Regression** because it achieved the highest ROC AUC score and provided the strongest overall ability to distinguish between approved and rejected applications.

### Why it was chosen
- strongest overall ranking performance
- balanced precision and recall
- good generalization across cross-validation folds
- interpretable coefficients for business insight

---

## Business Interpretation

The model suggests that loan approval is strongly influenced by financial stability features such as:
- prior default history
- employment status
- credit score
- income

This makes the model useful as a decision-support tool:
- strong applications can be fast-tracked
- borderline applications can be reviewed manually
- risky applications can be flagged earlier

---

## Conclusion

This project demonstrates how machine learning can support loan approval decisions while also showing the importance of fairness and interpretability in financial applications.

The final Logistic Regression model performs best overall and provides a strong baseline for real-world lending analytics.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---



---

## Author

Tanishtha Papadkar
