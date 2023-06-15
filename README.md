# Disinformation Scraping

This directory contains two site-specific scrapers in the scraper folder 
as well as an application of the Roberta misinformation classifier on
to the data scraped using these scrapers. 

The scraper folder contains two scrapers: one for AEI.org and one for Heartland.org

## AEI.ipynb
This scraper scrapes title, date, authors, and content from all publications
with the tag: "climate change" available at
https://www.aei.org/search-results/?wpsolr_fq%5B0%5D=tags_str:Climate%20change&wpsolr_page=1
It outputs all the articles at data/AEI.csv with each row representing an
article.

## Heartland.ipynb
This scraper scrapes title, date, authors, and content from all publications and
op-eds in the category: "environment and energy" available at
https://heartland.org/opinion/?topic=environment-energy and
https://heartland.org/publications/?topic=environment-energy. 
It outputs all the articles at data/heartland.csv with each row representing an
 article.


## classification.ipynb
This file applies to the logisti side of the misinformation classifier from
(https://www.nature.com/articles/s41598-021-01714-4) to each paragraph of an
article. 
Adds a row to the csv/dataframe with a list of claims made in the article. Each
element in the list is a claim corresponding to the article's paragraph at that
index. For this to work you need to actually download the model from
https://github.com/traviscoan/cards at the very bottom where it's possible to
download the pre-trained model. 