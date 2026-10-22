# Ride-Hailing Customer Feedback Intelligence & Automated Response

## Project Overview

This project analyzes customer reviews of **Ola and Uber** from the
Google Play Store to identify critical negative feedback, understand
common complaint patterns, and generate personalized customer support
response drafts.

The project was completed as part of the **Imarticus Learning Data
Science Internship Assessment -- Python Foundations & Gen AI**.

The analysis uses **Python and Pandas** for data cleaning and rule-based
analysis. No Machine Learning model is used for identifying critical
reviews.

## Objectives

-   Clean and prepare customer review data.
-   Identify critical reviews using a rule-based approach.
-   Compare critical-review rates between Ola and Uber.
-   Identify common complaint keywords and categories.
-   Select three detailed critical reviews.
-   Generate personalized and empathetic customer-support email drafts
    using Generative AI.

## Dataset

The project uses the **Ola vs Uber Play Store Reviews** dataset from
Kaggle.

Dataset:
`https://www.kaggle.com/datasets/khushipitroda/ola-vs-uber-play-store-reviews`

The dataset contains separate review data for Ola and Uber, including
ratings and review text.

After combining the two datasets, the project works with approximately
**1.4 million reviews** before the final text-cleaning steps.

## Data Cleaning

The following preprocessing steps were performed:

1.  Combined the Ola and Uber datasets.
2.  Added an `app` column to identify the application.
3.  Removed unnecessary columns such as `review_title` and `user_name`.
4.  Removed rows with missing review descriptions.
5.  Filled missing `thumbs_up` values with `0`.
6.  Converted review text to lowercase.
7.  Removed apostrophes and special characters.
8.  Removed extra spaces.
9.  Removed reviews that became empty after cleaning.
10. Corrected the `laguage_code` column name to `language_code`.
11. Converted `review_date` into datetime format.
12. Created a `developer_responded` flag based on whether a developer
    response was available.

Final cleaned dataset: **1,406,692 reviews**.

## Rule-Based Critical Review Identification

The assessment specifically requires critical reviews to be identified
without Machine Learning.

The project uses the following rule:

-   **1-star and 2-star reviews = Critical**
-   **3, 4 and 5-star reviews = Non-critical**

This resulted in **509,160 critical reviews**.

The critical reviews were then analyzed to understand the major
complaint patterns.

## Key Insights

### Critical Reviews by App

  App      Critical Reviews   Critical Review Rate
  ------ ------------------ ----------------------
  Ola               187,871                 53.01%
  Uber              321,289                 30.53%

Based on this dataset, Ola has a higher proportion of critical reviews
than Uber.

### Common Complaint Areas

The critical reviews were analyzed using keyword-based rules.

The main complaint categories identified were:

-   **Payment and Charges**
-   **Cancellation**
-   **Customer Support**
-   **Driver Behaviour**

The category analysis is based on keyword mentions. A single review can
contain keywords belonging to more than one category.

## Generative AI Response

Three detailed 1-star critical reviews were selected from the filtered
dataset.

Google Gemini was used to generate short, personalized and empathetic
customer-support response drafts.

The prompt instructs the model to:

-   Address the specific complaint.
-   Acknowledge the customer's frustration.
-   Keep the response professional and concise.
-   Avoid inventing facts.
-   Avoid making unsupported promises about refunds, compensation,
    investigations or escalations.
-   Avoid blaming the customer.

The three generated responses are included directly in the Jupyter
Notebook as required by the assessment.

## Technologies Used

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Collections / Counter
-   Google Gemini API
-   Jupyter Notebook

## Project Structure

``` text
Customer-Feedback-Analysis/
│
├── Customer_Feedback_Analysis_Final.ipynb
└── README.md
```

## How to Run

1.  Download or clone the project.
2.  Open `Customer_Feedback_Analysis_Final.ipynb` in Jupyter Notebook or
    JupyterLab.
3.  Run the notebook cells in order.
4.  For the Generative AI section, provide a valid Gemini API key when
    prompted.
5.  Do not hard-code or commit the API key to GitHub.

## Important Note About the API Key

The Gemini API key should be entered securely at runtime.

Do **not** write the API key directly inside the notebook code or upload
it to GitHub.

## Limitations

-   Critical reviews are identified using rating-based rules rather than
    Machine Learning.
-   Complaint categories are based on keyword matching, so one review
    may belong to multiple categories.
-   The quality of AI-generated responses depends on the selected model
    and API availability.
-   The project focuses on the requirements of the internship assessment
    rather than production deployment.

## Conclusion

This project demonstrates an end-to-end customer feedback analysis
workflow using Python, Pandas, rule-based logic and Generative AI. It
shows how large-scale review data can be cleaned, filtered, analyzed for
complaint patterns, and used to create personalized customer-support
response drafts.

