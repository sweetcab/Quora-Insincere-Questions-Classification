# Quora-Insincere-Questions-Classification

## Introduction
This task is to predict whether a question asked on Quora is sincere or not.

An insincere question is defined as a question intended to make a statement rather than look for helpful answers. 
Some characteristics that can signify that a question is insincere:

* Has a non-neutral tone
* Has an exaggerated tone to underscore a point about a group of people
* Is rhetorical and meant to imply a statement about a group of people
* Is disparaging or inflammatory
* Suggests a discriminatory idea against a protected class of people, or seeks confirmation of a stereotype
* Makes disparaging attacks/insults against a specific person or group of people
* Based on an outlandish premise about a group of people
* Disparages against a characteristic that is not fixable and not measurable
* Isn't grounded in reality
* Based on false information, or contains absurd assumptions
* Uses sexual content (incest, bestiality, pedophilia) for shock value, and not to seek genuine answers

The training data includes the question that was asked, and whether it was identified as insincere (target = 1). 
The ground-truth labels contain some amount of noise: they are not guaranteed to be perfect. (The data could be found at 
[Dataset](https://www.kaggle.com/c/quora-insincere-questions-classification/data))

## Training Results


| Model | Model Size | Batch Size | Epoch | Learning Rate | Keep Prob | Time | Accuracy |
| --------- | ---------- | -------- | -------- | --------------- | --------------- | --------------- | --------------- |
|LSTM|256*3|512|1|0.0001|0.5|30m|0.950|
|LSTM|256*3|512|2|0.0001|0.5|1h20m|0.953|
|LSTM|256*3|512|5|0.0005|0.5|2h40m|0.957|
|LSTM|256*3|512|1|0.001|0.5|20m|0.937|
|LSTM|128*3|512|1|0.0001|0.5|20m|0.950|
|LSTM|128*3|512|5|0.0005|0.5|1h20m|0.957|
|LSTM|128*3|512|8|0.0005|0.7|2h10m|0.957|
|Bi-LSTM|128*1|512|1|0.0005|0.5|20m|0.952|
|Bi-LSTM|128*3|512|3|0.0005|0.5|1h10m|0.956|
|Bi-LSTM|64*3|512|3|0.0002|0.5|1h10m|0.955|
|Bi-LSTM|128*1|1024|7|0.0001|0.7|42m|0.952|
|Bi-LSTM-Attention|32*1|512|2|0.0005|0.5|1h|0.956|0.594|
