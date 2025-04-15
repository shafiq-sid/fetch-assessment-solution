## Fetch Take Home Exercise

Fetch Assessment test for Site Reliability using python as a programing language.

### How to installation and Run the Code
- Download and install python from official website. [Download Python](https://www.python.org/downloads/)
- During installation, check for add python to environment variables. This will enable its usage in shell.
- Open your terminal and type python.
- Write command: `print("Hello There!") `.
- If it works fine, write: `exit()`.
- Install your favorite IDE. I'm using [Visual Studio Code](https://code.visualstudio.com/download) with some extension for better experience.
- Open project into your IDE.
- Install required dependencies named: [Requests](https://docs.python-requests.org/en/latest/index.html), [PyYAML](https://pypi.org/project/PyYAML/). Write the following command on your terminal:
```shell
pip install requests pyyaml
```
- Now your project is ready to run. Write the following command to start the app:
```shell
python monitor.py <config_file_name>.yaml
```
- If everything goes right, you should be able to see the logs with endpoints availability.

### (Optional) Setup your Virtual Environment
- #### Note: These steps should be followed right after install python and opening the project in your IDE.
-  Virtual Environments are isolated spaces where you can work on your Python projects, separately from your system-installed Python. You can set up your own libraries and dependencies without affecting the system Python. We will use [virtualenv](https://virtualenv.pypa.io/en/latest/index.html) to create a virtual environment in Python.
- Please run the following commands into your IDE terminal (where project resides):
```shell
pip install virtualenv
python -m venv <your-virtual-env-name>
cd <your-virtual-env-name>
```
- Now we have to activate virtual environment you can use the appropriate command from the table:
```shell
(Windows - Command Prompt) - path\to\venv\Scripts\activate
(Windows - PowerShell) - .\Scripts\Activate
(macOS/Linux - Bash) - source bin/activate
(macOS/Linux - Fish) - source bin/activate.fish
(macOS/Linux - PowerShell) - Scripts\Activate
```
- Now, use the virtual environment for further commands.

### Issues Identification and Fixes
- First issue found was passing Method as `NoneType` because there was no fallback method provided if there is no method in .yaml file. Fixed it passing fallback method of GET when there is none.
- (feat) Add check for 500ms or less request time for API availability. (fix) Calculated total time request takes by using `request.elapsed`. Further converting it to milliseconds and added into if condition that determines availability.