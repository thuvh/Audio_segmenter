# Audio Segmenter
Python script to splice audio files to 5 second intervals, as well as normalize amplitude, channel, sampling rate; and lastly removing unnesscary silences. Used to preprocess raw audio data for machine learning

## If you need to find the optimal parameters for removing silence in your audio:
1. Open parameter_tester.ipynb. This script will take a sample of your original file, which can be used to test and find the optimal silence length and threshold.

2. Run the first cell to splice a sample of your original raw audio data.

3. Adjust the parameters in `nonsilent_data = detect_nonsilent(normalized_sound, min_silence_len=4000, silence_thresh=-32, seek_step=1)`, then run the cell. It should output a series of time frames, for example:

![Time frame](https://github.com/Caldarie/Audio_segmenter/blob/master/Images/Screen%20Shot%202020-07-31%20at%209.39.55%20pm.png)

4. Run the third cell to output wave graph. 

5. Using the wave graph, make sure that it matches with the time frame from the second cell. If it doesn't match, readjust the parameters again. Optimal parameters should match the time frames like this:
![Wave Graph](https://github.com/Caldarie/Audio_segmenter/blob/master/Images/Screen%20Shot%202020-07-27%20at%2011.04.38%20pm.png)

# If you just want to splice the audio files:
The first cell is for normalizing audio and removing silence gaps. The second cell splits all audio files into 5 second intervals
1. Adjust the paremeters before running the cell. These are:
  a) For silence: `mini_silence_len` and `silence_thresh`
  b) For intended audio length, it is `target_length`
  c) If you don't wish to adding padding. Just remove comment remove 'silence_chunk` from `padded_normalized_chunk = normalized_chunk + silence_chunk`
  

