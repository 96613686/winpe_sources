# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Delete

- ea: `0x93e60`
- end: `0x93ec0`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Delete`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x92e20`
- `0x93070`
- `0x932c0`
- `0x936a0`

## callees

- `0x93e60`

## string_xrefs

- `0x93ea6`: `ms-crm-Menu-ReadForm`
- `0x93e65`: `RefreshCommandBar.Delete`
- `0x93e74`: `RefreshCommandBar.Delete`
- `0x93e7e`: `deleteButton`
- `0x93e8a`: `/_imgs/RefreshCommandbar/Delete_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93e60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93e65  ldstr    aRefreshcommand_14// "RefreshCommandBar.Delete"
0x93e6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93e6f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93e74  ldstr    aRefreshcommand_14// "RefreshCommandBar.Delete"
0x93e79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93e7e  ldstr    aDeletebutton// "deleteButton"
0x93e83  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93e88  stloc.0
0x93e89  ldloc.0
0x93e8a  ldstr    aImgsRefreshcom_15// "/_imgs/RefreshCommandbar/Delete_16.png"
0x93e8f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93e94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93e99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93e9e  ldloc.0
0x93e9f  ldc.i4.3
0x93ea0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93ea5  ldloc.0
0x93ea6  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93eab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93eb0  ldloc.0
0x93eb1  stloc.1
0x93eb2  leave.s  loc_93EBE
0x93eb4  ldloc.0
0x93eb5  brfalse.s loc_93EBD
0x93eb7  ldloc.0
0x93eb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93ebd  endfinally
0x93ebe  ldloc.1
0x93ebf  ret
```
