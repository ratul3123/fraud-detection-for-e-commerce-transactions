# E-Commerce Transaction Fraud Detection

A machine learning project focused on detecting fraudulent transactions in e-commerce platforms using classification algorithms and advanced preprocessing techniques.

---

## Overview

E-commerce fraud is a growing issue that leads to financial losses and reduced customer trust. This project builds a fraud detection system that analyzes transaction patterns and identifies suspicious activities using machine learning models.

The system leverages structured transaction data and applies preprocessing, feature engineering, and classification techniques to achieve reliable fraud detection.

---

## Objectives

* Detect fraudulent transactions with high accuracy
* Handle imbalanced datasets effectively
* Compare multiple machine learning models
* Improve model performance using feature engineering and scaling

---

## Dataset

* **Source:** Kaggle – *[Fraudulent E-Commerce Transactions](https://www.kaggle.com/datasets/shriyashjagtap/fraudulent-e-commerce-transactions)*
* **Total Instances:** 23,634
* **Features:** 16
* **Target Variable:** `Is Fraudulent`

  * `0` → Not Fraudulent
  * `1` → Fraudulent

### Feature Types

* **Numerical:**

  * Transaction Amount
  * Quantity
  * Customer Age
  * Account Age Days
  * Transaction Hour

* **Categorical:**

  * Payment Method
  * Product Category
  * Device Used
  * (Several identifiers and address-related fields)

---

## Data Preprocessing

### Data Cleaning

* No missing values
* No duplicate records

### Feature Removal

Dropped irrelevant features:

* Transaction ID
* Customer ID
* Transaction Date
* Customer Location
* IP Address
* Shipping Address
* Billing Address

### Encoding

* Applied **One-Hot Encoding** to:

  * Payment Method
  * Product Category
  * Device Used

### Handling Imbalance

* Dataset was highly imbalanced:

  * Majority: Not Fraudulent
  * Minority: Fraudulent

* Applied **SMOTE (Synthetic Minority Oversampling Technique)**:

  * Oversampled minority class
  * Improved model fairness and recall

---

## Feature Engineering

* Created a new feature: **Address Match**

  * `1` → Shipping & Billing address match
  * `0` → Mismatch

This helps detect suspicious transactions.

---

## Feature Scaling

Applied scaling techniques to normalize numerical features:

* StandardScaler
* MinMaxScaler
* RobustScaler

Scaled features:

* Transaction Amount
* Customer Age
* Account Age Days
* Transaction Hour

---

## Train-Test Split

* **Training Set:** 70%
* **Testing Set:** 30%
* Used **stratified splitting** to preserve class distribution

---

## Models Used

The following machine learning models were implemented and compared:

* **K-Nearest Neighbors (KNN)**
* **Logistic Regression**
* **Gaussian Naive Bayes**
* **Decision Tree**
* **Random Forest**

---

## Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

### Key Insight

* Initial results were biased toward the majority class (Not Fraud)
* After applying **SMOTE**, model performance improved significantly, especially for detecting fraudulent transactions

---

## Results Summary

* All models performed competitively after preprocessing
* **Random Forest** and **Logistic Regression** showed strong overall performance
* Handling class imbalance was critical for meaningful evaluation

---

## Challenges

* Severe class imbalance
* Risk of overfitting on minority class
* Limited dataset size affecting generalization

---

## Conclusion

This project demonstrates that effective preprocessing and imbalance handling are crucial for fraud detection systems. By applying SMOTE, feature engineering, and scaling techniques, the models achieved significantly improved and reliable performance.

---

## Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* Seaborn / Matplotlib
