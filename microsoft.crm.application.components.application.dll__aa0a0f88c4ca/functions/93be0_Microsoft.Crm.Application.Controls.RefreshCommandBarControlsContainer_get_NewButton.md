# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_NewButton

- ea: `0x93be0`
- end: `0x93c44`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_NewButton`
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

- `0x93be0`

## string_xrefs

- `0x93c2a`: `ms-crm-Menu-ReadForm`
- `0x93be5`: `RefreshCommandBar.New`
- `0x93bf4`: `RefreshCommandBar.New`
- `0x93c0a`: `/_imgs/RefreshCommandbar/New_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93be0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93be5  ldstr    aRefreshcommand_10// "RefreshCommandBar.New"
0x93bea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93bef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93bf4  ldstr    aRefreshcommand_10// "RefreshCommandBar.New"
0x93bf9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93bfe  ldstr    aNewbutton// "newButton"
0x93c03  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93c08  stloc.0
0x93c09  ldloc.0
0x93c0a  ldstr    aImgsRefreshcom_9// "/_imgs/RefreshCommandbar/New_16.png"
0x93c0f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93c14  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93c19  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93c1e  ldloc.0
0x93c1f  ldc.i4   0xD3
0x93c24  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93c29  ldloc.0
0x93c2a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93c2f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93c34  ldloc.0
0x93c35  stloc.1
0x93c36  leave.s  loc_93C42
0x93c38  ldloc.0
0x93c39  brfalse.s loc_93C41
0x93c3b  ldloc.0
0x93c3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93c41  endfinally
0x93c42  ldloc.1
0x93c43  ret
```
