<h1>Tokenization:</h1>


<h2>1. Using Python & NLTK</h2>
<h3>• Word Tokenization: Breaks the text into words.</h3>


```python
from nltk.tokenize import word_tokenize ##This imports the word_tokenize function from the NLTK (Natural Language Toolkit) library.
## word_tokenize is used to split sentences into words and punctuation.
```


```python
text = "Hello! I Am Tarun Kumar!"
```


```python
statement = "punkt is a pre-trained tokenizer model available in NLTK, which is used for breaking down text into words or sentences. It is a necessary resource for tokenization tasks."
```


```python
token=word_tokenize(text)
print(token)
```

    ['Hello', '!', 'I', 'Am', 'Tarun', 'Kumar', '!']
    


```python
token=word_tokenize(statement)
print(token)
```

    ['punkt', 'is', 'a', 'pre-trained', 'tokenizer', 'model', 'available', 'in', 'NLTK', ',', 'which', 'is', 'used', 'for', 'breaking', 'down', 'text', 'into', 'words', 'or', 'sentences', '.', 'It', 'is', 'a', 'necessary', 'resource', 'for', 'tokenization', 'tasks', '.']
    

<h2>• Sentence Tokenization: Splits the text into sentences.
</h2>


```python
from nltk.tokenize import sent_tokenize
```


```python
text = "hello! I love programming. It's fun!"
```


```python
token = sent_tokenize(text)
print(token)
```

    ['hello!', 'I love programming.', "It's fun!"]
    

<h2>• Character Tokenization: Breaks the text into individual characters.</h2>


```python
text = "Character tokenization splits text into individual characters."
```


```python
char_tokenize = list(text)
print(char_tokenize)
```

    ['C', 'h', 'a', 'r', 'a', 'c', 't', 'e', 'r', ' ', 't', 'o', 'k', 'e', 'n', 'i', 'z', 'a', 't', 'i', 'o', 'n', ' ', 's', 'p', 'l', 'i', 't', 's', ' ', 't', 'e', 'x', 't', ' ', 'i', 'n', 't', 'o', ' ', 'i', 'n', 'd', 'i', 'v', 'i', 'd', 'u', 'a', 'l', ' ', 'c', 'h', 'a', 'r', 'a', 'c', 't', 'e', 'r', 's', '.']
    

<h2>• Whitespace Tokenization: Splits based on spaces between words.</h2>


```python
text = "WhitespaceTokenization: Splits based on spaces between words"
```


```python
white_space_tokenize = text.split()
print(white_space_tokenize)
```

    ['WhitespaceTokenization:', 'Splits', 'based', 'on', 'spaces', 'between', 'words']
    

<h2>• Punctuation-Aware Tokenization: Treats punctuation marks as separate tokens.</h2>


```python
from nltk.tokenize import word_tokenize
```


```python
text= "Punctuation-Aware Tokenization: Treats punctuation marks as separate tokens"

```


```python
tokenization_with_punct = word_tokenize(text)
print(tokenization_with_punct)
```

    ['Punctuation-Aware', 'Tokenization', ':', 'Treats', 'punctuation', 'marks', 'as', 'separate', 'tokens']
    

<h1>Stopwords:</h1>


```python
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
```


```python
text = "The Boy is playing in the park with his friends."
word = word_tokenize(text)
stop_words = set(stopwords.words('english'))
filtered_words = [word for word in word if word.lower() not in stop_words]
```


```python
print(filtered_words)
```

    ['Boy', 'playing', 'park', 'friends', '.']
    

<h1>What is Stemming?</h1>
<h4>Stemming is the process of removing prefixes or suffixes from a word to get its root form (called a "stem").<br>
It doesn’t always give a real word — it just chops off parts of the word.</h4>


```python
from nltk.stem import PorterStemmer
```


```python
stemmer = PorterStemmer()
words = ["playing", "played", "studies", "running"]
```


```python
for word in words:
    print(f"{word}->{stemmer.stem(word)}")
```

    playing->play
    played->play
    studies->studi
    running->run
    

<h1>What is Lemmatization?</h1>
<h4>Lemmatization is the process of converting a word to its base or dictionary form, called a lemma.
Unlike stemming, lemmatization always gives you a real word.</h4>


```python
from nltk.stem import WordNetLemmatizer
import nltk
```


```python
nltk.download('wordnet')##📘 WordNet: a lexical database of English words (used for lemmatization)
```

    [nltk_data] Downloading package wordnet to
    [nltk_data]     C:\Users\LOQ\AppData\Roaming\nltk_data...
    [nltk_data]   Package wordnet is already up-to-date!
    




    True




```python
nltk.download('omw-1.4')##🌐 omw-1.4: multilingual data that helps with meanings
```

    [nltk_data] Downloading package omw-1.4 to
    [nltk_data]     C:\Users\LOQ\AppData\Roaming\nltk_data...
    [nltk_data]   Package omw-1.4 is already up-to-date!
    




    True




```python
lemmatizer = WordNetLemmatizer()
```


```python
words = ["playing", "studies", "mice", "better"]
```


```python
for word in words:
    print(f"{word}->{lemmatizer.lemmatize(word)}")
```

    playing->playing
    studies->study
    mice->mouse
    better->better
    


```python

```
