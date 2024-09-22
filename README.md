<div align="center">

# gitportal.nvim
#### Bridging the gap between your favorite git host and neovim.


<img alt="Git Portal" height="175" src="/assets/gitportal-icon.png" />
</div>

# 🚧 UNDER CONSTRUCTION 🚧
#### This plugin is not complete. You can track my progress here with this [milestone](https://github.com/trevorhauter/gitportal.nvim/milestone/1). 
#### Current expected release date: October 1st, 2024.

## ꩜ Use cases
#### You want to quickly share a file with a coworker 
- `gitportal` will automatically open your current file in github, including any selected lines in the permalink.

#### A coworker shares a file with you 
- `gitportal` will accept shareable permalinks, switch to the proper commit or branch, open the file, and go to or highlight any relevant lines embedded in the permalink.

## ꩜ Supported git web hosts
- [GitHub](https://github.com/)

NOTE: Support for additional hosts will be added after release.

## ꩜ Features currently available
- Automatically open your current file in GitHub, includes the selected line(s) in the permalink.
- Link ingestion is not currently available.

WARNING: If you use this plugin before release, it is likely you will run into bugs. If you do, please open a github issue and I will do my best to resolve it ASAP.

## ꩜ Installation
- [lazy.nvim](https://github.com/folke/lazy.nvim)
```lua
{ 'trevorhauter/gitportal.nvim' }
```

## ꩜ Basic setup
Here is how I have gitportal currently set up
```lua
local gitportal = require("gitportal.core")

-- In normal mode, `open_file_in_browser()` opens the current file in your browser on the correct branch/commit.
vim.keymap.set("n", "<leader>gp", function() gitportal.open_file_in_browser() end)

-- In visual mode, `open_file_in_browser()` behaves the same but it also includes the selected line(s) in the permalink.
vim.keymap.set("v", "<leader>gp", function() gitportal.open_file_in_browser() end)

-- open_file_in_neovim accepts a github link, switches to the correct branch/commit, and opens the specified file.
vim.keymap.set('n', '<leader>ig', function()
    gitportal.open_file_in_neovim(vim.fn.input("Github link > "));
end) 

```
