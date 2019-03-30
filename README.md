# PENNER: Pattern-enhanced Nested Named Entity Recognition in Biomedical Literature

This is the implementation of [PENNER: Pattern-enhanced Nested Named Entity Recognition in Biomedical Literature](), published in BIBM 2018. The general goal of this project is to extract nested structures/patterns from a corpus.

## Quick Start
To reproduce the results in our paper, you can directly download our preprocessed data/corpus from **[here](https://drive.google.com/file/d/1fGUZ_OI_iAlmpsdi1O1Dq3HvTavAu-NJ/view?usp=sharing)**, unzip the folder ```penner/``` and put it under the ```./data/``` folder. Then run
```
python3 ./src/SetExpan/set_expan_main.py
```
The expanded nested patterns will be in the output file ```./src/SetExpan/ExpanResult.txt```.

To test the method on your own dataset, you need to follow the steps listed below.

## Requirements
Adapted from [SetExpan](https://github.com/mickeystroller/SetExpan), the data preprocessing code requires the user to download the following two related packages and put them in the ```/src/tools/``` folder:

* [AutoPhrase](https://github.com/shangjingbo1226/AutoPhrase): used to extract quality phrases from raw input data.
* [Stanford CoreNLP 3.8.0](https://stanfordnlp.github.io/CoreNLP/history.html): used to do POS tagging and select quality Noun Phrases from the previous phrase list generated by AutoPhrase. The quality Noun Phrase will be treated as the "entity".

## Input
Two input files are required in ```./data/penner/``` (You can change "penner" to your dataset name). One is the corpus with replaced type tokens and candidate meta-patterns (e.g., ```./data/penner/corpus.txt```). The other is the mapping list of pattern id and pattern surface name (e.g., ```./data/penner/pid2mp.txt```).

## Running
You can use the script
```
./run.sh
```
It contains both preprocessing steps and the main expansion algorithm.

## Citation
If you find the implementation useful, please cite the following paper:
```
@inproceedings{wang2018penner,
	title={PENNER: Pattern-enhanced Nested Named Entity Recognition in Biomedical Literature},
	author={Wang, Xuan and Zhang, Yu and Li, Qi and Wu, Cathy H. and Han, Jiawei},
	booktitle={BIBM'18},
	year={2018},
	organization={IEEE}
}
```
