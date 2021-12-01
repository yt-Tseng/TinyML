# TinyML
## About the project:
The original application detects the two words "Yes" and "No" on the Arduino board. After successfully running the project, I decided to move on and trained another model by myself.

In the project, I used Google Colab to train a model by two words "Stop" and "Go." Afterward, I replaced the old model and deployed it on Arduino Nano 33 BLE Sense.
Steps:
Training on Google Colab:
## Modify
In this step, I modified the training code to train the two specific words "Stop" and "Go" on Google Colab. Besides, I slightly changed the training steps and rate. 

I'll run 14000 steps in a large training rate, and run 4000 steps in a small training rate to improve it. 

## TensorBoard
Loading the TensorBoard tool to monitor the training process and results.
## Freeze the graph
In the training process, there are a lot of checkpoints. To create a model file, we should combine the graph of operations, bias, and weights in the newest checkpoint to a file. In this step, we "freeze" the graph.
## TensorFlow Lite & C array
After creating the model file, we should convert the graph into TensorFlow Lite to run on Arduino. Then we'll convert the model to a C array.
## Deploy
There are some parts of codes that need to be modified.

arduino_command_responder.cpp

micro_features_micro_model_settings.cpp

micro_features_model.cpp
