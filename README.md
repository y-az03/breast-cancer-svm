# Breast Cancer Diagnosis Using Support Vector Machines (SVM)

## Overview

This project applies Machine Learning techniques to the Wisconsin Diagnostic Breast Cancer Dataset in order to classify breast tumors as **Benign** or **Malignant**.

The project follows a complete machine learning workflow, including:

* Exploratory Data Analysis (EDA)
* Data preprocessing
* Feature scaling
* Principal Component Analysis (PCA)
* Support Vector Machine (SVM) classification
* Kernel comparison (Linear vs RBF)
* Hyperparameter optimization using GridSearchCV
* Performance evaluation using classification metrics, confusion matrix, and ROC-AUC analysis

---

## Dataset

The project uses the Wisconsin Diagnostic Breast Cancer Dataset (WDBC).

### Dataset Characteristics

* 569 patient records
* 30 numerical features
* Binary classification:

  * Benign (B)
  * Malignant (M)

The features are computed from digitized images of breast mass cell nuclei.

---

## Project Workflow

### 1. Data Exploration

* Dataset inspection
* Missing values analysis
* Descriptive statistics
* Class distribution analysis

### 2. Feature Engineering

* Removal of Patient ID
* Target encoding
* Feature scaling using StandardScaler

### 3. Exploratory Data Analysis

* Correlation Matrix
* Feature correlation with diagnosis
* Class distribution visualization

### 4. Dimensionality Reduction

* Principal Component Analysis (PCA)
* 2D visualization of tumor classes

### 5. Model Development

#### Linear SVM

Accuracy: **95.61%**

#### RBF SVM

Accuracy: **98.25%**

### 6. Hyperparameter Optimization

GridSearchCV identified the optimal parameters:

```python
{
    "C": 100,
    "gamma": 0.001,
    "kernel": "rbf"
}
```

Cross-validation score:

```text
97.36%
```

Optimized model accuracy:

```text
98.25%
```

---

## Results

| Model             | Accuracy |
| ----------------- | -------- |
| Linear SVM        | 95.61%   |
| RBF SVM           | 98.25%   |
| Optimized RBF SVM | 98.25%   |

The RBF kernel significantly outperformed the linear kernel, indicating the presence of non-linear relationships in the dataset.

---

## Confusion Matrix

```text
[[71  0]
 [ 2 41]]
```

### Interpretation

* 71 benign tumors correctly classified
* 41 malignant tumors correctly classified
* 0 false positives
* 2 false negatives

The low number of false negatives is particularly important in a medical context because missing a malignant tumor may delay diagnosis and treatment.

---

## PCA Analysis

Principal Component Analysis was used to reduce the dimensionality of the dataset and visualize the data in a two-dimensional space.

The PCA visualization revealed a clear separation between benign and malignant tumors, supporting the strong classification performance achieved by the SVM model.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

## Repository Structure

```text
breast-cancer-svm/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── wdbc.data
│
├── notebook/
│   └── svm_pca.ipynb
│
├── images/
│   ├── correlation_matrix.png
│   ├── pca_visualization.png
│   ├── confusion_matrix.png
│   └── roc_curve.png
│
└── results/
    └── model_comparison.csv
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/y-az03/breast-cancer-svm.git
```

Navigate to the project folder:

```bash
cd breast-cancer-svm
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

---

## Key Learning Outcomes

* Exploratory Data Analysis (EDA)
* Feature Scaling
* Principal Component Analysis (PCA)
* Support Vector Machines (SVM)
* Kernel Selection
* Hyperparameter Tuning
* Model Evaluation
* Medical Data Classification

---

## Conclusion

This project demonstrates the effectiveness of Support Vector Machines for breast cancer diagnosis. The optimized RBF SVM achieved an accuracy of 98.25% while maintaining a very low number of false negatives.

The results highlight the potential of machine learning techniques to support medical decision-making and early disease detection.
