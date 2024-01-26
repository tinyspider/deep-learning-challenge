# Neural Networks Optimization Report

## Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures.

## Results
### Data Preprocessing
- What variable(s) are the target(s) for your model?
    - "IS_SUCCESSSFUL" column
- What variable(s) are the features for your model?
    -  APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
- What variable(s) should be removed from the input data because they are neither targets nor features?
    - EIN is neither a target nor a feature. NAME was removed in the initial model but was kept in the optimized model as a feature. 
### Compiling, Training, and Evaluating the Modelc22
- How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - First model: Loss: 0.5625632405281067, Accuracy: 0.7268804907798767
        - layer 1, 80, relu
        - layer 2, 30, sigmoid
        - layer 3, 1, sigmoid
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/1%20(1).png)
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/1%20(2).png)
    - Optimization v1: Loss: 0.5754250288009644, Accuracy: 0.7276967763900757
        - nodes_layer_in, 200, relu
        - nodes_layer1, 200, sigmoid
        - nodes_layer2, 100, sigmoid
        - nodes_layer3, 50, sigmoid
        - nodes_layer4, 25, sigmoid
        - nodes_layer_out, 1, sigmoid
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/2%20(1).png)
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/2%20(2).png)
    - Optimization v2: Loss: 0.560258686542511, Accuracy: 0.7276967763900757
        - nodes_layer_in, 40, relu
        - nodes_layer1, 20, sigmoid
        - nodes_layer2, 10, sigmoid
        - nodes_layer_out, 1, sigmoid
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/3%20(1).png)
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/3%20(2).png)
    - Optimization v3: Loss: 0.4654858112335205, Accuracy: 0.7878717184066772
        - nodes_layer_in = 80, relu
        - nodes_layer1 = 30, sigmoid
        - nodes_layer_out = 1, sigmoid
        - "NAME" is kept as a feature. 
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/4%20(1).png)
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/4%20(2).png)
        - ![photo1](https://github.com/tinyspider/deep-learning-challenge/blob/main/Result/Photos/name.png)
        
- Were you able to achieve the target model performance?
    - Yes. 
- What steps did you take in your attempts to increase model performance?
    - Attempt 1 has 5 layers and more neurons than the unoptimized model.
    - Attempt 2 has 4 layers and fewer neurons in each layer than the unoptimized model.
    - Attempt 3 has the "NAME" column as a feature instead of dropping it. Any value in "NAME" that occurred less than 5 times was replaced as other. The same layer and neuron setup as the unoptimized model.
## Summary

Overall, the final model can predict at 78.79% accuracy.
Alternatively, we could use a random forest model, which constructs multitude of decision trees at training time. The random forest model deals with semi-continuous variables easily. It also handles mixed variable types well. 
