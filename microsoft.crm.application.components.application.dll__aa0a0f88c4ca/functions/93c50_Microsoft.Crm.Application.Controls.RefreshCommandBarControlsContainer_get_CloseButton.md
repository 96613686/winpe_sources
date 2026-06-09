# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_CloseButton

- ea: `0x93c50`
- end: `0x93cb4`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_CloseButton`
- size: `100`
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

- `0x93c50`

## string_xrefs

- `0x93c9a`: `ms-crm-Menu-ReadForm`
- `0x93c55`: `RefreshCommandBar.Close`
- `0x93c64`: `RefreshCommandBar.Close`
- `0x93c7a`: `/_imgs/RefreshCommandbar/Close_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93c50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93c55  ldstr    aRefreshcommand_11// "RefreshCommandBar.Close"
0x93c5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93c5f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93c64  ldstr    aRefreshcommand_11// "RefreshCommandBar.Close"
0x93c69  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93c6e  ldstr    aClosebutton// "closeButton"
0x93c73  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93c78  stloc.0
0x93c79  ldloc.0
0x93c7a  ldstr    aImgsRefreshcom_10// "/_imgs/RefreshCommandbar/Close_16.png"
0x93c7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93c84  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93c89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93c8e  ldloc.0
0x93c8f  ldc.i4   0xDB
0x93c94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93c99  ldloc.0
0x93c9a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93c9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93ca4  ldloc.0
0x93ca5  stloc.1
0x93ca6  leave.s  loc_93CB2
0x93ca8  ldloc.0
0x93ca9  brfalse.s loc_93CB1
0x93cab  ldloc.0
0x93cac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93cb1  endfinally
0x93cb2  ldloc.1
0x93cb3  ret
```
