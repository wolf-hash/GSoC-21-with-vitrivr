## Week #2
### What did I do this week?
I talked to the main contributor of Tensorflow Java to figure out the best approach towards picking out a model. The conclusion was to choose a model with dynamic input size i.e. models that take a decoded image as the input. The reason for this was that manipulating images in Java, like resizing or padding them, can turn out to be a little difficult. 

Luckily the model I had selected had an input layer without any fixed size. It would take the image input as bytes which made it easier for me to run in Java. I wrote the code based on my earlier implementation of the Inception Net in Java. I did run into a few hiccups regarding the naming of the model output layers and data type of the output. 
Converting the output tensor to String was a little challenging since I could not figure out any function in the Tensorflow's class that would let me retrieve the value of the output because it was a scalar in this case. After a while of searching I found out that I could use the *bytesValue()* function to retrieve the tensor's value in bytes and then convert it to String. 

Here is the [link](https://github.com/wolf-hash/Attention-OCR-in-Java) to the repository.

The model is still untrained. Training can be done at a later point. My first aim will be to integrate this into the Cineast code base.
