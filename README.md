# 🎓 Student Academic Risk Intelligence System

An interactive student performance analysis system that analyzes academic data, identifies students who may be at academic risk, and provides insights through a Streamlit dashboard and FastAPI backend.

## 📌 Project Overview

The Student Academic Risk Intelligence System is designed to analyze student academic performance using data such as:

- Previous grades
- Final grade
- Study time
- Absences
- Previous failures
- Internet access
- Parental education
- Academic support
- Alcohol consumption

The system transforms the raw student dataset into meaningful academic indicators and presents the results through interactive visualizations and APIs.

---

## 🎯 Objectives

The main objectives of this project are to:

- Analyze student academic performance.
- Identify students who are at risk of failing.
- Identify dropout students.
- Calculate overall class performance.
- Analyze the relationship between study time and final grades.
- Analyze the relationship between internet access and final grades.
- Provide a simple academic result prediction API.
- Present student insights through an interactive dashboard.

---

## ✨ Features

### 📊 Student Performance Dashboard

The Streamlit dashboard provides:

- Total number of students
- Class average final grade (G3)
- Overall pass rate
- At-risk student count
- Interactive Plotly charts
- Student analysis table
- Result-based filtering
- At-risk student analysis

### 📈 Data Visualizations

The dashboard includes interactive visualizations such as:

1. Study Time vs Final Grade
2. Average G3 by Internet Access
3. Average G3 by Study Time

### ⚠️ Academic Risk Analysis

The system identifies students based on their final grade:

- **G3 = 0** → Dropout
- **G3 = 1–9** → Fail / At Risk
- **G3 = 10–20** → Pass

An academic risk score is also calculated using factors such as:

- Previous failures
- Absences
- Alcohol consumption
- Study time

### 🚀 FastAPI Backend

The project provides REST API endpoints for accessing student analysis results.

Available endpoints:

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | API information |
| GET | `/summary` | Overall student performance summary |
| GET | `/at-risk` | List of students at academic risk |
| GET | `/top-students` | Top-performing students |
| GET | `/by-studytime` | Average G3 grouped by study time |
| POST | `/predict-result` | Predict student academic result |

FastAPI also provides interactive API documentation through Swagger UI at:

```text
http://localhost:8000/docs
```

---

## 🧠 Feature Engineering

The project derives additional features from the original dataset, including:

### Result

Student result is classified using G3:

```text
G3 = 0       → Dropout
G3 = 1–9     → Fail
G3 = 10–20   → Pass
```

### Percentage

Final grade is converted into percentage:

```text
Percentage = (G3 / 20) × 100
```

### Average Alcohol Consumption

```text
Average Alcohol = (Dalc + Walc) / 2
```

### Parent Education Average

```text
Parent Education Average = (Medu + Fedu) / 2
```

### Grade Trend

```text
Grade Trend = G3 - G1
```

### Total Support

The system counts academic/family support from:

- School support
- Family support
- Paid classes

### Academic Risk Score

The risk score combines:

- Previous failures
- Absences
- Alcohol consumption
- Study time

Higher risk factors increase the student's academic risk score.

---

## 📂 Dataset

The project uses the Student Performance dataset.

The primary dataset used by the dashboard is:

```text
data/Maths.csv
```

A Portuguese dataset was also tested during analysis:

```text
data/Portuguese.csv
```

The two datasets were compared to observe differences in student performance across subjects.

---

## 🔍 Maths vs Portuguese Dataset

The same analysis pipeline was tested on both datasets.

| Metric | Maths | Portuguese |
|---|---:|---:|
| Total Students | 397 | 649 |
| Average G3 | 11.51 | 12.19 |
| Pass Rate | 74.02% | 86.59% |
| At-Risk Students | 93 | 85 |
| Dropout Students | 39 | 15 |

### Observations

The Portuguese dataset contains more students than the Maths dataset. Portuguese students also have a higher average final grade and pass rate.

When considering dataset size, the proportion of at-risk and dropout students is lower in the Portuguese dataset than in the Maths dataset.

This demonstrates that the same analytical pipeline can reveal different academic performance patterns across subjects.

---

## 🛠️ Technologies Used

### Programming

- Python

### Data Analysis

- Pandas
- NumPy

### Data Visualization

- Plotly
- Matplotlib

### Dashboard

- Streamlit

### API

- FastAPI
- Pydantic
- Uvicorn

### Development

- Visual Studio Code
- Git
- GitHub

---

## 📁 Project Structure

```text
student analysis/
│
├── app.py
├── main.py
├── requirements.txt
├── README.md
│
├── data/
│   ├── Maths.csv
│   └── Portuguese.csv
│
├── src/
│   ├── analysis.py
│   └── data_preprocessing.py
│
└── output/
    ├── avg_g3_by_studytime.png
    └── pass_fail_dropout_pie.png
```

---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/sadwi18/student_analysis.git
```

### 2. Navigate to the project directory

```bash
cd student_analysis
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit dashboard

```bash
python -m streamlit run app.py
```

The dashboard will be available at:

```text
http://localhost:8501
```

### 5. Run the FastAPI backend

```bash
python main.py
```

The API will be available at:

```text
http://localhost:8000
```

Swagger API documentation:

```text
http://localhost:8000/docs
```

---

## 🌐 Live Demo

### Streamlit Dashboard

https://studentanalysis-5vju4isivuadkw4us9eegi.streamlit.app/

### GitHub Repository

https://github.com/sadwi18/student_analysis

---

## 📊 Sample Insights

The analysis helps answer questions such as:

- How does study time relate to final grades?
- Do students with internet access have different average grades?
- How many students are at academic risk?
- How many students are classified as dropouts?
- Which students have the highest final grades?
- How do Maths and Portuguese student performance differ?

---

## 🚀 Future Improvements

Possible future improvements include:

- Machine learning-based academic risk prediction
- Early-warning notification system
- Student performance forecasting
- Personalized study recommendations
- More advanced feature engineering
- Interactive filters for multiple student attributes
- Database integration
- Authentication and role-based access
- Deployment of the FastAPI backend
- Automated model evaluation and monitoring

---

## 👩‍💻 Author

**Satya Sadwika**

GitHub: https://github.com/sadwi18

---

## 📜 License

This project is developed for educational and academic purposes.