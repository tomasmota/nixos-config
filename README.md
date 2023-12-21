# NixOS and home Config

## Setup

### Make sure nix is installed
`curl --proto '=https' --tlsv1.2 -sSf -L https://install.determinate.systems/nix | sh -s -- install`

### If this is a new machine, set up github authentication
```
ssh-keygen -t ed25519 -C "mail@example.com"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519
*add key to github*
```

### Clone this repo into .config
`git clone git@github.com:tomasmota/nixos-config.git ~/.config/nixos-config`

### Init home-manager
`nix run home-manager/master -- init --switch ~/.config/nixos-config`

### Set zsh as shell
`echo ~/.nix-profile/bin/zsh | sudo tee -a /etc/shells`

`chsh -s (which zsh)`  

## Add secrets to secrets.env, at the root of this repo

## TODO:

### home-manager
- fix auto commit message
- add alacritty config
- use lazy.nvim
- fix Cody

### nixos
- adapt readme for setting up nixos machine
