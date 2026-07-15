# Customer Feedback Analysis and AI-Powered Apology Email Generator

##  Project Overview

This project analyzes customer reviews from the Amazon Fine Food Reviews dataset using Python and Pandas. It performs data cleaning, identifies customer complaints using rule-based filtering, and automatically generates personalized apology emails using Google's Gemini Generative AI API.

The objective of this project is to demonstrate how data preprocessing and Generative AI can be combined to improve customer support by responding to negative customer feedback efficiently.

---

## Objectives

- Load and analyze customer review data.
- Clean and preprocess textual data.
- Handle missing values.
- Detect critical customer complaints.
- Generate AI-powered personalized apology emails.
- Export the final results for business use.

---

##  Dataset

**Dataset:** Amazon Fine Food Reviews Dataset

The following columns were used in this project:

 Column  Description 

 ProfileName , Customer's profile name ,
Score , Rating given by the customer (1–5) ,
Summary , Short summary of the review ,
Text , Detailed customer review 

---

## Technologies Used

- Python
- Pandas
- Regular Expressions (re)
- Jupyter Notebook
- Google Gemini API
- Generative AI

---

## Project Workflow

### Step 1 – Import Libraries

Required libraries were imported.

```python
import pandas as pd
import re
import google.generativeai as genai
```

---

### Step 2 – Load Dataset

The customer review dataset was loaded into a Pandas DataFrame.

---

### Step 3 – Data Exploration

Performed basic exploratory analysis using:

- `head()`
- `tail()`
- `shape`
- `columns`
- `info()`
- `describe()`
- `isnull().sum()`

---

### Step 4 – Data Cleaning

The dataset was cleaned by:

- Selecting required columns
- Handling missing values
- Filling missing customer names
- Filling missing summaries
- Converting review text to lowercase
- Removing punctuation and special characters

Example:

```python
reviews_df["Text"] = reviews_df["Text"].str.lower()
```

Special characters were removed using Regular Expressions.

---

### Step 5 – Rule-Based Complaint Detection

Critical reviews were filtered using:

```python
Score <= 2
```

A list of complaint keywords was created:

```python
complaint_keywords = [
    "bad",
    "terrible",
    "worst",
    "poor",
    "broken",
    "defective",
    "refund",
    "damaged",
    "late",
    "missing"
]
```

A custom function (`has_complaint`) checked whether a review contained any complaint keywords.

Reviews containing these keywords were marked as:

- True → Complaint
- False → No Complaint

---

### Step 6 – Select Top Complaint Reviews

Only complaint reviews were selected.

The first three complaint reviews were used for AI-generated responses.

---

### Step 7 – AI-Powered Apology Email Generation

Google Gemini API was integrated to generate professional apology emails.

Prompt Example:

```text
You are a Customer Support Agent.

Customer Review:
{review}

Write a professional and empathetic apology email addressing the customer's complaint.
```

Gemini generated personalized responses based on each review.

---

### Step 8 – Save Results

Generated apology emails were added to a new DataFrame column.

The final output was exported as:

```
Generated_Apology_Emails.xlsx
```

---

# 📊 Project Structure

```
Customer-Feedback-Analysis/
│
├── Customer_Feedback_Analysis.ipynb
├── Generated_Apology_Emails.xlsx
├── README.md
└── Reviews.xlsx (optional)
```

---

# 📈 Output

The final output includes:

- Customer Name
- Review
- Complaint Status
- AI-Generated Apology Email

Example:

| ProfileName | Complaint | Apology_Email |
|-------------|-----------|---------------|
| John | True | Dear John, We sincerely apologize... |

---

# ▶️ How to Run

## 1. Clone the repository

```bash
git clone https://github.com/yourusername/Customer-Feedback-Analysis.git
```

## 2. Install dependencies

```bash
pip install pandas google-generativeai openpyxl
```

## 3. Open Jupyter Notebook

Open:

```
Customer_Feedback_Analysis.ipynb
```

## 4. Configure Gemini API

Replace:

```python
genai.configure(api_key="YOUR_API_KEY")
```

with your own Gemini API key.

---

# 📸 Screenshots

You may add screenshots of:

- Data Exploration
- Complaint Detection
- AI-generated Email
- Final Output

to improve the GitHub project presentation.

---

# Future Improvements

- Sentiment Analysis using NLP
- Automatic Email Sending using SMTP
- Streamlit Web Application
- Dashboard Visualization using Power BI
- Customer Priority Classification
- Integration with CRM systems

---

# Learning Outcomes

This project demonstrates practical experience in:

- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Rule-Based Text Classification
- Prompt Engineering
- Generative AI Integration
- Python Programming
- Pandas
- API Integration
- Business Problem Solving

---

# Author

**Yash Bhola**

B.Tech – Computer Science Engineering (CSE)

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile

---

# 📄 License

This project is created for educational and internship learning purposes.
