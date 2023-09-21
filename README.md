# Diabetes_Predecition

This process performs a series of data preprocessing and machine learning tasks on a dataset. Here's a step-by-step explanation of what each section of the code does:

1. **Importing Libraries**:
   - The code imports various Python libraries, including Pandas, NumPy, Matplotlib, Seaborn, XGBoost, scikit-learn, and others, which are used for data manipulation, visualization, and machine learning.

2. **Loading the Dataset**:
   - Loads a dataset from an Excel file named 'dia_data.xlsx' into a Pandas DataFrame called `df`.
   - Displays basic information about the dataset, including its shape, the first few rows, data types, and the count of missing values.
   - Replaces '?' values with NaN (missing values) in the DataFrame.

3. **Handling Missing Data**:
   - Calculates the percentage of missing values in specific columns ('weight', 'payer_code', 'medical_specialty') and drops those columns if they have a high percentage of missing values.
   - Fills missing values in the 'race' column by grouping it based on 'patient_nbr' and filling missing values within each group with the mode of that group.

4. **Data Transformation**:
   - Maps the 'age' values to numerical values using a predefined `age_map` dictionary.

5. **Data Exploration and Visualization**:
   - Visualizes numerical columns using histograms and box plots to explore the distribution and outliers in the data.

6. **Data Type Conversion**:
   - Converts specific numerical columns to object type, likely for categorical encoding and visualization purposes.

7. **Outlier Removal**:
   - Detects and removes outliers in the numerical columns using the Interquartile Range (IQR) method.

8. **Low Variance Column Removal**:
   - Identifies and drops columns with low variance (where one value accounts for over 95% of the data).

9. **Categorical Data Visualization**:
   - Visualizes categorical columns using count plots to explore the distribution of categories with respect to the 'readmitted' target variable.

10. **Data Cleaning and Filtering**:
    - Removes records with duplicate 'gender' values within the same 'patient_nbr' group.
    - Removes records with conflicting 'age' values within the same 'patient_nbr' group.
    - Filters out records with 'gender' values as 'Unknown/Invalid'.

11. **ICD-9 Code Categorization**:
    - Categorizes ICD-9 codes into broader categories based on a predefined function.

12. **Medication Data Processing**:
    - Maps medication values to binary values (0 or 1) indicating if medication was taken.
    - Maps values in the 'A1Cresult', 'max_glu_serum', 'change', and 'diabetesMed' columns to numerical values.

13. **Label Encoding**:
    - Converts object-type columns to numerical using Label Encoding.

14. **Data Splitting and Standardization**:
    - Splits the data into training and testing sets.
    - Standardizes numerical columns to have zero mean and unit variance using StandardScaler.

15. **Logistic Regression Model**:
    - Trains a Logistic Regression model on the training data and evaluates it on the test data.

16. **XGBoost Model**:
    - Trains an XGBoost classifier on the training data and evaluates it on the test data.

Overall, this process demonstrates a comprehensive data preprocessing pipeline, including data cleaning, visualization, feature engineering, and machine learning model training and evaluation on healthcare data.
