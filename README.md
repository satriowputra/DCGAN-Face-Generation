[//]: # (Image References)

[image1]: ./image/result.png "Generated faces"

# DCGAN-Face-Generation

## Overview

In this project, I defined and trained a DCGAN on a dataset of faces. My goal is to get a generator network to generate new images of faces that look as realistic as possible!

The project was broken down into a series of tasks from loading in data to defining and training adversarial networks. At the end of the notebook, I was able to visualize the results of trained Generator to see how it performed.

Since the project's main focus is on building the GANs, we've done some of the pre-processing. Each of the CelebA images has been cropped to remove parts of the image that don't include a face, then resized down to 64x64x3 NumPy images. Some sample data is show below.

## Installation
1. Clone this repository and navigate to the downloaded folder.
	
	```	
		git clone https://github.com/satriowputra/DCGAN-Face-Generation.git
	```
    
__NOTE:__ Please note that i am running this notebook inside Udacity workspace. Remove any `active_session()` function from the notebook to prevent error.

2. Download the cleaned dataset [here](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/November/5be7eb6f_processed-celeba-small/processed-celeba-small.zip).  Unzip the folder and place it in the repo, at notebook directory. 
3. Make sure you have already installed the necessary Python packages according to the `requirements.txt` in the program repository.
4. Open a terminal window and navigate to the project folder. Open the notebook and follow the instructions.
	
	```
		jupyter notebook dlnd_face_generation.ipynb
	```
__NOTE:__ Make sure you have PyTorch installed on your machine prior using the notebook.

__NOTE:__ There are also several libraries that i used here that should be installed if you are install Python from Anaconda Distribution such as: Numpy, Matplotlib, time, and PIL.

## File Description
There are some files I uploaded in this repository:
1. /assets: contains image used in the notebook
2. problem_unittests.py: script to test function made in the notebook
3. workspace_utils.py: contains script to prevent Udacity workspace from being disconnected while running long processes.
4. train_samples.pkl: training generator samples

## Result
![Generated faces][image1]<br>
Overall, our generated face is good enough. Facial features is clearly shown despite that the generated picture is in low resolution. Please note that almost all generated face are white due to our biased dataset.

Some artifact is shown on picture at third column. There is skin tone difference between area above and below the eyes on picture in the first row. In the second row, it looks like the model is trying to generated mustache, but the color is different from the hair color.

How we could improve this model? Here is my suggestion:
1. Add more variance to skin color with larger number of picture. By doing this, model could generate with less bias and better facial features variance due to larger input data.
2. Train model with better input image resolution. This enable us to train deeper network which could generate better image.
3. We could try another loss function. I have provided the code above. I encourage you try it!
