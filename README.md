# Juliet

At the moment, I am beginning to port this over from my Otto3 repository on Github.  Google's gTTS has a female voice; so calling her Otto makes no sense.  It's also an opportunity to refactor my code, and cleanup the installation process. That means this repo is not ready for prime time.  That being said, if you can set up your environment correctly, this code does work and works well -- on my computer at least.

Juliet answers to any name starting Juli.  So you can say "Julie Help," or "Juliet Help," or "Julius Help."  However "Julie Julie Help" works best. ;) 

Virtual Assistant with STT and TTS

Juliet requires quite a few packages and programs to run as well as some customization for your system, for exampe, where your songs are. I've built Juliet on Ubuntu 18.04.  I have a modern Logitek Webcam and integrated microphone, but any microphone should work.  The pyaudio program is used to access the microphone.  I recommend doing everything inside a virtual environment.  I use miniconda.  BTW, I am programming this at home.  I don't have a team, and I don't have a lab with multiple systems with different linuxes and different hardware.  I have a lot of programs and modules installed.  I don't know how my particular system is effecting this program as a unique environment.  Therefore, I'd be very interested in hearing about your experiences.  You can create a Github issue in this repository to leave your experiences.  

I've noticed that some modules are not showing up in my Juliet.yaml file, so check all the import statements in Juliet.py as well as all the submodules like initializejuliet.py and the modules in the GreyMatter and SpeakAndHear subdirectories. You can manually pip install them into your virtual environment.  

Juliet requires git and python3. I use miniconda to create a virtual environment. On my own system, I create a directory.  You should fork my repository,  Then clone your fork. 
  
   sudo apt install git
  
   mikdir ~/Code
   
   cd ~/Code
   
   git clone Insert your url of the forked repository here  
  
   it should look something like this:  
  
  https://github.com/MikeyBeez/Juliet.git
  
  cd Juliet

I make a conda environment from the included yaml file. I'm using python 3.6.1  There are probably more modules here than you need.  In any case, create a virtual environment any way you want, with virtualenv, Venv, Anaconda, or Miniconda.  I used Miniconda because it doesn't mess up Lambda Lab's Lambda Stack. 
  
  conda env create --file=Juliet.yaml
  
I need to cleanup this yaml file.  It has all my site packages too.
The frustrating part is that I will need to set this up from scratch in a virtual machine before it's ready for the wild.  Then I can prune this down to the minimum.   

I built kaldi from source.  I still don't know if this step is required.  vosk may have everything that's needed.  If you do build kaldi, I have a video to help do that.  It will point you to the kaldi tutorial and installation docs.  I recommend reading the kaldi git tutorial before you start, so that you fork and then clone properly.  
https://www.youtube.com/watch?v=Kky-mdzYLq4

You also need to clone vosk-api so that you'll have the demo code.  Get it on github.  Pypi has the right repo, so look there for the url.  

The vosk module for python is installed with pip3.  It's in the yaml file; so you shouldn't need to do this.  "pip list| grep -i vosk"  will show you if it's installed.  I install pip3 models this way: 

python3 -m pip install vosk

I've included a file called mymusiclist.txt that has paths to mp3 files.  This file is for music on an example system.  It shows how filenames need to be formated and "escaped."  To play your own mp3 files, create your own list of files and call it mymusiclist.txt.   

