
## Introduction

The HIV/AIDS epidemic has been one of the most problematic public health crises of the last century, impacting millions of lives globally. Within New York City, a metropolis with a significant at-risk population, the epidemic's dynamics are captured in detail through the DOHMH HIV/AIDS Annual Report. This dataset provides a granular view of the epidemic's progression, treatment outcomes, and demographic influences from year to year. The prevalence and management of HIV/AIDS remain critical issues, with significant implications for public health policy, resource allocation, and community outreach programs. Utilizing this dataset, we propose to construct a predictive model that can provide insights into the factors contributing to these outcomes and potentially forecast future trends.

==

Data Source: [DOHMH HIV/AIDS Annual Report](#https://data.cityofnewyork.us/Health/DOHMH-HIV-AIDS-Annual-Report/fju2-rdad/about_data)

==

## Data Dictionary

| Column Name                    | Description                                                                                     | Type    |
|--------------------------------|-------------------------------------------------------------------------------------------------|---------|
| Year                           | Calendar year of the report                                                                     | Text    |
| Borough                        | Borough of residence at different stages of HIV/AIDS (diagnosis, treatment, death)              | Text    |
| UHF                            | United Hospital Fund neighborhood at different stages of HIV/AIDS                              | Text    |
| Gender                         | Gender of the individual, including transgender categories                                     | Text    |
| Age                            | Age at different stages of HIV/AIDS                                                            | Text    |
| Race                           | Race/ethnicity of the individual                                                               | Text    |
| HIV diagnoses                  | Number of HIV diagnoses for individuals 13 years or older                                      | Number  |
| HIV diagnosis rate             | Rate of HIV diagnoses per 100,000 population                                                   | Number  |
| Concurrent diagnoses           | Number of HIV diagnoses with a concurrent AIDS diagnosis within 31 days                        | Number  |
| % linked to care within 3 months | Proportion of new HIV diagnoses with a viral load or CD4 test within 3 months of diagnosis    | Number  |
| AIDS diagnoses                 | Number of AIDS diagnoses for individuals 13 years or older                                     | Number  |
| AIDS diagnosis rate            | Rate of AIDS diagnoses per 100,000 population                                                  | Number  |
| PLWDHI prevalence              | Estimated number of people living with diagnosed HIV infection per 100 population              | Number  |
| % viral suppression            | Proportion of people living with diagnosed HIV infection with viral load ≤200 copies/mL        | Number  |
| Deaths                         | Number of deaths from any cause among people with HIV/AIDS 13 years or older                   | Number  |
| Death rate                     | Deaths per 1,000 mid-year people living with HIV/AIDS                                         | Number  |
| HIV-related death rate         | Death rate for those assigned an HIV-related cause of death                                    | Number  |
| Non-HIV-related death rate     | Death rate for those assigned a non-HIV-related cause of death                                 | Number  |

======


| Column Name                     | Description                                                                                                   | Type   | Classification   | Justification                                                                                      |
|:--------------------------------|:--------------------------------------------------------------------------------------------------------------|:-------|:-----------------|:---------------------------------------------------------------------------------------------------|
| Year                            | Calendar year of the report                                                                                   | Text   | Temporal         | Year is a temporal marker important for trend analysis and tracking changes over time.              |
| Borough                         | Borough of residence at different stages of HIV/AIDS (diagnosis, treatment, death)                            | Text   | Categorical      | Residence location can be critical for geographical and regional analysis.                         |
| UHF                             | United Hospital Fund neighborhood at different stages of HIV/AIDS                                             | Text   | Categorical      | More granular than borough, provides insight into neighborhood-level health outcomes.              |
| Gender                          | Gender of the individual, including transgender categories                                                    | Text   | Categorical      | Gender is a significant variable in health outcomes and access to care.                            |
| Age                             | Age at different stages of HIV/AIDS                                                                           | Text   | Numerical        | Age is a continuous variable that affects health status and treatment response.                    |
| Race                            | Race/ethnicity of the individual                                                                              | Text   | Categorical      | Racial demographics are essential for understanding disparities in healthcare.                      |
| HIV diagnoses                   | Number of HIV diagnoses for individuals 13 years or older                                                     | Number | Numerical        | Directly quantifies the HIV epidemic's impact; a key variable for public health monitoring.        |
| HIV diagnosis rate              | Rate of HIV diagnoses per 100,000 population                                                                  | Number | Numerical        | Allows for comparisons across populations of different sizes.                                      |
| Concurrent diagnoses            | Number of HIV diagnoses with a concurrent AIDS diagnosis within 31 days                                        | Number | Numerical        | Concurrent diagnoses indicate the late stage of detection, affecting treatment and prognosis.      |
| % linked to care within 3 months | Proportion of new HIV diagnoses with a viral load or CD4 test within 3 months of diagnosis                   | Number | Numerical        | A measure of the healthcare system's efficiency in initiating treatment.                           |
| AIDS diagnoses                  | Number of AIDS diagnoses for individuals 13 years or older                                                    | Number | Numerical        | Represents the progression of HIV infection, crucial for evaluating disease management.             |
| AIDS diagnosis rate             | Rate of AIDS diagnoses per 100,000 population                                                                 | Number | Numerical        | Provides an adjusted measure for population comparisons.                                           |
| PLWDHI prevalence               | Estimated number of people living with diagnosed HIV infection per 100 population                             | Number | Numerical        | Prevalence is key to understanding the burden of disease on a population.                          |
| % viral suppression             | Proportion of people living with diagnosed HIV infection with viral load ≤200 copies/mL                       | Number | Numerical        | Indicates the success of treatment regimens and the potential for disease transmission.             |
| Deaths                          | Number of deaths from any cause among people with HIV/AIDS 13 years or older                                  | Number | Numerical        | Mortality rates are vital for assessing overall health outcomes.                                   |
| Death rate                      | Deaths per 1,000 mid-year people living with HIV/AIDS                                                         | Number | Numerical        | Adjusted mortality rate provides a standard for comparison across different population sizes.      |
| HIV-related death rate          | Death rate for those assigned an HIV-related cause of death                                                   | Number | Numerical        | Focuses on the mortality specifically attributable to HIV, important for disease management.       |
| Non-HIV-related death rate      | Death rate for those assigned a non-HIV-related cause of death                                                | Number | Numerical        | Highlights other health risks and comorbidities among the HIV-positive population.                 |







====



## Potential Target Variables

### Target Variable: HIV diagnoses

| Reasoning for Choice | Research Questions |
|----------------------|--------------------|
| Predicting the number of HIV diagnoses can help identify trends and evaluate the effectiveness of prevention efforts. | 1. How does the rate of HIV diagnoses correlate with different demographics such as age, borough, and race? |
|                      | 2. Can we predict future HIV diagnoses based on historical trends and demographic data? |
|                      | 3. What factors are most strongly associated with higher rates of HIV diagnoses in NYC? |
|                      | 4. How do social determinants of health like neighborhood or borough influence HIV diagnoses rates? |
|                      | 5. Can we identify patterns in the time of year when HIV diagnoses rates increase or decrease? |

### Target Variable: % Viral Suppression

| Reasoning for Choice | Research Questions |
|----------------------|--------------------|
| Understanding factors that lead to successful viral suppression can inform treatment plans and resource allocation. | 1. Which demographics have the highest rate of viral suppression in NYC, and why might that be? |
|                      | 2. Are there any significant changes over time in viral suppression rates among different boroughs? |
|                      | 3. Does the United Hospital Fund neighborhood relate to the likelihood of achieving viral suppression? |
|                      | 4. How do age and gender impact the rates of viral suppression among those diagnosed with HIV? |
|                      | 5. Can we use machine learning to predict the proportion of individuals likely to achieve viral suppression? |

## Approach

- Data acquisition from the NYC Open Data portal using direct download links.
- Preprocessing to handle missing values, anomalies, and data suppression indicated by '99999' values.
- Exploratory Data Analysis (EDA) to gain insights into the data distribution and identify potential predictive variables.
- Feature engineering to create new variables that might better capture the relationships in the data.
- Model selection will include:
  - Logistic Regression for baseline performance.
  - XG Boost for capturing non-linear relationships and feature importance ranking.
  - Neural Networks for modeling complex interactions between features.
- Model evaluation based on accuracy, AUC-ROC, F1 score, and precision-recall for classification tasks.
- Ensemble modeling to combine the predictions from the individual models and assess if performance improves.
- Visualization of results using plots such as ROC curves, precision-recall curves, and feature importance.
- Validation of findings against current literature and expert consultation.


## Approach

- **Data Collection**: Access and download the dataset in CSV format from the NYC Open Data portal.
- **Data Cleaning**: Handle missing, anomalous, and suppressed values, ensuring data quality.
- **Exploratory Data Analysis (EDA)**: Perform EDA to understand distributions and identify relationships.
- **Feature Engineering**: Develop new features that could improve model performance.
- **Model Building**:
  - **Logistic Regression**: To establish a baseline for model comparison.
  - **XG Boost Model**: Due to its powerful capability for classification problems and feature importance.
  - **Neural Network Model**: To capture complex, nonlinear relationships in the data.
- **Model Evaluation**: Use metrics like accuracy, precision, recall, F1 score, and AUC-ROC for evaluation.
- **Ensemble Model**: Combine individual models using techniques like stacking to improve predictions.
- **Visualization**: Create visualizations to present findings and model performance.
- **Validation**: Cross-reference findings with existing research and expert opinions.
- **Pandas Profiling**: Generate detailed reports for initial data understanding.



The project proposal laid out above is designed to be data-driven, leveraging a rich dataset from a credible source to address pressing public health issues regarding HIV/AIDS. The proposed approach, including the machine learning techniques and the ensemble model, is aimed at providing a comprehensive analysis while acknowledging the complexity of the subject matter.


![image](https://github.com/user-attachments/assets/9eaca14f-e3b9-460f-849b-ae28db45e5d5)

![image](https://github.com/user-attachments/assets/4e4493ab-1398-4763-932d-1f163befb0ee)

![image](https://github.com/user-attachments/assets/ddbb2ccc-8499-4060-9821-eddb88729393)

![image](https://github.com/user-attachments/assets/fe7630dd-2f0c-44f6-92cf-415a093ea10f)





