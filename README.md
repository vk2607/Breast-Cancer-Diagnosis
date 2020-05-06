# Breast Cancer Diagnosis

## Dataset
Dataset is publicly available on (https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)) and is created
by  Dr. William H. Wolberg, physician at the University Of Wisconsin Hospital at Madison, Wisconsin, USA. 

### Atribute Information

1) ID number
2) Diagnosis (M = malignant, B = benign)

Ten real-valued features are computed for each cell nucleus:

1) radius (mean of distances from center to points on the perimeter)
2) texture (standard deviation of gray-scale values)
3) perimeter
4) area
5) smoothness (local variation in radius lengths)
6) compactness (perimeter^2 / area - 1.0)
7) concavity (severity of concave portions of the contour)
8) concave points (number of concave portions of the contour)
9) symmetry
10) fractal dimension ("coastline approximation" - 1)


## Objective

The objective of this analysis is to shortlist the most important features in predicting benign or malignant cancer. It also
aims to find the co-related features.The final and main objective is to predict whether the cancer is benign or malignant. 

## Approach

### Data Exploration
Examine head(). Find if there is any missing data.Use feature scaling to bring all values in range of -1 to 1. Using seaborn and matplot library visualize all the features. With the help of violin plots, swarm plots and heatmap find
out the co-related features. 

### Drop the columns
Examine co-related features with the heatmap of seaborn library and drop the co-related columns where co-relation is equal to 1.

### XGBoost and PCA (Principal Component Analysis)
Firstly, split the dataset in the ration 7:3 for training and testing. We use XGBoost to classify the result into benign and malignant.
We use Univaraite feature selection from sklearn to select top 10 features. With the help of PCA we observe cummulative explained variance vs
number of components. We don't need PCA as there are only 30 columns.

## Accuracy 
The accuracy of the model is 97.6 %.<br>
The precision is 98.1 %  and recall is 96.8%
