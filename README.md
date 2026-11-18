# 🚗 Used Car Price Prediction using KNN Regression

## 📌 Project Overview

This project focuses on predicting the selling price of used cars using **K-Nearest Neighbors (KNN) Regression**, a supervised machine learning algorithm.

The model learns patterns from historical car data and predicts the estimated selling price based on features such as manufacturing year, kilometers driven, fuel type, mileage, engine capacity, maximum power, ownership history, and brand.

## 🎯 Project Objectives

- Understand and explore the used car dataset.
- Perform data cleaning and preprocessing.
- Handle missing values and duplicate records.
- Convert categorical variables into numerical format.
- Apply feature scaling using StandardScaler.
- Build a KNN Regression model.
- Evaluate model performance using regression metrics.
- Predict the selling price of a new car.

## 📂 Dataset Information

**Dataset:** Car Details from CarDekho

- Initial records: 8,128
- Initial features: 13
- Records after removing duplicates: 6,926
- Features used for modeling: 35 (after encoding)

### Important Features

- `year` – Manufacturing year
- `km_driven` – Kilometers driven
- `fuel` – Fuel type
- `seller_type` – Type of seller
- `transmission` – Manual or Automatic
- `owner` – Ownership history
- `mileage` – Car mileage
- `engine` – Engine capacity
- `max_power` – Maximum power
- `brand` – Car manufacturer
- `selling_price` – Target variable

## 🛠️ Technologies & Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## 🔍 Project Workflow

### 1. Data Loading and Exploration

- Loaded the dataset using Pandas.
- Examined dataset shape, information, data types and statistical summary.
- Identified missing values and duplicate records.

### 2. Data Cleaning

- Removed 1,202 duplicate records.
- Reset the DataFrame index.
- Dropped `torque` and `seats` columns.
- Extracted numerical values from `mileage`, `engine`, and `max_power` using regular expressions.
- Handled missing numerical values using median imputation.

### 3. Feature Engineering

- Extracted the car brand from the `name` column.
- Grouped brands appearing fewer than 10 times into an `Other` category.
- Removed the original `name` column.

### 4. Encoding

- Applied One-Hot Encoding to:
  - Fuel
  - Seller Type
  - Transmission
  - Brand
- Applied ordinal mapping to the owner column based on ownership order.

### 5. Train-Test Split

Split the dataset into training and testing sets:

- Training data: 80%
- Testing data: 20%
- Random state: 42

### 6. Feature Scaling

Applied **StandardScaler** to standardize numerical features.

The scaler was fitted only on training data and then used to transform both training and testing data.

Feature scaling is particularly important for KNN because it uses distance calculations to identify neighboring observations.

### 7. Model Building

Implemented KNN Regression using Scikit-learn.

- Algorithm: K-Nearest Neighbors Regression
- Number of neighbors (K): 23

### 8. Model Evaluation

Evaluated the model using the following regression metrics:

| Evaluation Metric |            Result |
| ----------------- | ----------------: |
| MAE               |        117,505.02 |
| MSE               | 67,163,841,928.05 |
| RMSE              |        259,159.88 |
| R² Score          |            0.6938 |
| Adjusted R²       |            0.6858 |

### 9. New Car Price Prediction

Tested the model with a new car's specifications.

The model predicted an estimated selling price of approximately ₹6,70,783.

## 📊 Key Results

- Achieved an R² score of approximately 69.38%.
- The model captures a meaningful relationship between car features and selling prices.
- Implemented an end-to-end machine learning workflow, from data preprocessing to price prediction.

## 📁 Project Structure

```text
Used-Car-Price-Prediction/
│
├── KNN Regression Assignment.ipynb
├── Car details v3.csv
└── README.md
```

## 📚 Key Learnings

- Data cleaning and preprocessing
- Missing value treatment
- Feature extraction and engineering
- One-Hot Encoding and Ordinal Encoding
- Feature scaling using StandardScaler
- KNN Regression
- Regression evaluation metrics
- Making predictions on new data
