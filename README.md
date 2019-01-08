## Let's get a hang of it ❄️ 

An autoencoder is an Unsupervised Learning technique that applies backpropagation, setting the target values to be equal to the input values. We'll design a neural network architecture such that we impose a bottleneck in the network which forces a compressed knowledge representation of the original input.

<p align="center"><img src="./images/1_auto_encoders.png" width="300" height="300"/></p>

> Data denoising and and Dimensionality reduction are the two major applications of Autoencoders.

It's capable of implementing some amazing things, ranging from image colorization, image generation to dialogue generation. 

* **Encode** - Compress the inputs to a few bits, also called the *latent-space representation*.<br>
* **Decode** - Reconstruct the image from the above generated latent-space representation. 

<p align="center"><img src="./images/auto-arch.png" width="600" height="300"/></p>

So, why are we doing this, wherein we're constructing the input back at the output side (there's no output though)?
The reason is, if at all the input is constructed reliably at the output side, it indicates that the hidden layers have enough information to represent the output. Hence, in an autoencoder, we care about the hidden layer(s). A hidden layer is smaller than the input and output layer, in terms of the number of nodes, and henceforth, stores dense information. If at all the hidden layer is the same as the input layer, then the network just blindly memorizes the data by passing the values to the output layer. Therefore, we need to make sure to let the **hidden layer be the bottleneck**. 

This feature of the autoencoder produces a lower-dimensional representation of the input. In this case, the autoencoder is termed to be **undercomplete**. And yes, this is how, we would do dimensionality reduction using an autoencoder (A no-brainer indeed!). 

*Why not PCA?* <br>
PCA is restricted to a linear map, whereas autoencoders can have non-linear encoder/decoder. That is, if we were to use linear activation functions at each layer in an autoencoder, it would be the same as PCA. Nonetheless, if it were non-linear activation functions, autoencoders trump PCA.

It's also used for *image classification* purposes, say a set of images belonging to a particular class are sent and trained. Take a note of this, 'only a single class images are sent'. The model gets trained, learns the parameters, and then, when a new instance is sent to it, it calculates the reconstruction error existing between the reconstructed image and the actual image. If the error is low, then it's likely belonging to the same class on which the model is trained. Hence, **Binary Classification** does make sense in the case of autoencoders which can indeed be extended to **Anomaly detection** as well. 

An interesting point to take note of is, it has this adversarial nature embedded in it, similar to the way **Generative Adversarial Networks** function. The trade-off in here, exists between the reconstruction loss and the regularizer. Reconstruction loss should be low between the input image and the reconstructed image, but the regularizer discourages over-memorization or overfitting. 






