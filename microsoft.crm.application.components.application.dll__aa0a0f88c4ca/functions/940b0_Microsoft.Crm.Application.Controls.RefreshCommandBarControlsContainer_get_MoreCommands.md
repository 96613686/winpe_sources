# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_MoreCommands

- ea: `0x940b0`
- end: `0x940f5`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_MoreCommands`
- size: `69`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x92e20`
- `0x93070`
- `0x932c0`
- `0x936a0`

## callees

- `0x940b0`

## string_xrefs

- `0x940ba`: `RefreshCommandBar.MoreCommands.ToolTip`
- `0x940c4`: `moreCommandsButton`
- `0x940d0`: `$find("readFormToolBar").get_moreMenu().processAndShowMenu()`
- `0x940db`: `ms-crm-Menu-ReadForm ms-crm-Menu-moreCommandsButton`

## pseudocode

```c

```

## disassembly

```asm
0x940b0  ldstr    asc_F5D88// "..."
0x940b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x940ba  ldstr    aRefreshcommand// "RefreshCommandBar.MoreCommands.ToolTip"
0x940bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x940c4  ldstr    aMorecommandsbu// "moreCommandsButton"
0x940c9  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarPopupButton::.ctor(string, string, string)
0x940ce  stloc.0
0x940cf  ldloc.0
0x940d0  ldstr    aFindReadformto// "$find(\"readFormToolBar\").get_moreMenu"...
0x940d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x940da  ldloc.0
0x940db  ldstr    aMsCrmMenuReadf_1// "ms-crm-Menu-ReadForm ms-crm-Menu-moreCo"...
0x940e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x940e5  ldloc.0
0x940e6  stloc.1
0x940e7  leave.s  loc_940F3
0x940e9  ldloc.0
0x940ea  brfalse.s loc_940F2
0x940ec  ldloc.0
0x940ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x940f2  endfinally
0x940f3  ldloc.1
0x940f4  ret
```
