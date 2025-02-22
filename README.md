# Captcha-Recognizer

## Model description 
A OCR style model is being implemented for captcha recognition as OCR is one of the best models there for character recognition and gives one of the best accuracy and can be stated as a SOTA method for these use cases. The model containes a convulutional RNN and LSTM.

## Data Preprocessing and model training
The data contained 6000 training sample. I used them to split it in train and test data for model training and evaluation. I forgot to use val data for model evaluation and found it easy to evaluate it like this as of less training due to resource constraints. I also used CTC loss for better model training and best accuracy. I used accuracy metric to evaluate present in torch functional. The accuracy on the above test set came out to be 96.7% for perfect hit which is quite good keeping in mind that model was trained upto 18 epochs due to only cpu training and resource unavailability.
Epoch=18, Train Loss=0.03182249845091806, Test Loss=0.020952331940643488 Accuracy=0.9733333333333334

## Problem faced and solution
The main problem was to design the model and have ctc loss integrated in it for better performance. To solve this i used some search references that helped me to design the model properly and train it accordingly.

## Model training details
The model was trained on colab with a cpu as t4 gpu was slower and not effective. 
The model is coded in model.py and training and eval script is in train.py 
Config file contains the details of the files used and image dimensions.
A 18 epoch trained pth file is also included for evaluation using eval_fn present in engine.py file.
The dataloader is present in dataset.py file to access the data properly and preprocess it.
The data was not cleaned much as this OCR model training is capable of handling this amount of noise and data is already proper seeing the images present in it.

## Model setup 
Use requirement.txt to install required libraries and train.py file to train and evaluate the model.
