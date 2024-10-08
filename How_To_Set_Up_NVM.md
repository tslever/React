# How To Set Up `nvm`

## Linux

To install nvm (https://github.com/nvm-sh/nvm), run `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash`.

Restart terminal or run `source ~/.bashrc`.

Install Node.js by running `nvm install <version (e.g., 20.16.0)`.

## Windows

Due to error in cloning Git repository Node Version Manager on Windows, use a combination of PowerShell, Windows Subsystem for Linux, and Git Bash.

In PowerShell, run `wsl --install`.

In WSL, run `git clone https://github.com/nvm-sh/nvm.git /mnt/c/Users/tlever/.nvm`.

In Git Bash, run `nano ~/.bashrc` and enter the following:

```
export NVM_DIR="/c/Users/tlever/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

In Git Bash:

Run `source ~/.bashrc`.

Run `nvm install 16.14.2` to install Node version 16.14.2 and Node Package Manager version 8.5.0.

To set Node version 16.14.2 as default, run `nvm alias default 16.14.2`.

To switch to Node version 20.11.0, run `nvm use 20.11.0`.

To switch back to default Node version, run `nvm use default`.

To uninstall Node version 20.11.0, run `nvm uninstall 20.11.0`.

To uninstall Node Version Manager, run `nvm unload`.

To switch to system Node version, run `nvm use system`.

To use a project-specific Node version, run the following:

```
cd ~/Documents/R3L/SKEO.R3L.Web
echo "16.14.2" > .nvmrc
cat .nvmrc
nvm alias default 20.11.0
nvm use default
node --version
nvm use
node --version
nano hello.js and console.log('Hello World');
node hello.js
rm hello.js
```

Considering adding `"terminal.integrated.defaultProfile.windows": "Git Bash"` to Visual Studio Code -> Ctrl+Shift+P -> Preferences: Open User Settings (JSON) to have Visual Studio use Git Bash with nvm sourced.
