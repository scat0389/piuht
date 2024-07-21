# My Habit Tracking App

## Description
This habit tracking app allows the user to keep track of any habits they wish to form. 
It is used via a Command-Line Interface; while habit creation requires typed user input, the rest 
of the app is largely controlled by selecting from options using the arrow keys. 

The database contains a number of pre-defined daily and weekly habits and 'streaks' of habit completions events (check-offs), which allows users to explore 
the options provided by the app. All of these can be deleted by choosing the 'Delete Habits'-option from the menu, which 
deletes not only the habit itself, but all associated check-off events. 

Habit creation asks the user to decide whether the habit is to be performed daily or weekly. When a habit is 
checked off by the user, the program checks whether more than the specified period of time has been elapsed since the last time the 
habit was completed. At this point, some leniency is built into the app;
daily habits are considered to have been completed within the specified period if no more than 27 hours have passed since the last
check-off for the habit, while weekly habits allow up to ten days for habit completion without breaking the streak. In future updates, 
users are to be given the option to specify how lenient the app is to be in checking whether a habit has been repeated on time. 

Successive on-time completions of habits are termed streaks, and the app not only provides the count of the current streak 
as feedback immediately upon check-off, it also allows the user to perform a variety of analyses, such as listing or counting habits,
calculating the longest overall streak, the longest streak for a given habit or a given periodicity, average streak length etc. 
Future updates may add functions such as length of intervals between streaks, or calculate longest streaks for a user-defined period, such as the last month.



## Installation

Once you have obtained the habit_tracker-1.0.0.tar.gz or .zip file, unpack it to a newly
created folder. 

Then install a virtual Python environment into the same folder from the command line. For Windows, make sure your python.exe is
in the default PATH, which is an install option for the default Python.org installers for Windows.

The code is:

```shell
# Linux and macOS:
python -m venv habit_tracker-1.0.0
source habit_tracker-1.0.0/bin/activate
python -m ensurepip
cd habit_tracker-1.0.0
pip install -r requirements.txt
cd src/habit_tracker
```

```shell
REM Windows: open a cmd.exe console window
python.exe -m venv habit_tracker-1.0.0
habit_tracker-1.0.0/Scripts/activate.bat
python.exe -m ensurepip
cd habit_tracker-1.0.0
pip install -r requirements.txt
cd src\habit_tracker
```

then continue under ...

## Usage

Start

```shell
python main.py
```
and follow instructions on screen.

## Tests

The program include a test suite with predefined habits and tracker events. The functionality of the app can be 
tested as follows.

Open a console shell and cd to the `habit_tracker-1.0.0` directory.
Then activate the virtual environment by executing only the line containing _activate_ 
from the installation instructions above, for macOS or Linux:

```shell
source bin/activate
pytest tests
```

For Windows:


```shell
Scripts\activate.bat
pytest tests
```

## Recreating the distribution:

```shell
pip install hatch
hatch build
```
