# Avoid being prompted for password

Being prompted for password on every **Git** operation can get tiresome in the long run.

```bash
$ ssh-add ~/.ssh/id_rsa 
```

Enter your pasphrase and you should be good to go. If you want to automate even more, check out `ssh-agent`:

Add the following smippet to your `.bash_profile`.

```bash
if [ -z "$SSH_AUTH_SOCK" ] ; then
  eval `ssh-agent -s`
  ssh-add
fi
```

These are general `ssh` tricks, so they can be used in other cases where `ssh` is put to use.

Source [StackOverflow: ssh-add](https://stackoverflow.com/questions/21095054/ssh-key-still-asking-for-password-and-passphrase)

Source [StackOverflow: ssh-agent](https://unix.stackexchange.com/questions/90853/how-can-i-run-ssh-add-automatically-without-password-prompt)
