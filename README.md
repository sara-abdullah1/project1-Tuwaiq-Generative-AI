# Project1 - Tuwaiq Generative AI
## News Article Classification

This project classifies Arabic news articles into seven categories: Sport, Finance, Religion, Technology, Medical, Culture, and Politics.

It utilizes the [MARBERT model for news article classification](https://huggingface.co/Ammar-alhaj-ali/arabic-MARBERT-news-article-classification), provided by Ammar Alhaj.

Dataset: [SANAD: Single-Label Arabic News Articles Dataset for Automatic Text Categorization](https://data.mendeley.com/datasets/57zpx667y9/2).

The Gradio library is used to build a graphical user interface (GUI) for easy interaction with the model.

Link to the project on Hugging Face:
[News Article Classification on Hugging Face](https://huggingface.co/spaces/SarahMarzouq/newsArticleClassification)

---

## Main Files and Their Functions:
The project is divided into three separate Python notebooks:

### 1. Notebook One (HuggingFace_P1.ipynb):
Implements the Hugging Face MARBERT model for news article classification using the pipeline from the transformers library. This notebook processes a list of Arabic sentences (news article) provided by the user, classifying them into one of seven categories (Sport, Finance, Religion, Technology, Medical, Culture, Politics), along with a confidence score for each prediction. After classification, the results are converted into a pandas DataFrame for further analysis and visualizations using matplotlib.

#### Main Operations in Notebook One:
- Uses the Hugging Face text-classification pipeline to categorize a list of sentences with the confidence score.
- The results are stored in a pandas DataFrame, with columns for the sentences, categories (labels), and confidence score.
- Generates visualizations, such as bar charts and pie charts, to depict the distribution of the categorized articles.

#### The Expected Output:
- **DataFrame Contents**: label, score, sentence, sorted in descending order of score.
- **Information about the DataFrame**: Displays the number of rows and columns and shows data types of each column.
- **Some Calculations**: Displays the minimum and maximum values in the score column and displays rows where the score is less than 0.99.
- **Label Distribution**: Counts the number of sentences for each label and the total number of sentences and identifies the label with the highest count.

Visualizations:
- **Bar Chart**: Visualizes the number of sentences per label.
- **Pie Chart**: Shows the proportion of sentences for each label.

---

### 2. Notebook Two (Gradio_P1.ipynb):
Implements a simple Gradio interface that allows users to input a news article and get the classification result (label) along with a confidence score, with custom CSS to enhance the experience. This notebook simulates the functionality of the Hugging Face MARBERT model for news article classification without using the actual model. Instead, it uses predefined word lists for each category to classify sentences and return a predicted label and random confidence score just as an example.

#### Main Operations in Notebook Two:
- Categorizes Arabic news articles into seven categories (Sport, Finance, Religion, Technology, Medical, Culture, and Politics) based on the presence of specific keywords in the sentence.
- Uses predefined word lists for each category. For example, words related to "Sport" (like "فريق", "مباراة") will categorize the input as "Sports."
- The function checks for the presence of words from these lists in the input and returns the corresponding category with a randomly generated confidence score.

#### The Expected Output from the Gradio Interface:
- The user enters an Arabic news article in the textbox.
- The Gradio interface processes the input using the `classification_fun` function, which checks for the presence of keywords from predefined lists (Sport, Politics, etc.).
- The function returns two outputs:
  - **Label of the Article**: The category that best matches the article based on the identified keywords.
  - **Confidence Score**: A randomly generated score between 0.0 and 0.99, simulating a real-world scenario. This score is random because we are not using a pre-trained model in this notebook.

---

### 3. Notebook Three (HuggingFace_Gradio_P1.ipynb):
Integrates the Hugging Face MARBERT model for news article classification with the Gradio interface. Users can input Arabic news articles, and the model will classify the text, returning both the label (category) and the confidence score. The interface is styled with custom CSS.

#### Main Operations in Notebook Three:
- Categorizes Arabic news articles into seven categories (Sport, Finance, Religion, Technology, Medical, Culture, and Politics) using the Hugging Face MARBERT model for news article classification.
- The function uses the model to process the input and returns the corresponding category with a confidence score.

#### The Expected Output:
- **Label of the Article**: The category that best matches the article based on the Hugging Face MARBERT model for news article classification.
- **Confidence Score**: A numerical score between 0.0 and 1.0 indicating the model's confidence in the classification.

---

## How the Text-to-Text Pipeline Works:
- **Model Selection**: We choose a text-to-text model that processes text input and provides text output. In our case, the model is designed for news article classification in Arabic.
- **Input**: Arabic news articles are fed into the pipeline from Hugging Face.
- **Process**: The pipeline processes the input text and classifies it into predefined categories.
- **Output**: The result of the process is a text label indicating the category of each news article and the confidence score.

---

## How to Run the Code

You can run the code either locally or on a cloud-based platform (such as Google Colab or Jupyter Notebook). Ensure you have installed the required libraries listed in the `requirements.txt` file before running the notebooks.

1. **Notebook 1 (HuggingFace_P1.ipynb)**:
   - You can change the sentences of news articles in the list to test different scenarios and check the accuracy of the model.

2. **Notebook 2 (Gradio_P1.ipynb)**:
   - Try inputting various news articles (one at a time) and test if each list for the categories contains enough keywords. You may also add new keywords to improve the classification.

3. **Notebook 3 (HuggingFace_Gradio_P1.ipynb)**:
   - Input any news articles to see how the Hugging Face MARBERT model classifies them and review the results.


---

## Video:
A video demonstrating the project has been uploaded to the repository. You can view it for a better understanding of the project. You can find it in the [`video/`](./video) directory as `demo_video.mp4`.
