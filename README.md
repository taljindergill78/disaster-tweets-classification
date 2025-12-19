# Disaster Tweets Classification (NLP)

## 📌 Project Overview
This project focuses on identifying whether a tweet is related to a real-world disaster using **Natural Language Processing (NLP)** techniques. The goal is to build a robust text classification pipeline that systematically progresses from exploratory data analysis to baseline modeling and finally to improved models using feature engineering, ensemble techniques, and threshold tuning.

This project demonstrates a systematic NLP modeling workflow focused on evaluation rigor interpretability, and reproducibility—skills directly applicable to real-world ML systems.

---

## 🧠 Problem Statement
Given a tweet’s text, determine whether it refers to a **real disaster event** (`1`) or **not** (`0`).  
The challenge lies in the informal nature of tweets, short text length, noisy language, and context ambiguity.

---

## 📊 Dataset
- **Source:** Kaggle – *Natural Language Processing with Disaster Tweets*
- **Size:** ~7.6K labeled training tweets
- **Target variable:** `target` (0 = non-disaster, 1 = disaster)
- **Features:** tweet text, keyword, location (where available)

> ⚠️ **Note on data availability:**  
> The dataset is **not included in this repository** to keep the repo lightweight and comply with Kaggle’s data usage guidelines.

### 🔽 How to obtain the data
1. Create a Kaggle account  
2. Download the dataset from:  
   👉 https://www.kaggle.com/competitions/nlp-getting-started/data  
3. Place the files in the following structure:
```
data/
├── train.csv
└── test.csv
```

All notebooks assume this directory structure.

---

## 🔍 Exploratory Data Analysis (EDA)
The EDA notebook focuses on:
- Class distribution and imbalance analysis
- Tweet length and token distribution
- Keyword and location sparsity
- Early signals distinguishing disaster vs non-disaster tweets

Notebook:
- `notebooks/01_disaster_tweets_eda.ipynb`

---

## 🏗️ Modeling Approach
The modeling pipeline follows a **progressive and explainable approach**:

### Feature Engineering
- Word-level **TF-IDF** features
- Character-level **TF-IDF** features
- Basic text normalization
- Optional metadata features (where applicable)

### Models Evaluated
- Logistic Regression  
- Linear Support Vector Machines (SVM)  
- Complement Naive Bayes  
- Ensemble combinations of linear models  

### Optimization Techniques
- Stratified cross-validation
- Holdout validation split
- Probability threshold tuning for F1-score optimization
- Comparative evaluation of baseline vs improved models

Notebook:
- `notebooks/02_disaster_tweets_modeling_baseline_to_improved.ipynb`

---

## 📈 Results & Evaluation
- Performance evaluated primarily using **F1-score**, suitable for class imbalance
- Iterative improvements over baseline through:
  - Feature augmentation
  - Ensemble learning
  - Threshold calibration
- Final model demonstrates **consistent improvement over baseline models** on the validation set

(Exact metrics and plots are documented inside the notebook and final report.)

---

## 📁 Repository Structure
```
disaster-tweets-classification/
├── data/ # Dataset folder (CSV files not included)
├── notebooks/
│ ├── 01_disaster_tweets_eda.ipynb
│ └── 02_disaster_tweets_modeling_baseline_to_improved.ipynb
├── report/
│ └── final_report.pdf
├── slides/
│ └── checkpoint_2_presentation.pptx
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ▶️ How to Run
1. Clone the repository:
   - git clone https://github.com/<your-username>/disaster-tweets-classification.git
   - cd disaster-tweets-classification
2. Install dependencies:
    - pip install -r requirements.txt
3. Download the dataset (see Dataset section above) and place it in 'data/'
4. Launch Jupyter:
    - jupyter notebook
5. Run notebooks in order:
    - 01_disaster_tweets_eda.ipynb
    - 02_disaster_tweets_modeling_baseline_to_improved.ipynb

---

## 🧪 Reproducibility Notes
- Fixed random seeds where applicable
- Clear separation between EDA and modeling
- Explicit path handling to ensure consistent execution from the notebooks/ directory

---

## 📄 Additional Materials
- Final Report: report/final_report.pdf
- Checkpoint Presentation: slides/checkpoint_2_presentation.pptx

---

## 🛠️ Technologies Used
- Python
- pandas, NumPy
- scikit-learn
- TF-IDF (word & character level)
- Matplotlib / Seaborn

---

## 📬 Contact
If you have questions or suggestions, feel free to reach out via GitHub.