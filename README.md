# ToxPLTC


This repository contains code for "**ToxPLTC: Peptide toxicity by integrating pre-trained T5 protein language model and text convolutional neural network.**"



## 1 Description

ToxPLTC is a deep learning framework designed for predicting peptide toxicity. The model employs ProtT5, a Transformer-based protein language model, to pre-train peptide sequences, utilizes the Borderline SMOTE algorithm to address class imbalance in the training set, and incorporates a text convolutional neural network along with fully connected layers for classification. Trained on the training set, the model demonstrates well predictive performance and generalization capability on independent test sets.



## 2 Requirements
Before running, please create a new environment using this command:

```bash
conda create -n toxpltc python=3.9
conda activate toxpltc
```

Next, run the following command to install the required packages:

```bash
cd ToxPLTC
pip install -r requirements.txt --no-cache-dir
```

## 3 Project Structure

*   **`Datasets/`**: Include the three required datasets: `train`, `Indtest 1`, `Indtest 2`.
*   **`Codes/`**: It contains the main codes required for the implementation and experiment of the ToxPLTC model. The functions of the main files are described as follows:
     - `get_ProtT5.py`: Used to extract high-dimensional protein language model features based on ProtT5 from each dataset.
     - `Borderline-SMOTE.py`: For performing Borderline-SMOTE data balancing on the training set 
     - `main.py`: Define the overall framework of the ToxPLTC model.
     - `predict.py`: Load the trained model `Trained ToxPLTC.pt` and perform predictions on two independent test sets based on `ProtT5_Indtest1_features.csv` and `ProtT5_Indtest2_features.csv` respectively.
     - `ROC and PRC.py`: Based on the results of training set cross-validation, plot the model's ROC curve and PRC curve.
     - `visualization.py`: t-SNE distribution results for visualizing feature representations across different layers of the model.
     - `Applicability domain(AD).py`: Applicability domain (AD) analysis for evaluating the reliability of model predictions on samples within the AD in independent test sets.

*   **`requirements.txt`**: Lists all dependencies and their versions for quick environment setup.

## 4 Predict

Using `ProtT5_Indtest1_features.csv`, `ProtT5_Indtest2_features.csv`, and `predict.py` allows you to reproduce the prediction results for the independent test sets in the experiment.
Specifically, `predict.py` calls the model structure defined in `main.py` and loads the trained model parameter file `Trained ToxPLTC.pt`.





