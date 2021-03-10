# RANZCR CLiP - Catheter and Line Position Challenge - Baseline

The challenge is to classify the presence and correct placement of tubes on chest x-rays to save lives. Early recognition of malpositioned tubes is the key to preventing dangerous complications, mainly now that millions of COVID-19 patients need these tubes and lines. 

I've implemented on Colab a notebook where I'll show how to apply the following concepts to get **0.96+ Area under the ROC Curve**:
* **Transfer Learning**: Keras provides several pre-trained models, and we can use them, such as the Xception and InceptionResNetV2, for our task.
* **Data Augmentation**: Data augmentation is significant to avoid overfitting. I used some random augmentations like horizontal/vertical flips, saturation, brightness, and contrast.
* **Best Learning Rate**: Find the best possible learning rate for the model. This is done by plotting a graph between the learning rate and the loss function to check where the loss starts decreasing.
* **Learning rate annealing**: Cosine annealing learning rate scheduler with periodic restarts https://arxiv.org/abs/1608.03983.
* **Ensembling**: Bagging using K-Fold and Xception pre-trained on Imagenet.
* **Test time augmentation (TTA)**: a final technique that can raise accuracy by one per cent or two is test time augmentation (TTA). This involves taking a series of different versions of the original image (for example, cropping different areas or changing the zoom) and passing them through the model. The average output is then calculated for the different versions, and this is given as the final output score for the image.

