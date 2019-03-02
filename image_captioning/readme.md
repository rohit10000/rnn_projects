# Image description generation using LSTM and DNN

## Overview

This project completely illustrates the usage of sequential model and deep convolutional neural networks. In this project, we have trained a sequential model such that when given an image feature vector as input to the model, it gives the best suited caption relating to that image. 

We have divided the complete process into 6 parts, they are:
- Dataset Selection
- Prepare Photo Data
- Prepare Text Data
- Develop and train a Deep Learning Model
- Evaluate Model
- Generate captions given an image

The complete idea of this project is to first pass the image to a Deep CNN VGG16 model pretrained on imagenet dataset and get a featured vector corresponding to each image. We do so with the help of transfer learning where we discard the softmax layer from the original VGG16 model and insteads gives an output vector of 4096 values that completely represents the image.

Then, the featured image vector is passed through a dense map of neural network which is then converted to a vector of 128 values. Then, the featured vector serves as a previous activation and memory value for the first LSTM cell.

## Helper files for Preprocessing of Data

The file named extract_features.py consists of the code for feature extraction and saving it to the filenamed features.pkl and all the image names in image_names.txt. Then we split the image feature into train, test and dev sets and save them in the train_features.pkl, dev_features.pkl and test_features.pkl respectively.

The dataset contains multiple descriptions for each photograph and the text of the descriptions required some minimal cleaning. By using the text_preprocessing.py. We have cleaned the text data and stored the corresponding train, dev and test descriptiontext to train_descriptions.txt, dev_descriptions.txt and test_descriptions.txt respectively.
