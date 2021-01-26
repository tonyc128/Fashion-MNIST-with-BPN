# Fashion-MNIST-with-BPN

Fashion MNIST using BPN (one hidden layer)

## Result
accuracy: 85.95%

## Dataset 
The dataset this project is using is from https://www.kaggle.com/zalando-research/fashionmnist.

## Notice
Seperate the original training data set into fashion-mnist_train_data and fashion-mnist_train_label.
Seperate the original testing data set into fashion-mnist_test_data and fashion-mnist_test_label.

## 說明
在此實驗中，我們使用兩種方法。第一種方法是基礎的One hidden layer Neural Network with BPN。第二種方法是仿造Paper所提出的方法，並稍作修改，實現CNN的圖片辨識。
One hidden layer Neural Network with BPN

![](https://i.imgur.com/bbCJO3t.png)

Fig. 1 : Architecture of One hidden layer Neural Network
Forward-Propagation
Inner-Product (Hidden Layer)：每一個輸出是前一層的每個結點乘以一個權重係數 (W)，再加上一個bias (b)。

![](https://i.imgur.com/BjAKDTG.png)

Activation Function (Hidden Layer)：利用非線性函數作為 Activation function，使輸入不再是線性組合，得以逼近任意函數。(本實驗使用ReLu當作Activation layer)

![](https://i.imgur.com/E4EAmDw.png)

Inner-Product (Output Layer)：每一個輸出是前一層的每個結點乘以一個權重係數 (W)，再加上一個bias (b)。(同1.)

![](https://i.imgur.com/omWaqHU.png)

Softmax (Output Layer)：對向量進行歸一化，凸顯其中最大的值並抑制遠低於最大值的其他分量，藉此找出最可能的值。
![](https://i.imgur.com/gnvPIes.png)

Backward-Propagation
Softmax (Output Layer)：將預測結果與 Label 比較得到 Loss。

![](https://i.imgur.com/CNT3zSx.png)

Inner-Product (Output Layer)：由已知傳遞到該層的梯度 (dEdy)，透過 chain rule 運算得到 dEdx、dEdW、dEdb

![](https://i.imgur.com/pitXLEB.png)

Activation Function (Hidden Layer)：保留已知傳遞到該層的梯度 (dEdy) 中大於 0 的值，小於 0 的值則指定為 0。

![](https://i.imgur.com/jazF90C.png)
![](https://i.imgur.com/FrLM7Zw.png)

Inner-Product (Hidden Layer)：由已知傳遞到該層的梯度 (dEdy)，透過 chain rule 運算得到 dEdx、dEdW、dEdb。(同1.)

![](https://i.imgur.com/JbuKoki.png)



