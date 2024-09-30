## Usage

```powershell
Start-BitsTransfer -Source "https://raw.githubusercontent.com/urob/dotfiles-win/main/boot.ps1"; .\boot.ps1
```

## Troubleshooting

If you get an error message like `File boot.ps1 cannot be loaded because running scripts is disabled on this system.`, you need to enable a
[less restrictive script execution policy](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies). E.g.

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## Todo

```powershell
# this doesn't work b/c windows terminal dynamically adds WT_SESSION and WT_PROFILE to WSLENV
# setx WSLENV "${env:WSLENV}:USERPROFILE/up"
# this isn't great either, b/c it overwrites the existing WSLENV. Better would be to append ignoring WT_VARIABLES
setx WSLENV "USERPROFILE/up"
```
