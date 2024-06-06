# DNA-Promoter-Classification-CNN

![image](https://github.com/shantanufuke/DNA-Promoter-Classification-CNN/assets/104629474/8db549ad-952d-492f-bdfd-9495bdde987c)

## Indrodution
In this project, we have explore the world of bioinformatics by using deep learning. A promoter is a short region of DNA (100–1,000 bp) where transcription of a gene by RNA polymerase begins. It is typically located directly upstream or at the 5′ end of the transcription initiation site. DNA promoters has been proven to be the primary cause of many human diseases, especially diabetes, cancer, or Huntington's disease. Therefore, classifying promoters has become an interesting problem and it has attracted the attention of a lot of researchers in the bioinformatics field. We will try to classify this using Machine Learning and Neural Networks.

## Data Processing
We start with two datasets: one containing promoter sequences and the other containing non-promoter sequences. The datasets are processed to remove unnecessary information and encode the DNA sequences into a format suitable for training the CNN.

## Model Creation
A Convolutional Neural Network (CNN) is created using Keras. The model architecture consists of a series of layers designed to capture and learn from DNA sequence patterns: an initial Conv1D layer with 128 filters and 
a kernel size of 3 using ReLU activation, followed by a MaxPooling1D layer with a pool size of 2, and a Dropout layer with a rate of 0.4. This is followed by another Conv1D layer with 64 filters, a kernel size of 2, 
ReLU activation, and the same padding, again followed by MaxPooling1D and Dropout layers with the same configurations. A third Conv1D layer with 32 filters and a kernel size of 2 using ReLU activation and the same padding 
is added, followed by MaxPooling1D and Dropout layers. The sequence is then flattened, followed by dense layers with 128, 64, 32, and 16 units, all using ReLU activation, with the final dense layer incorporating L2 regularization. The output layer consists of 2 units with sigmoid activation for binary classification.

## Model Training
The model is compiled with the Adam optimizer and binary cross-entropy loss function. It is trained on the training dataset with early stopping and model checkpoint callbacks to prevent overfitting and save the best model.

## Model Evaluation
The model is evaluated on the test set to determine its accuracy and loss. Additional metrics such as the classification report, confusion matrix, and ROC curve are used to provide a detailed analysis of the model's performance.

## Evaluation Metrics
Test Loss: Measures the model's error on the test data.
Test Accuracy: Measures the model's accuracy on the test data.
Classification Report: Precision, recall, F1-score for each class.
Confusion Matrix: Visual representation of actual vs. predicted classifications.
ROC Curve and AUC: Plots the true positive rate against the false positive rate and calculates the area under the curve.
