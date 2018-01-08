# Mac-Setup

This setup is heavily sided to a web development setup specifically React and NodeJS.

This was tested on MacOS High Sierra.

- [Start](#start)
- [Fonts](#fonts)
- [iTerm2](#iterm2)
- [Homebrew](#homebrew)
- [Bash](#bash)
- [Git](#git)
- [VSCode](#vscode)
- [Sublime Text](#sublime)
- [MySQL](#mysql)
- [Node](#node)
- [Ruby](#ruby)
- [Mongo](#mongo)
- [Slack](#slack)
- [Alfred](#alfred)
- [DevToolsAuthor](#devtoolsauthor)
- [Others](#others)
- [Python](#python)
- [Heroku](#heroku)
- [Thanks!](#thanks)

### Start
---
#### *Start Here Please*

First thing you need to do, on any OS actually, is update the system! For that: **Apple Icon** > **About This Mac** then **Software Update**....

"Quality of Life" changes:
- Instal XCode Suite (even if you don't need it anymore you will probably need along the road)
```bash
xcode-select --install
```
- Install [Google Chrome](www.google.com/chrome) (Make it default)
- Remove useless icons from the sidebar
- Open **Preferences** and modify these:
    - Trackpad > Tap to click
    - Keyboard > Key Repeat > Fast (all the way to the right)
    - Keyboard > Delay Until Repeat > Short (all the way to the right)
    - TrackPad > More Gestures > Activate "App Expose"
- Show battery percentage, right click battery

**👇🏼 Settings**

<div align="center">
<img src="./images/KeyboardSpeed.png" width="49%">
<img src="./images/BatteryPercentage.png" width="50%">
<img src="./images/TapToClick.png" width="49%">
<img src="./images/AppExpose.png" width="50%">
</div>


### Fonts
---
#### *Better Fonts for Development*

I like these fonts:
 - FiraCode (free) - [link](https://github.com/tonsky/FiraCode)
 - Operator Mono ($200) - [link](https://www.typography.com/blog/introducing-operator)
 - Hack (free) - [link](https://github.com/source-foundry/Hack)

Visit [Nerd Fonts](https://nerdfonts.com/) They have a long list of good programming fonts (Hot Tip: 🔥)

Operator Mono has cursive ligatures and Fira Code contains operator ligatures, to install just double clicked them and Font Book will open up.


### iTerm2
___

#### *Epic Better Console*

* Download and install [iTerm2](http://www.iterm2.com/)

* In **iTerm > Preferences...**, under the tab **General**, uncheck **Confirm closing multiple sessions** and **Confirm "Quit iTerm2 (Cmd+Q)" command** under the section **Closing**.

* In the tab **Profiles**, create a new one with the "+" icon, and rename it to your first name for example. Then, select **Other Actions... > Set as Default**. Under the section General set Working Directory to be Reuse previous session's directory. Finally, under the section **Window**, change the size to something better, like **Columns: 125** and **Rows: 35**.

* Configure oh-my-zsh with Cobalt2

Paste on a terminal to install Oh-My-Zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Install Powerline-Fonts
```bash
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

Download Cobalt2-iterm from [here](https://github.com/wesbos/Cobalt2-iterm)

Follow these instructions:

1. Drop the cobalt2.zsh-theme file in to the ~/.oh-my-zsh/themes/ directory.
2. Open up your ZSH preferences at ~/.zshrc and change the theme variable to ZSH_THEME=cobalt2.
3. In iTerm2 access the Preferences pane on the Profiles tab.
4. Under the Colors tab import the cobalt2.itermcolors file via the Load Presets drop-down.
5. Under the Text tab change the font for each type (Regular and Non-ASCII) to 'Inconsolata for Powerline'. (Refer to the powerline-fonts repo for help on font installation.)
6. Refresh ZSH by typing source ~/.zshrc on the command line.




**👇🏼 Screenshot of iTerm2 with ZSH + Inconsolata for Powerline**

<div align="center">
    <img src="./images/zsh.png"/>
</div>

* Modify starting folder on **iTerm/Preferences**

### Homebrew
___
`Package Manager for OSX`

Find the documentation and manual install here
 [Homebrew](http://brew.sh/).


* Install Homebrew on the terminal
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* One thing we need to do is tell the system to use programs installed by Hombrew (in `/usr/local/bin`) rather than the OS default if it exists. We do this by adding `/usr/local/bin` to your `$PATH` environment variable:

```bash
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
```


* Install MacOS CLI and sign in to be able to install from the store directly from the console

```bash
brew install mas
mas signin mail@mail.com
```
* Create a file called brewfile

```bash
touch ~/brewfile
```
* My Brewfile

```bash
## Required to install almost every app
tap 'caskroom/cask'

# Essentials
brew 'git'          # Essential
brew 'node'         # Essential comes with npm
brew 'zsh-completions'
brew 'tree'         # Tree Command
cask 'imageoptim'

# Browsers
# cask 'google-chrome' # Browser Installed at the beginning
cask 'firefox'       # Browser

# Coding Essentials
cask 'visual-studio-code'   # Awesomeness 🎆 💻 🎆
cask 'sourcetree'
cask 'sublime-text'         # Ultra fast 🏃


# Design Essentials
# cask 'sketch'        # Epic design tool
# cask 'noun-project'  # Free icons


# MAC Quality of life
cask 'alfred'        # Spotlight on 💊
cask 'spectacle'     # Windows Rearrangment

# Utilities
cask 'spotify'       # Music
cask 'slack'         # Chat - Work
cask 'evernote'
cask '1password'
cask 'skype'
cask 'tunnelblick'


# Cloud
cask 'google-backup-and-sync'  # Google Cloud
cask 'virtualbox'

# Coding Utilities
cask 'sequel-pro'    # SQL
cask 'vlc'           # Videos


# Others   
mas 'Amphetamine' id: 937984704 # Stop Mac from sleeping
mas 'Skitch - Snap. Mark up. Share.', id: 425955336 # Markup tools
mas 'Dr. Cleaner: Disk,Memory,System Optimizer', id: 921458519 # Clean memory and space 
```
Feel free to add or remove apps

Find the apps either on the [Cask Search Website](https://caskroom.github.io/search)
or use this on the console
```bash
brew cask search <package>
```
or use this to find apps with Mas on the console
```bash
mas search slack
```
* Install everything by running this

```bash
brew bundle install
```

* Install these apps manually
  - [Microsoft Office Suite](https://www.microsoft.com/en-ca/store/b/officeformac) (way better than the MacOS Defaults)
  - [MAMP](https://www.mamp.info/en/) for Wordpress work

### Bash
___
#### *Bash_Profile*

* Create a .bash_profile

```bash
touch ~/.bash_profile
```

* Brewup

Add useful alias

```bash
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```
Restart bash profile and run __brewup__

```bash
source ~/.bash_profile
brewup
```

Now you can run every often and it will update homebrew packages

### Git
___
#### *Configure Git and Aliases*
```bash
touch ~/.gitconfig
git config --global user.name "First Last"
git config --global user.email "Email"
git config --global credential.helper osxkeychain
```

Typical .gitconfig will look like this, be free to remove aliases 

```bash
[user]
    name = First Last
    email = email@email.com
[github]
    user = username
[alias]
    a = add
    ca = commit -a
    cam = commit -am
    s = status
    pom = push origin master
    pog = push origin gh-pages
    puom = pull origin master
    puog = pull origin gh-pages
    cob = checkout -b
[credential]
    helper = osxkeychain
```

##### *Generate a new SSH Key*
```
ssh-keygen -t rsa -C "your_email@example.com"
```
Add the key to your Github Account

Add the DS_Store to your gitignore

```bash
# specify a global exclusion list
git config --global core.excludesfile ~/.gitignore
# adding .DS_Store to that list
echo .DS_Store >> ~/.gitignore
```
Or add this [gitignore](https://github.com/github/gitignore/blob/master/Global/macOS.gitignore) file mantained by Github to your gitignore

I also like to keep my alias on the .zshrc file

Open ~/.zshrc with `code ~/.zshrc` 

Restart with `source ~/.zshrc`

These are my aliases

```bash
alias zshconfig="code ~/.zshrc" # Modify this file
alias bashconfig="code ~/.bash_profile"
alias cd..="cd .." # Most Important Alias
alias batcave="cd ~/Dropbox/batcave" # Side Projects
alias jobcave="cd ~/Projects" # 8hrs Job Projects
alias rm="trash"
alias gitlog="git log --oneline --decorate --all --graph"
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor' # Quick House Cleaning
alias youtube-dl='youtube-dl -o "%(title)s.%(ext)s' # Donwload without id
alias python="python3"
alias pip="pip3"
alias herokupush="git commit -am 'updating';git push; git push heroku master"
```

### VSCode
___
#### *Best Code Editor*

The most effective way to do this is by using [Settings-Sync Extension](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), if you haven't I highly recommend it, they way it works is by saving all your config which includes your settings, plugins, themes and snippets into your Github gist and then pulls all the data and install everything.

* Using Settings-Sync Extension

Find my config [here](https://gist.github.com/alemesa/e1d85a6d82e56872f6ddfaf73fc11537) including the UserSettings.json

Open VSCode and type "shell command" and add to the PATH. Close VSCODE, restart Terminal , now you can use any project with this

```bash
code \directory\to\open
```

I like many themes for VSCode but my favorite is [Sublime Material Theme](https://marketplace.visualstudio.com/items?itemName=jprestidge.theme-material-theme#review-details)

**👇🏼 Screenshot of Visual Studio Code with Sublime Material Theme + Operator Mono**

<div align="center">
    <img src="./images/vscode.png"/>
</div>

* Manually Installing Plugins

Some extensions I can't live without:

0. [Seti Icons]()
1. [Auto-Open Markdown Preview]()
2. [Color Highlight]()
3. [ESLint]()
4. [Guides]()
5. [Import Cost]()
6. [npm Intellisense]()
7. [Prettier]()
8. [Sublime Babel]()
9. [Terminal]()

Themes I like besides Sublime Material Theme

1. [Dracula]()
2. [Cobalt2]()

### Sublime
#### *Second Best Code Editor*

* Install Package Manager

Go [here](https://packagecontrol.io/installation)

* Follow this [guide](https://engageinteractive.co.uk/blog/getting-setup-on-sublime-text-3-2017-edition) to install theme and plugins

* Install Babel for React syntax
    - Follow this [guide](https://github.com/babel/babel-sublime)

* Be able to open sublime from the command line
    - Paste this on the command line
```bash
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime
```

* Fonts:
    - Operator Mono

**👇🏼 Screenshot of Sublime Text 3 + Operator Mono + Material Theme**

<div align="center">
    <img src="./images/sublime.png"/>
</div>

### MySQL
___
#### *...Database...*
* To install, run:

```bash
brew update # Always good to do
brew install mysql
``` 

* Setup MySQL

```bash
unset TMPDIR
mkdir /usr/local/var
mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp
```

* Usage
To start the MySQL server, use the `mysql.server` tool:
```bash
mysql.server start # start server
mysql.server stop  # stop server
mysql.server --help # find other commands
mysql -uroot # connect with the command-line client
exit # to quit the shell
```

### Node
___

* Install Node

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
nvm install node
nvm use node
node -v
```

* Add to path

To do so, add this line to your `~/.path` file, before the `export PATH` line:

```bash
PATH=/usr/local/share/npm/bin:$PATH
```

#### *npm Usage*

npm Commands:
```bash
npm install <package>    # Install locally
npm install -g <package> # Install globally
npm install <package> --save # Save to a package.json file
npm list                # What's installed Locally
npm list -g             # what's installed Globally
npm outdated [-g]       # Find outdated packages    
npm update [<package>]  # Upgrade particular package
npm uninstall <package> # Uninstall Packages
```

#### *npm Goodies*

* **Gulp**
```bash
npm install --global gulp-cli
```

* **Surge**
```bash
npm install -g surge
```
* To deploy a project
```bash
surge <path>
```

* **trash**
Instead of using `rm -r something` do `trash something`, and it will remove it to the trash folder, this is way more safe. You can add an alias too like this:

```bash
alias trash="rm -r" 
```

```bash
npm install trash
```

### Ruby

Let's install Jekyll for Github Pages

```bash
gem install jekyll # might need to run it with sudo
bundle update jekyll
gem update jekyll
```

To start a project
```bash
jekyll build # current folder will get generated inside ./_site
jekyll serve # start development
```

### Mongo

Follow this [guide](https://treehouse.github.io/installation-guides/mac/mongo-mac.html)


### Slack

* `Preferences` → `Sidebar Theme`
* [Cobalt2](https://github.com/wesbos/Cobalt2-Slack) => Paste `#193549,#FFC600,#1D425D,#FFFFFF,#FFC600,#FFFFFF,#FFC600,#FFC600` 
* Gartland => `#404040,#696969,#FFD200,#000000,#000000,#FFFFFF,#00703C,#EF4C23` 

<div align="center">
    <img width="49%" src="./images/Slack1.png"/>
    <img width="49%" src="./images/Slack2.png"/>
</div>

### Alfred

* Make Alfred substitute for Spotlight
* Install this [theme](https://github.com/wesbos/Cobalt2-Alfred-Theme) if you have the Powerpack (£19)


### DevToolsAuthor

Follow this [guide](http://mikeking.io/devtools-author/) and then select a theme on the Author Settings tab inside the Chrome Dev Tools. I'm using the `Default Theme` with `Fira Code` font and `13px` size. Small change but it makes the code more readable.

<div align="center">
    <img src="./images/devtools.png"/>
</div>


### Others

* Show hidden files, paste this on the command line
```bash
defaults write com.apple.finder AppleShowAllFiles YES
```

* Show path bar
```bash
defaults write com.apple.finder ShowPathbar -bool true
```

* Show status bar
```bash
defaults write com.apple.finder ShowStatusBar -bool true
```

### Python
---

#### *Raspberry Fun*

```bash
brew install python
```

It also installed pip (and its dependency Setuptools), which is the package manager for Python. Let's upgrade them both:

```bash
$ pip install --upgrade setuptools
$ pip install --upgrade pip
```

* If pip is not installed use this:
```bash
sudo easy_install pip
```

* To install packages with pip use:
```bash
sudo pip install foo_package --user # this will install the package on the user folder, instead that the root folder
```

### Heroku
---

#### *Heroku is a Platform-as-a-Service (PaaS) that simplifies deploying your apps online.*

**Installation**

Assuming that you have an Heroku account (sign up if you don't), let's install the Heroku Client for the command-line using Homebrew.

```bash
brew install heroku/brew/heroku
npm install -g heroku-cli
```
The formula might not have the latest version of the Heroku Client, which is updated pretty often. Let's update it now:

```bash
heroku update
```
Don't be afraid to run heroku update every now and then to always have the most recent version.

**Setup**

Login to your Heroku account using your email and password:

```bash
heroku login
```

If this is a new account, and since you don't already have a public SSH key in your ~/.ssh directory, it will offer to create one for you. It will also upload the key to your Heroku account, which will allow you to deploy apps from this computer.

If it didn't offer create the SSH key for you (i.e. your Heroku account already has SSH keys associated with it), you can do so manually by running:

```bash
mkdir ~/.ssh
ssh-keygen -t rsa
```
Keep the default file name and skip the passphrase by just hitting Enter both times. Then, add the key to your Heroku account:

```bash
heroku keys:add
```
Usage

Once your keys are in place and you are authorized, you're ready to deploy apps. Heroku has a getting started [guide](https://devcenter.heroku.com/articles/python). Heroku uses Git to push code for deployment, so make sure your app is under Git version control.

**A cheat sheet for deployment**:

```bash
cd myapp/
heroku create myapp
git push heroku master
heroku ps
heroku logs -t
```
The Heroku Dev Center is where you will find more information.

### Thanks
---

Inspired by these posts:
* [Mac Dev Setup](https://github.com/nicolashery/mac-dev-setup) by [nicolashery](https://github.com/nicolashery/)
* [Setting up a brand new mac](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/) by [Tania Rascia](https://www.taniarascia.com)
* [Mac Setup](http://sourabhbajaj.com/mac-setup) by [sourabhbajaj](http://sourabhbajaj.com)
* Big thanks to [WesBos 🍖](http://wesbos.com/) because I use everything he uses, he's pure 🔥🔥🔥 


