# Tesseract Android Tools

## Requirements
* Download and install [Android NDK](http://developer.android.com/tools/sdk/ndk/index.html)


## Installation

* Clone the repository and `cd` to it:
```
$ git clone https://github.com/rebbix/tesseract-android-tools.git
$ cd tesseract-android-tools/tesseract-android-tools
```

* Download required libraries:
```
$ ./dependencies.sh
```

* Build using NDK:
```
$ /path/to/ndk/installation/ndk-build
```


## Language Files
You can optionally download language files, most probably you will need at least one to work with.


## Usage




-----------------------


## Old (original) README
This project contains tools for compiling the Tesseract and Leptonica
libraries for use on the Android platform. It contains an Eclipse Android
library project that provides a Java API for accessing natively-compiled
Tesseract and Leptonica APIs.

NOTE: You must download and extract source files for the Tesseract and
Leptonica libraries prior to building this library.

To download the latest versions of these libraries and build this project, run
the following commands in the terminal:

cd <project-directory>
curl -O https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.02.tar.gz
curl -O http://leptonica.googlecode.com/files/leptonica-1.69.tar.gz
tar -zxvf tesseract-ocr-3.02.02.tar.gz
tar -zxvf leptonica-1.69.tar.gz
rm -f tesseract-ocr-3.02.02.tar.gz
rm -f leptonica-1.69.tar.gz
mv tesseract-3.02.02 jni/com_googlecode_tesseract_android/src
mv leptonica-1.69 jni/com_googlecode_leptonica_android/src
ndk-build -j8
android update project --path .
ant debug

To download the English language files for Tesseract and copy them to your
device's external storage, run the following commands in the terminal:

cd <project-directory>
curl -O http://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.eng.tar.gz
tar -zxvf tesseract-ocr-3.02.eng.tar.gz
rm -f tesseract-ocr-3.02.eng.tar.gz
mkdir data
mv tesseract-ocr data/tesseract
adb push data/ /sdcard/
adb shell sync
