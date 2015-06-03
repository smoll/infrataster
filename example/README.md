# Infrataster Example

```
$ cd example
$ bundle install
$ bundle exec berks vendor vendor/cookbooks
$ vagrant up
$ bundle exec rspec
```

## Troubleshooting

If `vagrant up` fails due to berks failing to execute, e.g.

```
The following berks command failed to execute:

    /Users/myusername/.rvm/gems/ruby-2.2.0/bin/berks --version --format json

# ...
```

make sure you have ChefDK installed (`$ chef --version`), and that `which berks` points to the install prepackaged with ChefDK and not the one that comes in this Gemfile...

```
$ which berks
/Users/myusername/.rvm/gems/ruby-2.2.0/bin/berks # no good

$ PATH=/opt/chefdk/bin:$PATH
$ which berks
/opt/chefdk/bin/berks # good
```

Related issue here: https://github.com/berkshelf/vagrant-berkshelf/issues/264
