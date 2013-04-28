classifier-demo
=================

A simple demo of a bag-of-words based text classifier in python using [NTLK](http://nltk.org/book/).

Mostly ripped off from a great [pydata conference talk](http://vimeo.com/53062324)

To try it out, first install the requirements using pip:

    $ pip install -r requirements.txt

You will also need the 'wordnet' and 'stopwords' datasets, which can be obtained 
by opening your python shell and selecting the two packages for download from 
the NLTK window that pops up:

    $ python classifier.py
    >> import nltk; nltk.download()

You're now set to run the demo script itself:

    $ python classifier.py

Sample output:

    nltk4:  NLTK
    nytimes5:  Nytimes
    jezebel:  NLTK

Indicating that the trained classifier--when given an article about NLTK (data/nltk4),
by the New York Times (nytimes5), and Jezebel (data/jezebel)--classfies them as 
an NLTK, NYTimes, and NLTK article respectively.

The two additional preprocessing steps this toy classifier performs that greatly 
improves it's ability to model a document's classification is that 
1) [stop words](https://en.wikipedia.org/wiki/Stop_words) are ignored and 
2) words that share a common lemma are normalized--for example, the existence of the 
word "run" in one document is treated identically to the word "running" in another,
making the model take into account such variations of a word. The process of lemmatization
can be read about more extensively on [wikipedia](https://en.wikipedia.org/wiki/Lemmatization), 
of course.
