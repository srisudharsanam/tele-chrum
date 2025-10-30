## Telecom Customer Churn Prediction

**Project Goal:** To predict customer churn in the telecom industry and identify high-risk customers for targeted retention campaigns.

**Methodology:**

1.  **Data Loading:** Fetches data from a MySQL database (`telecom_churn_data` table).
2.  **Data Cleaning:** Renames columns, converts data types (numeric, binary), and handles basic cleaning.
3.  **Exploratory Data Analysis (EDA):** Visualizes target distribution and numeric feature correlations.
4.  **Preprocessing:** Uses `StandardScaler` for numeric features and `OneHotEncoder` for categorical features (`state`).
5.  **Model Training:** Trains and compares three classification models:
    * Logistic Regression
    * Random Forest Classifier
    * XGBoost Classifier
6.  **Model Evaluation:** Evaluates models using Accuracy, Precision, Recall, F1-score, ROC-AUC, Classification Report, Confusion Matrix, and ROC Curve. XGBoost was selected as the best model based on recall and F1-score.
7.  **Feature Importance:** Uses SHAP (TreeExplainer) with the best model (XGBoost) to understand global feature importance and identify key drivers of churn (e.g., `day_mins`, `custserv_calls`).
8.  **Output:**
    * Saves the best model (`xgb_pipe`) using `joblib`.
    * Calculates churn risk scores (probabilities) for all customers.
    * Creates a `CHURN_FLAG` based on a 0.5 probability threshold.
    * Exports a CSV file (`high_risk_customers.csv`) containing customers flagged as high risk.

**Key Libraries Used:**

* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* SQLAlchemy (+ PyMySQL)
* Joblib
* SHAP

**Outcome:** The project successfully identifies customers likely to churn and provides actionable insights into the factors driving churn, enabling targeted retention strategies.
