# Dotsible

This is an Ansible template for syncing your dotfiles repository across multiple
servers, including your local machine. It processes dotfiles in the j2 template via
Ansible's `template` module.

# Requirements

Ansible 1.3 or higher is required. This is currenly kind of hacky (see `site.yml`) and
may break with future Ansible releases.

# Usage

Clone dotsible to your machine, `cd` into it and run `./sync`. It will copy the inventory example
and instruct you to clone your dotfiles repo.

Once you have a dotfiles repo in the `dotfiles` directory, `sync` will recursively copy all files
and directories to the `~/` directory on all servers under the `[managed]` block within `my-inventory`.

Within your dotfiles, you may use Ansible/j2 tags, such as `{{ inventory_hostname }}`, which could be
useful in customizing prompts.

# Contribute

If you find this interesting, please leave feedback in the GitHub issues. Thanks!
