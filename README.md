# white2black-GAN
**white2black for T-shirts Cycle GAN (weights included). [ENG]**

Task
-----------------------------------
The task was to turn the black T-shirts in the photo into black ones and vice versa.

Dataset
-----------------------------------
My dataset of black and white T-shirts is essentially part of a larger dataset consisting of many images of clothing of different types and colors with Ali Express. You can find it [here](https://github.com/deerslab/clothes-dataset).
To use the T-shirts dataset, you will first need to download it from [this link](https://drive.google.com/file/d/1bM4eoMcNmTbUoQRhJVKiTRY7l9ZiY_1E/view?usp=sharing) (2 GB). Next, without changing the name or unpacking the archive, you should put it in the root of your Google drive. Then the corresponding cell in the code will download it and unpack it.

The dataset is divided into 4 parts in advance (folders):
1. testA (1000 Files)
2. testB (1000 Files)
3. trainA (11137 Files)
4. trainB (11137 Files)

`A-files - white ones, B-files - black ones.`

This dataset is far from ideal. It is not possible to collect such a number of images manually, because the dataset was probably formed by parsing. It includes not only title images of products, but also images from customer reviews, because there is not a little garbage. However, I tried to reduce their impact on my network and in the end, I got good results. If the network sees an image where there is no t-shirt of the desired color at all, then most often it simply ignores it and returns almost the same.

Weights
-----------------------------------
The weights were too large to directly add them to github, so I leave you links to download them. You will need to download them and, without changing the name, put them in the root of your Google drive, and the corresponding cell in the code will pass them to the necessary models. To implement Cycle GAN, you need 4 different models, so there will also be 4 weights.

Links:
* https://drive.google.com/file/d/10BKZTSgx8189tPLPrAIM6Jzdwbj6MeAT/view?usp=sharing
* https://drive.google.com/file/d/10BNjUEf9tFb6hPhyvQZJmQsxqhZNb0WN/view?usp=sharing
* https://drive.google.com/file/d/10C7Xjc4ud8zzchgy8QPXSnySFBqAwG7S/view?usp=sharing
* https://drive.google.com/file/d/10Ba-juJCx00i1CPs-cGjYCWPudXzjCme/view?usp=sharing

Training
-----------------------------------
All training parameters can be found in the laptop. I decided to do 200 epochs of training. If you suddenly decide to train this network yourself, keep in mind that for a full day on Google Colab Pro, approximately 20-30 epochs are performed. In this regard, I had to load weights several times and start with checkpoints. The code for loading weights is in the laptop. The training cycle also contains a block of code that saves weights to your Google drive every epoch, specifying the era number in the name.

You can change the training parameters to get a better result. **n_cpu** (the number of cores in the processor) I have costs 2, because my processor only has two cores, you can put the number of cores of your processor. **Batchsize** I have is 6, this is the maximum size that fits on the GPU provided by Google Colab Pro. If you get an error, try reducing this parameter.

Other
-----------------------------------
All other comments and explanations are contained in the laptop itself. There is an illustration of the final results at the end of the notebook. You can also find two cells before the learning cycle cell that will help you convert your own image (preferably JPG).
