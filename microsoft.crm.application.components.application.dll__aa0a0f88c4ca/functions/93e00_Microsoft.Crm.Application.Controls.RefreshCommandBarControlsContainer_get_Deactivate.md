# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Deactivate

- ea: `0x93e00`
- end: `0x93e60`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_Deactivate`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x92e20`
- `0x93070`

## callees

- `0x93e00`

## string_xrefs

- `0x93e46`: `ms-crm-Menu-ReadForm`
- `0x93e05`: `RefreshCommandBar.Deactivate`
- `0x93e14`: `RefreshCommandBar.Deactivate`
- `0x93e2a`: `/_imgs/RefreshCommandbar/Deactivate_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93e00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93e05  ldstr    aRefreshcommand_13// "RefreshCommandBar.Deactivate"
0x93e0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93e0f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93e14  ldstr    aRefreshcommand_13// "RefreshCommandBar.Deactivate"
0x93e19  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93e1e  ldstr    aDeactivatebutt// "deactivateButton"
0x93e23  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93e28  stloc.0
0x93e29  ldloc.0
0x93e2a  ldstr    aImgsRefreshcom_14// "/_imgs/RefreshCommandbar/Deactivate_16."...
0x93e2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93e34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93e39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93e3e  ldloc.0
0x93e3f  ldc.i4.5
0x93e40  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93e45  ldloc.0
0x93e46  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93e4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93e50  ldloc.0
0x93e51  stloc.1
0x93e52  leave.s  loc_93E5E
0x93e54  ldloc.0
0x93e55  brfalse.s loc_93E5D
0x93e57  ldloc.0
0x93e58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93e5d  endfinally
0x93e5e  ldloc.1
0x93e5f  ret
```
