# Yongil's dotfiles

## Contents

- vim (Neovim) config
- powershell config

## Neovim requirement

- [vim-plug](https://github.com/junegunn/vim-plug.git) - Vim plugin

## PowerShell requirement

- [Nerd font](https://github.com/ryanoasis/nerd-fonts) - Hack nerd font familty
- [Scoop](https://scoop.sh/) - A command-line installer
- [Git for Windows](https://gitforwindows.org/) - Git for windows
- [Oh My Posh](https://ohmyposh.dev/) - Prompt theme engine
- [Terminal Icons](https://github.com/devblackops/Terminal-Icons) - Folder and file icons
- [PSReadLine](https://docs.microsoft.com/en-us/powershell/module/psreadline/) - Cmdlets for customizing the editing environment, used for autocompletion
- [z](https://www.powershellgallery.com/packages/z) - Directory jumper
- [PSFzf](https://github.com/kelleyma49/PSFzf) - Fuzzy finder
- [Make](https://gnuwin32.sourceforge.net/packages/make.htm) - Make for windows

## PowerShell setup

1. Install Hack nerd font family in Windows system
2. Install PowerShell in Microsoft store
2. Set default terminal application to "Windows Terminal" in Terminal setting startup tab
3. Set acrylic tab row to "On" in Terminal setting appearance tab
4. Set color scheme to "One Half Dark" in Terminal setting defaults-appearance tab
5. Set font face to "Hack Nerd Font" in Terminal setting defaults-appearance tab
6. Set enable acrylic to "On" and set opacity to "to" in Terminal setting defaults-appearance tab
7. Open a powershell setting json, copy and paste to my git setting.json
8. Install Scoop(Command-line installer)
    ```
    iwr -useb get.scoop.sh | iex
    ```
    ```
    scoop install curl sudo jq
    ```
    ```
    curl 'https://api.inkdrop.app/' | jq .
    ```
9. Install git for windows
    ```
    winget install -e --id Git.Git
    ```
10. Install oh-my-posh
    ```
    Install-Module posh-git -Scope CurrentUser -Force
    ```
    ```
    Install-Module oh-my-posh -Scope CurrentUser -Force
    ```
    ```
    winget install JanDeDobbeleer.OhMyPosh -s winget
    ```
11. Copy powershell directory in my git in USER\.config
12. Install Terminal Icons
    ```
    Install-Module -Name Terminal-Icons -Repository PSGallery -Force
    ```
13. Install z - Directory jumper
    ```
    Install-Module -Name z -Force
    ```
14. Install PSReadLine - Autocompletion
    ```
    Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
    ```
    - Set PSReadLineOption
        ```
        Set-PSReadLineOption -PredictionSource History
        ```
        ```
        Set-PSReadLineOption -PredictionViewStyle ListView
    ```
15. Install Fzf - Fuzzy finder
    ```
    scoop install fzf
    ```
    ```
    Install-Module -Name PSFzf -Scope CurrentUser -Force
    ```
    - Set PsFzfOption
        ```
        Set-PsFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineChordReverseHistory 'Ctrl+r'
        ```

## Neovim setup

1. Copy and paste nvim directory in user\AppData\Local
2. Install visual studio 2022 
3. Install vim-plugin
``
iwr -useb https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim |`
    ni "$(@($env:XDG_DATA_HOME, $env:LOCALAPPDATA)[$null -eq $env:XDG_DATA_HOME])/nvim-data/site/autoload/plug.vim" -Force
``
4. Install NodeJS
``
winget install -e --id OpenJS.NodeJS
``
5. Install NVM
``
scoop install nvm
``
6. Move directory to coc.nvim
``
cd $PROFILE\AppData\Local\nvim-data\plugged
``
7. Build coc
``
npm install
``
8. Open a vim and coc install clangd
``
CocInstall coc-clangd
``
9. Install LLVM

