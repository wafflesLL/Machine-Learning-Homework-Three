Liam Loeffel
COSC 312
Dr. Santos
12 November 2025
## Task 1
* Describe your pre-processing steps and justify your feature engineering decisions. (Under 200 words)
    *  Include a dataflow diagram (hand-drawn or graphic tool based) that outlines all preprocessing steps, indicating where data statistics, such as the mean and standard deviation (used for data standardization), are calculated and applied.
![[ML dataflow diagram.png]]
1. I obtained the data from the kaggle dataset https://www.kaggle.com/competitions/titanic/data
2. I decided to drop the `PassengerId` and `Name` since those features are irrelevant to whether the passengers survived or not
3. I decided to drop the `Cabin` and `Ticket` features because they were too sparse and they would inflict too much unnecessary variance to the data since most of the data was missing
4. I imputed the missing data with the median of the feature in order to counteract the bias that the outliers may inflict on the imputed values
5. While One hot encoding I chose to omit one of the columns every time I ran the function, in order to prevent colinearlity and decrease dimensionality
6. When standardizing the data I chose to use Min-Max standardization because it was more simple, and I could use the same function i used beforehand
7. when I split the data into validation and test sets, I just took 15 percent of the data for validation, and did not worry about data leakage, since each sample was unique
8. when I tensorized the data I used `torch.from_numpy()` function to convert the numpy arrays to Pytorch tensors
9. No need for this step since we did not have any duplicate samples

* What resources did you use to build the TitanicDataset class? Were these resources the most helpful and inspiring to you? (Under 200 words)
	* I used my prior python knowledge to create a class and its constructor
	* then I went to see how to create a tensor from the [PyTorch Documentation](https://docs.pytorch.org/tutorials/beginner/basics/tensorqs_tutorial.html)
## Task 2
1. What resources did you use to build the `MLP_Network` class? Were these resources the most helpful and inspiring to you? (Under 200 words)
	*   the pytorch documentation, Building Multilayer
	* 
2. Justify your choices for the hyperparameter search.
3. Compare and analyze the results from various hyperparameter configurations to provide insights into model performance.
4. Select the best-performing model and justify your selection.
5. When explaining your design choices, include performance visualizations and evaluation results such as loss curves, accuracy metrics, and confusion matrices.
6. Submit your solution to Kaggle and report on your ranking