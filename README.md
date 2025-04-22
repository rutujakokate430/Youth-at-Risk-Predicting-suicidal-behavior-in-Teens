# Predicting Youth Suicidality Using Data Science

## Overview
Youth suicidality is a pressing public health concern, with alarming increases in suicidal thoughts and behaviors among teenagers over the past decade. Our project aims to provide actionable insights into identifying at-risk youths using advanced data mining and machine learning techniques. By leveraging the **Youth Risk Behavior Surveillance System (YRBSS)** 2021 dataset, this project highlights key behavioral, demographic, and emotional indicators of suicide risk to aid early intervention strategies.

<img width="242" alt="image" src="https://github.com/user-attachments/assets/f71b0888-8cdc-486a-b985-7d6e7399d9f3" />

---

## Motivation
The Centers for Disease Control and Prevention (CDC) reports a 52.2% increase in youth suicides between 2000 and 2021. Suicide remains the second leading cause of death among individuals aged 10–24. With over 224,000 emergency department visits annually for self-harm in youth, there is a critical need for proactive identification and support systems. This project provides a data-driven approach to addressing this crisis.

---

## Dataset
- **Source**: YRBSS dataset (2021), CDC  
- **Size**: 17,232 respondents, 109 survey questions  
- **Target Variable**: Binary response to "During the past 12 months, did you ever seriously consider attempting suicide?"  
- **Features**: Demographic, behavioral, and emotional indicators.
## Data Mapping from Raw Dataset

The raw dataset provided by the YRBSS consisted solely of numeric values representing survey question numbers and encoded answer choices selected by respondents. These numeric representations required mapping to their corresponding survey questions and response options to make the dataset interpretable and suitable for data analysis.

<img width="379" alt="image" src="https://github.com/user-attachments/assets/c1133bf3-6e9a-4dc0-a29e-c18ea7d8acaf" />

To achieve this, we referred to the **YRBSS Data User Guide**, specifically **Appendix A**, which contains detailed mappings of question numbers and encoded responses to their actual questions and values. Using a custom Python script, we systematically transformed the raw data into a human-readable and structured format by:

1. **Extracting Question Mappings**: Mapping question numbers to their respective textual descriptions.  
2. **Decoding Responses**: Translating encoded response options into their corresponding values based on the guide.  
3. **Creating a Unified Dataset**: Integrating the mappings into the raw dataset to produce a well-structured dataframe ready for analysis.

This transformation step was essential to unlock the dataset's full potential, enabling meaningful exploratory data analysis, hypothesis testing, and predictive modeling.

## Data Preprocessing and Exploratory Data Analysis (EDA)
1. **Handling Missing Data**:  
   - Columns with >40% missing values were excluded.  
   - KNN-based imputation for continuous features (e.g., height, weight).  

2. **Feature Engineering**:  
   - Combined related columns into meaningful composites (e.g., "Tobacco Products Usage").  
   - Introduced calculated features like BMI and categorized it into four groups: Underweight, Healthy Weight, Overweight, and Obese.

3. **Scaling and Encoding**:  
   - Min-max scaling for continuous features.  
   - One-hot encoding for categorical features, resulting in 301 encoded variables.

---

## Methodology
We employed statistical and machine learning techniques to uncover insights and build predictive models:

<img width="510" alt="image" src="https://github.com/user-attachments/assets/0afdb8d6-77e4-4793-8044-61b4875bb931" />


1. **Statistical Analysis**:  
   - **T-tests** for continuous variables (e.g., height, weight, BMI) showed significant differences linked to suicidality.  
   - **Chi-square tests** for categorical variables quantified relationships between features (e.g., gender, race) and the target variable.  
   - **Cramer's V** measured the strength of these associations.

2. **Machine Learning Models**:  
   - **Logistic Regression**: Baseline model with good interpretability.  
   - **Random Forest**: Identified top predictors of suicide risk and achieved high recall.  
   - **XGBoost**: Provided the best accuracy (85%) and robust AUC scores (0.90), excelling in identifying true positives.

3. **Feature Importance**:  
   - Emotional indicators such as "Felt Sad or Hopeless" emerged as the strongest predictors.  
   - Social factors (e.g., bullying, sexual identity) also played significant roles.
     
<img width="601" alt="image" src="https://github.com/user-attachments/assets/02df98a8-4d45-4e97-b009-0aeebec4a923" />

---

## Results and Key Findings
1. **Demographic Insights**:  
   - LGBTQ+ youth showed disproportionately higher risk levels, with bisexual respondents being the most vulnerable group.  
   - Females were twice as likely as males to consider suicide.

2. **Behavioral Patterns**:  
   - Electronic bullying victims had a 2x higher suicide risk.  
   - Substance use (e.g., tobacco, marijuana) correlated with elevated risk levels.

3. **Emotional Health**:  
   - Respondents reporting poor mental health "always" were at the highest risk.

---

## Achievements
- Raw dataset was converted into a form suitable for analysis using multiple mapping techniques using the Appendix A and C in the YRBSS data guide.
- Combining and creating new composite features simplify the data analysis and modeling processes.
- Hypothesis testing and use of statistical tests like T-test, Chi-square test and Cramer’s V help in ensuring statistical rigor and insight generation.
- The overall suicide risk (21.2%) establishes a good baseline measure for comparison against different data cuts.
- Creation of "Risk score“ using predicted probabilities is ideal for quantifying and bucketing an individual's suicide risk.
- Successfully identified key factors influencing suicidal tendencies which are valuable for identifying early indicators of suicidal risk.
- Uniqueness: Our model identifies respondents' risk profiles, allowing teachers, counselors, and authorities to intervene proactively with high-risk respondents to prevent unfortunate events.

<img width="488" alt="image" src="https://github.com/user-attachments/assets/56681b7d-7653-4bf4-aa02-b2b610f7e8c7" />


## Practical Applications
- **Risk Scoring**:  
   A calculated "Suicide Risk Score" categorizes individuals into five actionable risk groups (Very High Risk, High Risk, Moderate Risk, Low Risk, No Risk).

- **Community Impact**:  
   - Helps educators and counselors prioritize resources.  
   - Enables data-driven preventive interventions for at-risk students.  

---

## Challenges
- Balancing data sensitivity with imputation techniques.  
- Managing class imbalance without compromising survey integrity.  
- Ensuring models generalize effectively across diverse populations.

---

## File Structure

- **`YRBS_Data_Mapping_and_Preprocessing.ipynb`**: This notebook focuses on mapping raw survey data into a structured format and performing necessary data preprocessing steps.  
- **`YRBS_EDA_and_Modeling.ipynb`**: This notebook covers Exploratory Data Analysis (EDA) and the development of predictive models for the project.  

## Acknowledgments
This project was guided by Dr. Taehee Jeong and supported by San Jose State University's Applied Data Science Department.
