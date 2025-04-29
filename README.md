# 🚢 Titanic Survival Prediction

A machine learning project to predict whether a passenger survived the Titanic disaster using data such as age, gender, passenger class, and more. This project is part of the GrowthLink internship assignment.

---

## 📂 Dataset

- **Source**: [Kaggle Titanic Competition](https://www.kaggle.com/competitions/titanic/data)
- **Files used**: `train.csv`, `test.csv`
- The dataset includes passenger details like age, gender, class, fare, family size, etc.
 
📌 Note: The dataset given in the pdf was broken as there was no survival labeled column which is important for prediction of survival. Therefore, I used the main Titanic Dataset from kaggle.

---

## 🎯 Objective

To build and evaluate machine learning models that can accurately predict the survival of passengers on the Titanic based on available features.

---

## 🛠️ Steps Performed

### 1. Exploratory Data Analysis (EDA)
- Plotted survival distribution across different passenger classes, genders, and family size.
- Analyzed correlations between features using a heatmap.
- Observed that gender, class, and fare had significant relationships with survival.

### 2. Data Preprocessing
- Handled missing values in `Age` (filled with median) and `Embarked` (filled with mode).
- Dropped irrelevant or non-informative columns: `Name`, `Ticket`, and `Cabin`.
- Converted `Sex` to numeric (0 = male, 1 = female).
- One-hot encoded `Embarked`.
- Created a new feature: `FamilySize = SibSp + Parch`.

### 3. Model Building
Two models were trained and evaluated:

#### ✅ Logistic Regression
- Used as a baseline model.
- Achieved decent performance with minimal tuning.

#### ✅ Random Forest Classifier
- Performed better than logistic regression by capturing nonlinear relationships.

---

## 🔧 Hyperparameter Tuning

Used **GridSearchCV** to tune the Random Forest model.

- **Best Parameters**:
  - `n_estimators`: 150
  - `max_depth`: 4
  - `min_samples_split`: 5
  - `min_samples_leaf`: 1

- **Best Cross-Validation Accuracy**: 83.28%
- **Validation Set Accuracy After Tuning**: 80.45%

**Default Random Forest Accuracy** (before tuning): 82.12%

📌 *Observation*: While the tuned model performed better on cross-validation, the untuned model actually performed slightly better on the validation set — a common occurrence in real-world modeling.

---

## 📊 Results Summary

| Model               | Accuracy | Notes                                                   |
|---------------------|----------|---------------------------------------------------------|
| Logistic Regression | 81.00%   | Simple baseline                                         |
| Random Forest       | 82.12%   | Best performance (untuned)                              |
| Tuned Random Forest | 80.45%   | Best cross-validation, slightly lower hold-out accuracy |

---

## 💡 Future Improvements

- Extract titles from `Name` (e.g., Mr, Mrs, Miss) for additional feature power.
- Try advanced classifiers like XGBoost, SVM.
- Apply SMOTE or similar if class imbalance becomes significant.
- Deploy as a web app using Streamlit or Flask.

---

## 🧑‍💻 Author

- *Snehil Singh*  
- *GitHub*: [snehil-mod](https://github.com/snehil-mod)  
- *LinkedIn*: [sneyyhil](https://linkedin.com/in/sneyyhil)

