---
# Heart Disease Prediction Using Random Forest Classifier

## Introduction

This project aims to predict heart disease risk using a **Random Forest Classifier**. The model analyzes patient health metrics such as **age, cholesterol levels, and maximum heart rate achieved** to determine the likelihood of heart disease. The application is deployed on **Streamlit Cloud** and **Render** for easy access.



## Table of Contents
- [Project Structure](#project-structure)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Evaluation](#model-evaluation)
- [Deployment](#deployment)
- [Conclusion](#conclusion)

## Project Structure
```
|-- 📂 Heart-Disease-Prediction
    |-- 📄 heartdieaseup.py           # Main Streamlit app for cloud deployment
    |-- 📄 sk7_random_forest.ipynb    # Jupyter notebook for training and evaluation
    |-- 📄 README.md                  # Documentation
    |-- 📄 heart.csv                   # UCI Heart Disease Dataset
    |-- 📂 models                      # Trained models (if applicable)
    |-- 📂 images                      # Visualizations (Confusion Matrix, Feature Importance)
```

## Dataset
Download datat from.    https://archive.ics.uci.edu/dataset/45/heart+disease
The dataset used is the **UCI Heart Disease Dataset**, which contains 14 features:

- **age**: Age of the patient
- **sex**: Gender of the patient
- **cp**: Chest pain type
- **trestbps**: Resting blood pressure
- **chol**: Serum cholesterol level
- **fbs**: Fasting blood sugar
- **restecg**: Resting electrocardiographic results
- **thalach**: Maximum heart rate achieved
- **exang**: Exercise-induced angina
- **oldpeak**: ST depression induced by exercise
- **slope**: Slope of the peak exercise ST segment
- **ca**: Number of major vessels colored by fluoroscopy
- **thal**: Thalassemia
- **target**: 1 = presence of heart disease, 0 = absence of heart disease


## Model Evaluation

The **Random Forest Classifier** was trained and evaluated using various metrics:

- **Confusion Matrix**: Displays True Positives (TP), False Positives (FP), True Negatives (TN), and False Negatives (FN).
- **Accuracy Score**: Measures overall model accuracy.
- **Precision, Recall & F1-Score**: Evaluates classification performance.

### Example Results:
- **Accuracy**: ~99% on the test dataset.
- **Confusion Matrix Visualization:**

```python
from sklearn.metrics import confusion_matrix
import seaborn as sns
import matplotlib.pyplot as plt

cm = confusion_matrix(y_test, y_pred)
plt.figure(figsize=(5,3))
sns.heatmap(cm, annot=True, fmt="d", cmap="Blues", xticklabels=['No Disease', 'Disease'], yticklabels=['No Disease', 'Disease'])
plt.xlabel("Predicted Label")
plt.ylabel("True Label")
plt.title("Confusion Matrix")
plt.show()
```

## Deployment

The application is deployed on **Streamlit Cloud** and **Render** for easy access.

### Deployment Steps
1. **Prepare the App**: Ensure `heartdieaseup.py` contains the Streamlit UI logic.
2. **Push to GitHub**: Ensure all required files are committed.
3. **Deploy to Streamlit Cloud**:
   - Go to [Streamlit Cloud](https://streamlit.io/cloud)
   - Connect your GitHub repository
   - Select `heartdieaseup.py` as the entry point
   - Deploy!
4. **Deploy to Render**:
   - Go to [Render](https://render.com/)
   - Create a new **Web Service**
   - Connect your GitHub repository
   - Select Python as the environment
   - Set the **Start Command** to `streamlit run heartdieaseup.py`
   - Deploy!



