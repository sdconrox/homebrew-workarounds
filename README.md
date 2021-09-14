# homebrew-workarounds

Homebrew tap to workaround missing security checks, restrictions, nuances, nuisances, etc.

***NOTE:*** Any software installed using the code installed using the code in this repository is governed by its respective License. If you maintain any code that I've refernced and have any concerns, please feel free to reach out via issue or email.

## Usage

    brew tap sdconrox/workarounds
    brew update # Optional as this should happen automatically
    brew install sdconrox/workarounds/<formula_name>

## 🧪 Formulae

### 🔑 sshpass

If you're here for sshpass, please note that this is the least secure way to do absolutely anything over ssh. Makse sure setting up passwordlass auth is at least on your TODOs, if at all possible. 

#### Installation

    brew tap sdconrox/workarounds # if not already tapped
    brew install sdconrox/workarounds/sshpass

## ssh-keygen reference, in case it helps:

### Generating a key

#### 👩‍💻🧑‍💻 Interactive

    ssh-keygen -f "~/.ssh/id_rsa"

#### 👩‍💻🧑‍💻 Interactive (✨Fancy✨)

    ssh-keygen -t rsa -b 4096 -f "~/.ssh/id_rsa" -C "$(id -un)@$(uname -n)"

#### 🤖👾 Non-interactive

***NOTE:*** Sets a blank passphrase on the key so be sure to add one after the script runs with `ssh-keygen -p -f keyfile`

    ssh-keygen -q -t rsa -b 4096 -f "${ssh_defaults[key_user]}" -C "$(id -un)@$(common_os_alias).$(common_host_alias).${underverse_info[domain]}" -P ''

### Copying the key to a remote system

    ssh-copy-id -i "~/.ssh/id_rsa" remote_user@remote_host

## 📚 References

### ssh manuals (run locally, if installed)

  man ssh
  man ssh-keygen
  man ssh-copy-id

### Homebrew Documentation
* [Taps (Third-Party Repositories) — Homebrew Documentation](https://docs.brew.sh/Taps "Taps (Third-Party Repositories) — Homebrew Documentation")

### Inspiration
* [kadwanev/bigboybrew: Homebrew Formulas for big boys](https://github.com/kadwanev/bigboybrew "kadwanev/bigboybrew: Homebrew Formulas for big boys")
