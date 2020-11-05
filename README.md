# NLP Bake-Off
> Please read the instructions!

![Obama Inauguration Audience](https://cdn.britannica.com/63/127963-050-D8E9AEFC/Barack-Obama-Pres-steps-address-US-Capitol-Jan-20-2009.jpg)

---------------

## Context

Is it possible to identify the political party of U.S. Presidents from their inauguration speeches? That is your challenge in this bake-off!

U.S. Presidents have represented five different political parties in unequal numbers: 
- Democrats 
- Democratic-Republicans
- Federalists
- Republicans
- Whigs 

Of the 58 inaugural speeches, about 40% were given by representatives of the Democratic Party, and about 40% were given by representatives of the Republican, with the remainder split among the other three parties named above.

----------------
## Your Task

In this repo are three pickled `pandas` Series: X_train, y_train, and X_test. The contents of X_train and X_test are the speeches; the contents of y_train are the political parties of the presidents who gave the corresponding speeches in X_train. **Your job is to build a model to predict the political parties of the presidents who gave the speeches contained in X_test.**


### Preprocessing

Note that you will need to do some preprocessing of the data. The speeches in X_train (and X_test) are *mostly* clean in the sense of containing little else beyond the English words of the speeches themselves. But you may want to do some further cleaning. And you will definitely want to consider strategies like:

- Eliminating capital letters and punctuation;
- Using a stemmer or a lemmatizer;
- Tokenizing; and
- Employing `CountVectorizer()` or `TfidfVectorizer()`

before you get to modeling.

You may use any of the modeling techniques we have explored that apply to classification problems, including any of the modeling classes contained in `sklearn.naive_bayes`.

Your final model will be evaluated according to its _accuracy_.

# Get started
To begin the bakeoff:
1. Fork this repo
2. Clone your fork onto to your local computer
3. cd into the repo folder
4. Create a notebook and get to baking!


# Format Your Predictions

Once you have generated predictions for `y_test.pkl`, you will need to transform the array of numbers back into an array of letters. To do this you can use `.inverse_transform()`. If you are unfamiliar with this process, an example has been provided below:

```python
from sklearn.preprocessing  import LabelEncoder

array =  ['a', 'b', 'c', 'd']
encoder = LabelEncoder()
encoded_array = encoder.fit_transform(array)
print(encoded_array)
>>> [0 1 2 3]

decoded_array = encoder.inverse_transform(encoded_array)
print(decoded_array)
>>> ['a' 'b' 'c' 'd']
```

After you have transformed your predictions into an array of letters, please pickle your predictions and label the file using you and your teammate initials seperated by an underscore followed by '_predictions.pkl'. 

> For example, if Erin and Joél were a team their pickled predictions would be called `'eh_jc_predictions.pkl'`.

# Validate and Submit Your Predictions

#### Validate

Once you have saved your predictions to file, please open the [validate_predictions](./validate_predictions.ipynb) notebook, and follow the instructions to ensure you predictions are the correct shape and datatype!

#### Submit

Once you pass all of the tests in the validation notebook
1. `git add` your bakeoff notebook and your predictions
2. `git commit`
3. `git push` your work to your fork.
4. Navigate to the [NLP Bakeoff Canvas Assignment](https://learning.flatironschool.com/courses/605/assignments/48829) and submit a link to your fork.

--------

**Note:** It would be possible for you to search for the speeches that are contained in X_test and discover who gave them (and also what the speakers' political parties were). For the sake of this bake-off we of course cannot allow that and will consider any such behavior as cheating. You are on your honor!

--------