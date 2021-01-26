---
layout: model
title: Recognize Entities OntoNotes - BERT Base
author: John Snow Labs
name: onto_recognize_entities_bert_base
date: 2020-12-09
tags: [pipeline, open_source, en]
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

A pre-trained pipeline containing NerDl Model. The NER model trained on OntoNotes 5.0 with `bert_base_cased` embeddings. It can extract up to following 18 entities :

`CARDINAL`, `DATE`, `EVENT`, `FAC`, `GPE`, `LANGUAGE`, `LAW`, `LOC`, `MONEY`, `NORP`, `ORDINAL`, `ORG`, `PERCENT`, `PERSON`, `PRODUCT`, `QUANTITY`, `TIME`, `WORK_OF_ART`.

{:.btn-box}
[Live Demo](https://demo.johnsnowlabs.com/public/NER_EN_18/){:.button.button-orange}
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/onto_recognize_entities_bert_base_en_2.7.0_2.4_1607509662244.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use

<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPython.html %}

```python
from sparknlp.pretrained import PretrainedPipeline

pipeline = PretrainedPipeline('onto_recognize_entities_bert_base')

result = pipeline.annotate("Johnson first entered politics when elected in 2001 as a member of Parliament. He then served eight years as the mayor of London, from 2008 to 2016, before rejoining Parliament.")

```
```scala
import com.johnsnowlabs.nlp.pretrained.PretrainedPipeline

val pipeline = new PretrainedPipeline("onto_recognize_entities_bert_base")

val result = pipeline.annotate("Johnson first entered politics when elected in 2001 as a member of Parliament. He then served eight years as the mayor of London, from 2008 to 2016, before rejoining Parliament.")
```
</div>


{:.h2_title}
## Results

```bash
+------------+---------+
|chunk       |ner_label|
+------------+---------+
|Johnson     |PERSON   |
|first       |ORDINAL  |
|2001        |DATE     |
|Parliament  |ORG      |
|eight years |DATE     |
|London      |GPE      |
|2008 to 2016|DATE     |
|Parliament  |ORG      |
+------------+---------+
```

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|onto_recognize_entities_bert_base|
|Type:|pipeline|
|Compatibility:|Spark NLP 2.7.0+|
|Edition:|Official|
|Language:|en|

## Included Models

 - DocumentAssembler
 - SentenceDetectorDLModel
 - Tokenizer
 - BertEmbeddings
 - NerDLModel
 - NerConverter