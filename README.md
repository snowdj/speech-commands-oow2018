![oowbanner](https://user-images.githubusercontent.com/5395649/46774991-04b8bf80-ccba-11e8-8dcf-2cb79bd513a6.png)

# Speech Command Recognition Demo for Oracle OpenWorld 2018

In this simple demo, we will use a convolutional neural network (CNN) to classify speech commands. We will show how one can use the **Oracle Data Science Platform** to deploy the model as a REST API endpoint. 

## Overview 

The demo is in three parts:

* In the first part, we explore audio data and the necessary data transformations we need to apply to the data before training the neural network. Refer to the Jupyter notebook : `notebooks/1-intro-to-audio-data.ipynb` . **This notebook is optional. If you are already familiar with signal processing, you may skip the first notebook** 

* In the second part, we train the CNN model using Keras. This is done in notebook `notebooks/2-cnn-model-with-keras.ipynb`

* In the last part, you test the model API endpoint you deployed on the Oracle Data Science Platform with pre-recorded audio clips. The Instructions are stored in `notebooks/3-testing-model-deployment.ipynb`. I also included instructions on how you can test the endpoint with your own audio clips using the `pyaudio` python library. This third notebook is intended to be run on your laptop. If you do not have access to the Oracle Data Science Platform, this last step should be skipped. 


## Dataset 

Throughout this demo, we use the [Speech Commands Dataset (Warden 2018)](https://arxiv.org/abs/1804.03209). You have two options to dowload the raw dataset for this demo: 
* from Oracle Cloud Object Storage by using the shell script `notebooks/get-data-from-oci.sh` 
* from its original location [http://download.tensorflow.org/data/speech_commands_v0.01.tar.gz](http://download.tensorflow.org/data/speech_commands_v0.01.tar.gz) 

Alternatively, you can use the pre-processed and transformed dataset we use in `notebooks/2-cnn-model-with-keras.ipynb` to train the model. This dataset has been serialized and can be found in this repo (`data/processed_data.pkl`). Instructions on how to load the data can be found in `notebooks/2-cnn-model-with-keras.ipynb`. 

## Installation Instructions 

These notebooks were intended to be run on the Oracle Data Science Platform. You can stil run notebooks 1 and 2 locally on your machine. Simply `pip` install the dependencies 
listed in `requirements-pip.txt` : 

```
pip install -r requirements-pip.txt
```

I simply did a `pip freeze` of my environment. I recommend running the notebooks in a `conda` environment or a Docker container. 

Any questions? contact jr.gauthier@oracle.com. 
