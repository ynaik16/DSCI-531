This project has two parts - Analysis of existing ASR which is contained in the ASR_analysis.ipynb and secondly, python files long with vui_notebook.ipynb which contains code of my custom ASR.

Dataset for Analysis part is contained in the Datasets folder which contains predicted text for different accents (Scotland, Wales, Nigeriain) in .zip file.
To download American Accent speech use the link <https://www.openslr.org/45/> to download the zippd file


 *******************************************************************************************************
 Follow these steps below for custom ASR
 *******************************************************************************************************
-Obtain the libav package.

Linux: sudo apt-get install libav-tools
Mac: brew install libav
Windows: Browse to the Libav website
Scroll down to "Windows Nightly and Release Builds" and click on the appropriate link for your system (32-bit or 64-bit).
Click nightly-gpl.
Download most recent archive file.
Extract the file. Move the usr directory to your C: drive.
Go back to your terminal window from above.
rename C:\usr avconv
set PATH=C:\avconv\bin;%PATH%

- Here are the instruction to download Librispeech dataset to train custom VUI 

Obtain the appropriate subsets of the LibriSpeech dataset, and convert all flac files to wav format.

wget http://www.openslr.org/resources/12/dev-clean.tar.gz
tar -xzvf dev-clean.tar.gz
wget http://www.openslr.org/resources/12/test-clean.tar.gz
tar -xzvf test-clean.tar.gz
mv flac_to_wav.sh LibriSpeech
cd LibriSpeech
./flac_to_wav.sh

- Create JSON files corresponding to the train and validation datasets.

cd ..
python create_desc_json.py LibriSpeech/dev-clean/ train_corpus.json
python create_desc_json.py LibriSpeech/test-clean/ valid_corpus.json

-Install a few pip packages.

pip install -r requirements.txt

-- run the Jupiter notebook now
