# Machine Unlearning

## Objective
The goal of this repository is to provide a solution for the NeurIPS 2023 - Machine Unlearning competition. The challenge involves developing an algorithm capable of "unlearning" specific data points from a trained machine learning model, particularly an age predictor model based on face images. The solution aims to ensure that the influence of the forgotten data is removed efficiently without retraining the model from scratch, while also preserving the overall accuracy and performance on the remaining data.

## Background

Machine unlearning is a growing subfield of machine learning that focuses on the removal of specific data from a trained model. This need arises for various reasons, such as protecting user privacy, complying with legal requests for data deletion, or correcting training datasets. Traditional approaches to this problem involve retraining the model without the data to be forgotten, which can be computationally expensive and time-consuming. The objective of this competition, and hence our code, is to refine and develop more efficient unlearning processes.
![MachineUnlearningExample](Images/example.png)


## What Does the Code Do?

The code in this repository:

1. **Loads a Pre-trained Model**: The initial step involves loading a pre-trained age prediction model that has been trained on a dataset of face images.

2. **Identifies Forget Set**: We segregate the specific subset of data (the forget set) that needs to be unlearned from the model according to the provided guidelines.

3. **Applies Unlearning Algorithm**: The core of the code applies a novel unlearning algorithm that efficiently removes the influence of the forget set from the model's weights.

4. **Ensures Random Variation**: To accurately capture the distribution required for unlearning, the code introduces randomness in the data processing, such as shuffling the data in each epoch.

5. **Evaluates Model Performance**: After the unlearning process, the code evaluates the model to ensure that the accuracy remains high for the retained data while confirming that the forget set's influence is effectively removed.

6. **Generates New Model Checkpoints**: Post unlearning, the model checkpoints are saved, ensuring that the transformed model retains the required utility without the influence of the forgotten data.

