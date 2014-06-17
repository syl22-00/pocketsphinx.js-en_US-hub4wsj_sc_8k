PocketSphinx.js HUB4 acoustic model bower package
-------------------------------------------------

This is the bower package for the HUB4 acoustic model to be used with `pocketsphinx.js`. 

HUB4 is an acoustic model for US English, trained on broadcast news audio. It is available as part of [PocketSphinx](http://cmusphinx.org). Is should be used with audio recorded at 8kHz.

This bower package depends on `pocketsphinx.js-lib` which contains the library, without any language-specific file, such as acoustic or language model.

# 1. usage

For general usage of `pocketsphinx.js`, see https://github.com/syl22-00/pocketsphinx.js/blob/master/README.md.

Following are the specific for that model.

a. Loading the acoustic model

The files must be loaded in the recognizer, with a call to the "load" command and the following file names:

```javascript
data = {command: 'load', data: ["feat.params.js", "mdef.js", "means.js", "noisedict.js", "sendump.js", "transition_matrices.js", "variances.js"].map(function(x) {return "../pocketsphinx.js-en_US-hub4wsj_sc_8k/" + x;}
```

b. Initializing the recognizer

At init time, a config object that contains:

```javascript
["-hmm", "hub4wsj_sc_8k"]
```

c. Setting the sample rate

The recorder should be initialized with the correct sample rate, 8kHz:

```javascript
outputSampleRate: 8000
```

## License

These files are compiled versions of the acoustic models shipped with PocketSphinx source code. PocketSphinx licensing terms are included in the `pocketsphinx` and `sphinxbase` folders of PocketSphinx.js source repository.