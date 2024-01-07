# Tested on MacOS M1 Fedora 39 docker container


```bash
# Start container
docker run -ti --rm fedora /bin/bash

# Will install neovim 0.9
dnf install -y neovim python3-neovim

# Clone kikstart config file
git clone https://github.com/nvim-lua/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim

# Install zsh and plugins
dnf install -y zsh git tmux fzf gcc wget

# Install ohmyzsh
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

# Clone zsh autougestions 
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Add pluggin
nvim ~/.zshrc 
plugins=(git zsh-autosuggestions)

# Save the state of the container by running the following command:
docker commit -p container_id new_container_name

```

# Dotfile backup and management to github

```bash
# Install chezmoi for dotfale managemet
dnf install https://github.com/twpayne/chezmoi/releases/download/v2.43.0/chezmoi-2.43.0-aarch64.rpm

# Basic startup how to backup dotfiles including encrypt secrets using pass
https://fedoramagazine.org/take-back-your-dotfiles-with-chezmoi/
```


```bash
# TODO: add dot file mangement
1. Git clone zchrc , tmux.conf , nvim config in correct locations

# Seems you cannot connect using ssh to Fedora docker so ansible configurations need to be done using real VM.  
```
