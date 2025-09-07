# Columns of Pixels from Films.
What would it look like if you took the same column of pixels from every frame of a film and lined them up? 

## First, How did I create this? 
I've had this idea for the longest time. Then today, like a bolt of lightning, it occurred to me this should be something FFMpeg should be able to do, and rather quickly. 

Here is the script:
```
ffmpeg -noautorotate -y -i /Volumes/testfiles/The\ Matrix\ \(1999\)\ \[1080p\]/The.Matrix.1999.mp4  -frames 1 -vf "select=between(n\,0\,65499),crop=1:ih:x=iw-1:y=0:exact=1,tile=65499x1" lastcolumnframe-TheMatrix_tri_1.jpg
```
First we get 65499 frames (JPEG spec says you cannont have an image over 65500). We crop each frame to be 1 pixel wide, and whatever the height of the video. We then take the pixel column and tile them one after the next. 
We end up with an image that is composed of the pixels of the last column of each frame. 

I chose two movies to illustrate what is happening.

Koyaanisqatsi for its visuals

[Koyaanisqatsi Pt1](https://raw.githubusercontent.com/squeevey/ColumnPixelsFromFilms/refs/heads/main/lastcolumnframe-Koyaanisqatsi-1.jpg)

[Koyaanisqatsi Pt2](https://raw.githubusercontent.com/squeevey/ColumnPixelsFromFilms/refs/heads/main/lastcolumnframe-Koyaanisqatsi-2.jpg)

The Matrix for its unique cinematic identity. 

[Matrix 1 1 of3](https://raw.githubusercontent.com/squeevey/ColumnPixelsFromFilms/refs/heads/main/lastcolumnframe-TheMatrix_tri_1.jpg)

[Matrix 1 2 of 3](https://raw.githubusercontent.com/squeevey/ColumnPixelsFromFilms/refs/heads/main/lastcolumnframe-TheMatrix_tri_2.jpg)

[Matrix 1 3 of 3](https://raw.githubusercontent.com/squeevey/ColumnPixelsFromFilms/refs/heads/main/lastcolumnframe-TheMatrix_tri_3.jpg)
