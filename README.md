
### **1. EDA: Trend Indicators**

#### **Correlation Coefficient (`data.corr()`)**
- **Range**: [-1, 1]
  - **-1**: Perfect negative correlation (as one variable increases, the other decreases).
  - **0**: No correlation (variables are independent).
  - **1**: Perfect positive correlation (both variables increase together).
  
  **Example**:  
  A correlation of 0.8 between `Temperature` and `Humidity` indicates a strong positive relationship.

---

#### **Skewness (`data.skew()`)**
- **Range**: Any real number.
  - **0**: Perfectly symmetrical distribution.
  - **> 0**: Positively skewed (right tail longer).
  - **< 0**: Negatively skewed (left tail longer).

  **Indicator**:  
  For normal distributions, skewness should be close to 0. Skewed data may need transformation (e.g., log or sqrt).

---

#### **Outliers (IQR Method)**
- **Range for Outlier Detection**:
  - Lower Bound: (Q1 - 1.5) * IQR 
  - Upper Bound: (Q3 + 1.5) * IQR
  - Points outside these bounds are considered outliers.
  
  **Interpretation**:  
  Removing or handling outliers depends on the context of the analysis.

---

### **2. KNN: Classification Metrics**

#### **Confusion Matrix Metrics**
- **Accuracy**:  (TP + TN) / Total Prediction
  - **Range**: [0, 1]
  - **Indicator**: Closer to 1 indicates better model performance.
  
- **Precision**: TP / (TP + FP)
  - **Range**: [0, 1]
  - **Indicator**: High precision minimizes false positives. Useful when FP is costly.

- **Recall (Sensitivity)**: TP / (TP + FN)
  - **Range**: [0, 1]
  - **Indicator**: High recall minimizes false negatives. Useful when FN is costly.

- **F1-Score**: ``(2*Precision*Recall)/ (Precision + Recall)``
  - **Range**: [0, 1]
  - **Indicator**: Harmonic mean of precision and recall. Best for imbalanced datasets.

---

#### **K Value in KNN**
- **Range**: [1, \( n-1 \)], where \( n \) is the number of training samples.
  - Low \( k \): High variance, low bias (overfitting risk).
  - High \( k \): Low variance, high bias (underfitting risk).
  
  **Optimal K**: Found using cross-validation.

---

#### **ROC-AUC Score**
- **Range**: [0, 1]
  - **< 0.5**: Worse than random guessing.
  - **0.5**: Random guessing.
  - **> 0.5**: Better than random guessing.
  - **1**: Perfect model.

---

### **3. K-Means: Clustering Metrics**

#### **Inertia (Within-Cluster Sum of Squares)**
- **Range**: [0, ∞)
  - Lower values indicate tighter clusters.
  - Stops decreasing significantly after the "elbow point."

---

#### **Silhouette Score**
- **Range**: [-1, 1]
  - **-1**: Poor clustering (clusters overlap).
  - **0**: Overlapping clusters or no structure.
  - **1**: Perfect separation between clusters.
  
  **Indicator**: Scores closer to 1 are ideal for well-separated clusters.

---

### **4. General Indicators**

#### **Normalization/Scaling**
- Post-normalization values typically lie in the range:
  - **StandardScaler**: Mean = 0, Std Dev = 1.
  - **MinMaxScaler**: [0, 1].

#### **K-Means Cluster Centers**
- Values depend on the feature range (after scaling). These represent the centroid of each cluster.

#### **Prediction Accuracy**
- **Range**: [0, 1]
  - Indicates how many predictions were correct compared to the total predictions.
