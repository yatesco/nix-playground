Trying to get a dev environment set up that can run `prettier` with a bunch of plugins.

I cannot state this enough - I am a nix-newbie. Monkeys throwing bricks at keyboards might produce a more idiomatic nix flake than this...

Steps:
 1. cd into this directory
 2. `nix develop`
 3. `prettier example.toml --check --plugin="prettier-plugin-toml"`

 This currently shows:
 ```
 nix-playground/prettier-plug-plugin on  main [+]
 ❯ nix develop
 warning: Git tree '/Users/coliny/Dev/nix-playground' is dirty
 bash-5.2$ prettier example.toml --check --plugin=prettier-plugin-toml
 [error] Cannot find package 'prettier-plugin-toml' imported from /Users/coliny/Dev/nix-playground/prettier-plug-plugin/noop.js
 bash-5.2$
```

it should successfully find the plugin.

The plugin is "there" (for some definition of 'there'):
```
bash-5.2$ node
Welcome to Node.js v20.15.1.
Type ".help" for more information.
> require ('prettier-plugin-toml')
{
  languages: [
    {
      name: 'TOML',
      aceMode: 'toml',
      since: '0.1.0',
      parsers: [Array],
      linguistLanguageId: 365,
 <snip>
 ...
```

so I don't really know what's going on.
