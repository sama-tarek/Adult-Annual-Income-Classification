# Adult Annual Income Classification 💰

## 📌 Project Overview

This project uses **Machine Learning classification techniques** to predict whether an individual's annual income is **≤ $50K or > $50K** based on demographic and employment-related characteristics.

The project focuses on exploring the dataset, cleaning and preprocessing the data, performing feature engineering, building classification models, and evaluating their performance.

Two machine learning models were developed and compared:

* **Logistic Regression**
* **Decision Tree Classifier**

---

## 🎯 Business Problem

Understanding the factors associated with higher income levels can help identify patterns in demographic and employment data.

The goal of this project is to build a classification model that can predict an individual's income category:

* `0` → ≤ $50K
* `1` → > $50K

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Explore and understand the Adult Census Income dataset.
* Identify and handle missing and inconsistent data.
* Perform Exploratory Data Analysis (EDA).
* Engineer useful features from existing variables.
* Prepare numerical and categorical features for Machine Learning.
* Build a Logistic Regression model.
* Build a Decision Tree model.
* Evaluate both models using multiple classification metrics.
* Compare the models' performance.
* Analyze important features related to income classification.

---

## 📊 Dataset

The project uses the **Adult Census Income dataset** from the **UCI Machine Learning Repository**.

The dataset contains demographic and employment-related information such as:

* Age
* Workclass
* Education
* Education Number
* Marital Status
* Occupation
* Relationship
* Race
* Sex
* Capital Gain
* Capital Loss
* Hours per Week
* Native Country
* Income

The target variable is **Income**.

### Target Classes

| Class | Meaning       |
| ----- | ------------- |
| `0`   | Income ≤ $50K |
| `1`   | Income > $50K |

---

## 🛠️ Technologies & Libraries

The project was developed using **Python** and the following libraries:

* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical operations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Scikit-learn** — Data preprocessing, Machine Learning, and evaluation
* **ydata-profiling** — Automated data profiling
* **ucimlrepo** — Accessing the UCI dataset

---

## 🔄 Project Workflow

The project follows these main steps:

### 1. Data Loading

The Adult Census Income dataset was loaded using `ucimlrepo`.

### 2. Data Understanding

The dataset was explored using:

* `info()`
* `describe()`
* Missing-value analysis
* Value counts
* Data profiling

### 3. Data Cleaning

Several preprocessing steps were performed:

* Removed unnecessary spaces from categorical values.
* Converted `?` values into missing values.
* Replaced missing values in selected categorical columns with `"Unknown"`.
* Checked and removed duplicate rows.
* Standardized the target variable.
* Removed the redundant `education` column because `education-num` provides the numerical representation of education.

### 4. Feature Engineering

New features were created to provide additional information to the models:

* `age_group`
* `has_capital_gain`
* `has_capital_loss`
* `work_hours_group`

### 5. Outlier Analysis

Boxplots and the IQR method were used to investigate potential outliers in the `age` feature.

The observed age range was:

**17 to 90 years**

No age values were considered problematic outliers based on the analysis.

### 6. Data Preprocessing

Different preprocessing techniques were applied according to the feature type.

**Numerical Features**

* `StandardScaler`

**Nominal Categorical Features**

* `OneHotEncoder`

**Ordinal Features**

* `OrdinalEncoder`

A `ColumnTransformer` and Scikit-learn `Pipeline` were used to organize the preprocessing and modeling steps.

### 7. Train/Test Split

The dataset was divided into:

* **80% Training Data**
* **20% Testing Data**

Stratified splitting was used to preserve the target-class distribution.

---

## 🤖 Machine Learning Models

### Logistic Regression

A Logistic Regression model was trained as one of the classification models.

The model achieved:

| Metric   |      Score |
| -------- | ---------: |
| Accuracy | **85.61%** |
| ROC-AUC  | **77.15%** |

The model performed particularly well on the `≤50K` class but had lower recall for the `>50K` class.

### Decision Tree

A Decision Tree Classifier was also trained and evaluated.

The model achieved:

| Metric   |      Score |
| -------- | ---------: |
| Accuracy | **81.57%** |
| ROC-AUC  | **75.03%** |

The Decision Tree showed slightly higher recall for the `>50K` class but lower performance on several other metrics.

---

## 📈 Model Comparison

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix
* Classification Report

### Results

| Model               |   Accuracy |   F1 Score |    ROC-AUC |
| ------------------- | ---------: | ---------: | ---------: |
| Logistic Regression | **85.61%** | **66.96%** | **77.15%** |
| Decision Tree       |     81.57% |     61.88% |     75.03% |

Based on the evaluation performed in this project, **Logistic Regression was selected as the final model** because it provided stronger overall performance across most of the evaluation metrics.

---

## 🔍 Feature Importance

Feature importance was also analyzed using the Decision Tree model to identify features that contributed most to the model's predictions.

The project includes a visualization of the **Top 15 Important Features**.

This helps provide additional insight into which demographic and employment-related characteristics contain useful information for income classification.

---

## 📊 Visualizations

The project includes several visualizations, including:

* Data profiling report
* Age boxplot
* Confusion matrices
* Model comparison chart
* Top 15 feature importance chart

These visualizations help understand the dataset and evaluate the machine learning models.

---

## 💡 Key Insights

Some of the main findings from the project include:

* The dataset contains both numerical and categorical variables.
* Missing and inconsistent values required preprocessing before modeling.
* The target variable is imbalanced, with more individuals in the `≤50K` category.
* Feature engineering was used to create additional age, capital gain/loss, and working-hours information.
* Both models were able to classify income categories with reasonable performance.
* Logistic Regression achieved higher overall performance across most evaluation metrics.
* The `>50K` class was more difficult for both models to identify compared with the `≤50K` class.

---

## 📁 Project Structure

```text
Adult-Annual-Income-Classification/
│
├── Adult_Annual_Income_Classification.ipynb
├── Adult Annual Income Report.html
├── README.md
│
└── Images/
    ├── Age_Boxplot.png
    ├── Logistic_Regression_Confusion_Matrix.png
    ├── Decision_Tree_Confusion_Matrix.png
    ├── Model_Comparison.png
    └── Feature_Importance.png
```

> You can adjust the file and image names to match the files you actually upload to GitHub.

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Adult-Annual-Income-Classification.git
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn ucimlrepo ydata-profiling
```

### 3. Open the notebook

Open:

```text
Adult_Annual_Income_Classification.ipynb
```

using **Jupyter Notebook** or **JupyterLab**.

### 4. Run the cells

Run the notebook cells from top to bottom to reproduce the analysis and model results.

---

## 🔮 Future Improvements

Possible improvements for future versions of this project include:

* Hyperparameter tuning.
* Trying additional classification algorithms.
* Handling class imbalance using techniques such as class weighting or resampling.
* Performing cross-validation.
* Improving the feature engineering process.
* Comparing additional evaluation metrics.
* Deploying the final model as a simple web application or API.

---

## 👩‍💻 Author

**Sama Tarek**

Aspiring Data Scientist interested in **Data Analysis, Machine Learning, and Data Science**.

---

## ⭐ Project Status

**Completed — Learning Project**

This project was created as part of my journey in learning **Data Science and Machine Learning**, with a focus on data preprocessing, exploratory analysis, feature engineering, classification, and model evaluation.
