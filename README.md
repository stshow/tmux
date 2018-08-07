Tmux configs

For powerline:

1.  Copy `tmux-powerline.conf` to `~/.tmux.conf`
2.  Edit `default.json` to contain your city/state. 
3.  Copy `default.json` to `<powerline-root>/powerline/config_files/themes/tmux` (e.g. `/usr/lib/python3.6/site-packages/powerline/config_files/themes/tmux/`) Alternatively, if `$XDG_CONFIG_DIRS` is set, put the files in the appropriate folders. See: http://powerline.readthedocs.io/en/master/configuration.html
4.  Add `bashrc-tmux-func` to your bashrc to have ssh host displayed in the window tab. 


Workaround for systemd closing tmux sessions in bashrc: 

```
## Adding `KillUserProcesses=no` to /etc/systemd/logind.conf doesn't 
## seem to work after `systemctl restart systemd-logind`. Could require reboot to spawn additional procs.
## One suggestion is to: `loginctl enable-linger <user>`, but might require reboot.
## See: https://askubuntu.com/questions/802189/how-to-run-tmux-screen-with-systemd-230
alias tmux='systemd-run --remain-after-exit tmux'
```
