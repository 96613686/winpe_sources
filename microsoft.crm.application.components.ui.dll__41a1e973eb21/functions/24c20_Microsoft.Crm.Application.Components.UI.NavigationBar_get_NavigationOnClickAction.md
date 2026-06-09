# Microsoft.Crm.Application.Components.UI.NavigationBar::get_NavigationOnClickAction

- ea: `0x24c20`
- end: `0x24c26`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::get_NavigationOnClickAction`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x24a50`
- `0x24da0`

## string_xrefs

- `0x24c20`: `\n						var navBar = $find({0}); \n						navBar && navBar.sideStripOnClick(); \n						return false;`

## pseudocode

```c

```

## disassembly

```asm
0x24c20  ldstr    aVarNavbarFind0// "\r\n\t\t\t\t\t\tvar navBar = $find({0})"...
0x24c25  ret
```
