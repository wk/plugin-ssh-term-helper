![][license-badge]

<div align="center">
  <a href="http://github.com/oh-my-fish/oh-my-fish">
  <img width=90px  src="https://cloud.githubusercontent.com/assets/8317250/8510172/f006f0a4-230f-11e5-98b6-5c2e3c87088f.png">
  </a>
</div>
<br>

# ssh-term-helper

[Oh My Fish][omf-link] plugin that overloads the ssh command
to set a conversative $TERM value

Due to inconsistency of 256 color terminal support across
terminal applications, it may be desirable to force the
$TERM value to its -256color variant.

For example, this is often accomplished in tmux by means
of adding the following to a tmux.conf file:

    set -g default-terminal "screen-256color"

Unfortunately, remote hosts accessed via ssh may not have
the requisite terminfo files, and may not even allow the
user to supply them, as is often the case with network
equipment and other appliances accessible via ssh.

This helper strips the -256color suffix and exports a
regular 'screen' or 'xterm' $TERM value when setting up
a ssh connection.

## Install

```fish
$ omf install ssh-term-helper
```

## Usage

```fish
$ ssh [arguments]
```

ssh-term-helper overloads the 'ssh' command and changes the
value of $TERM to a conservative setting present in most
termcap files. Any arguments are passed directly to the ssh
command.

# License

[MIT][mit] © [wk][author] et [al][contributors]


[mit]:            http://opensource.org/licenses/MIT
[author]:         http://github.com/wk
[contributors]:   https://github.com/wk/pkg-ssh-term-helper/graphs/contributors
[omf-link]:       https://www.github.com/oh-my-fish/oh-my-fish

[license-badge]:  https://img.shields.io/badge/license-MIT-007EC7.svg?style=flat-square
