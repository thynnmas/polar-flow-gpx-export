# Polar Flow HTML to GPX convertor

***
## About
[@jan_schmid](https://www.twitter.com/jan_schmid) got himself a new Polar V800 this year, which means his old Garmin was destined to fall upon me. However, our primary use of the GPS function is to import the data into [QuickRoute](http://www.matstroeng.se/quickroute/en/) to analyze orienteering races, and as it turns out, the V800 uses the new Polar Flow instead of the old Pro Trainer. Flow does not yet support exporting the GPS data, however it loads it all into the webapp to overlay it onto google maps. So, naturally, I wrote a small python script that parses that data and writes it into the QuickRoute-supported [Global Position eXchange](http://www.topografix.com/gpx.asp) format. The script is here, and below.
It must be noted that this just parses the HTML/JS of the webapp, and does so in a very hacky way. It is likely that it will break if Polar change anything on their side. When that happens, Jan will probably expect me to update it, but that happening is far from guaranteed. If you find any other bugs in it, feel free to use whatever github's way of notifying me is, or email bugs(alfa)schmidx2(dt)com.

## Instructions
1. Install Python. You want Python 2, whichever the newest version is for your architecture (at time of writing that is 2.7.8).
2. In the script, find the line that says NAME = 'Runner' (line 53) and replace Runner with your name.
3. In Polar Flow, navigate to the excercise you want to export.
4. Now you have two alternatives,
The easy way:
1. Drag the url onto the script
2.3 The GPX file is now located in the script's folder as out.gpx
The hard way:
1. Press Ctrl+U, Ctrl+S (in firefox and chrome at least) to download the source of the page.
2. Open the command line (CTRL+R -> cmd -> enter) and run python polar_export.py [downloaded file]. If python is not found (meaning python is not in your environment variables),find python.exe and use the full path, typically (Windows, x86) "C:\Program Files\Python27\python.exe" [qualified path to script] [qualified path to file].
3.The GPX file is now in the folder the downloaded file is in with teh same name (but gpx file extension).

