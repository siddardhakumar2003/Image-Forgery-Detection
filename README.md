**Image Forgery Using Convolutional Neural Networks**
-
* Architecture of Feature Vector Generator model:
    -  
    * Model is nine layered where each layer parameters are given below :
    - 1st layer 
        * input size: 128x128x3 
        * output size: 124x124x30
        * stride : 1
        * padding : 0
        * kernel size : 5x5
    - 2nd layer 
        * input size: 124x124x30 
        * output size: 30x30x16
        * stride : 2, 2
        * padding : 0
        * kernel size : 5x5, 2x2
        * activation function: relu, maxpool
    - 3rd layer 
        * input size: 30x30x16
        * output size: 28x28x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
    - 4th layer 
        * input size: 28x28x16 
        * output size: 26x26x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
    - 5th layer 
        * input size: 26x26x16
        * output size: 24x24x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
    - 6th layer 
        * input size: 24x24x16 
        * output size: 11x11x16
        * stride : 1, 2
        * padding : 0
        * kernel size : 3x3, 2x2
        * activation function: relu, maxpool
    - 7th layer 
        * input size: 11x11x16 
        * output size: 9x9x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
    - 8th layer 
        * input size: 9x9x16
        * output size: 7x7x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
    - 9th layer 
        * input size: 7x7x16 
        * output size: 5x5x16
        * stride : 1
        * padding : 0
        * kernel size : 3x3
        * activation function: relu
* Hyperparameters of Feature Vector Generator Model:
    -
    - Loss function : Cross entropy loss (Best for binary classification)
    - Optimizer : Stochastic gradient descent (momentum)
    - Scheduler : StepLR (to decay learning rate by 0.9 for every 10 epochs)
    - Epochs : 50
    - Learning Rate : 0.0001
    - Batch size : 128
* Support Vector Machine as Classifier :
    -
    - Kernel : Radial Basis Function.
    - Gamma : 1e^-3, 1e^4
    - C : 0.001, 0.01, 0.1, 1 ,10, 100, 1000

* Working:
    -
    - Given image, the model will extract all 128x128 patches.
    - This 128x128x3 patches are passed to model to generate feature vector of size 16x5x5.
    - Now, this feature vector are passed to svm model traind to classify the feature vector.
    - To take decision on image mean value is derived from all patches.
    - Finally the result is show whether it is forgery or authentic.

* Report:
    - 
    - Accuracy score of Neural Network model : 85%
    - Accuracy score of SVM model : 92%
