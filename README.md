# Analysis of German election manifestos 
The notebooks in this repository are part of a project that analyses the major German parties’ manifestos for the federal elections from 1949-2021. The diversity of German parties makes this task particularly interesting, as there are and have been multiple parties in parliament, all with slightly different ideologies.

This project was created during my postgraduate studies in the course unit "Natural Language Processing for the Creative Industries" at UAL in 2022.
Unit Tutors:  [Louis McCallum](http://louismccallum.com/), [Terence Broad](https://terencebroad.com/), [Rebecca Fiebrink](https://researchers.arts.ac.uk/1594-rebecca-fiebrink)

## The data
I retrieved the data needed for this analysis from the [Manifesto Project] (https://manifestoproject.wzb.eu/) using their [R package] (https://manifestoproject.wzb.eu/information/documents/manifestoR), but you can also use the API directly (with Python). Anyone can create an account on their website and request an API key. However, it is forbidden to share the data provided, so I will not publish it here.

## Order and explanations of the notebooks
### 01_Data-cleanup
Some of the manifestos (the newer ones) are split into many quasi-sentences/rows because the Manifesto Project has annotated them. This is why my dataset partly looked like this (simplified):

    manifesto_id                                      text  date
    101                             The government changed  1990
    101                 the legislation on import control.  1990
    102                 Politics cannot solve all problems  2005
    102                  but it should try to do its part.  2005
    
The code in this notebook puts the 'text' fields back together.

### 02_Stopwords-Lemmatisers
Since I work with German-language documents, I had to try out several stopword lists and lemmatisers to see which ones would work best for my use case. The notebook contains this exploration.

### 03_BagOfWords-TFIDF
As the name suggests, this notebook contains the code of how I applied Bag-of-Words and TF-IDF to analyse my data.

### 04.1_Topic-Modelling
Using LSA and LDA with my data.

### 04.2_Topic-Numbers
I separated this code from the previous notebook (04.1_Topic-Modelling) to test out various topic numbers and to explain why I chose the numbers I used in the main notebook.

### Other folders
- **stopwords:** Contains some of the stopword lists (and their MIT licences), which are tested in notebook 02.
- **data:** Contains images that are included in the notebooks. Originally, the dataset was also stored here.


## Credits
As mentioned, I tried out different stopword lists and lemmatisers in the second notebook. To give them the credit they deserve, here is a list of what I used:
- **stop-words 2018.7.23** by Alireza Savand & Contributors (2014), can be found [here](https://pypi.org/project/stop-words/).
- **german_stopwords** Marco Götze and Steffen Geyer (2016), can be found [here](https://github.com/solariz/german_stopwords).
- **Stopwords German (DE)** by Gene Diaz & Contributors (2020), can be found [here](https://github.com/stopwords-iso/stopwords-de).
- **HanTa - The Hanover Tagger** by Christian Wartena (2019), can be found [here](https://github.com/wartaal/HanTa). *For a explanation of the underlying ideas see:* Christian Wartena (2019). A Probabilistic Morphology Model for German Lemmatization. In: Proceedings of the 15th Conference on Natural Language Processing (KONVENS 2019): Long Papers. Pp. 40-49, Erlangen. https://corpora.linguistik.uni-erlangen.de/data/konvens/proceedings/papers/KONVENS2019_paper_10.pdf https://doi.org/10.25968/opus-1527
- **simplemma 0.9.1** by Adrien Barbaresi (2021), can be found [here](https://pypi.org/project/simplemma/).