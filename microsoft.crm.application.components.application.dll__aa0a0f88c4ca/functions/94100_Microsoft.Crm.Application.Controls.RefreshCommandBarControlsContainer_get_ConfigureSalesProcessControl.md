# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_ConfigureSalesProcessControl

- ea: `0x94100`
- end: `0x94164`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_ConfigureSalesProcessControl`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x932c0`
- `0x936a0`

## callees

- `0x94100`

## string_xrefs

- `0x9414a`: `ms-crm-Menu-ReadForm`
- `0x94105`: `RefreshCommandBar.EditSalesProcess`
- `0x94114`: `RefreshCommandBar.EditSalesProcess`
- `0x9411e`: `configureProcessControlButton`
- `0x9412a`: `/_imgs/RefreshCommandbar/Settings_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x94100  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94105  ldstr    aRefreshcommand_22// "RefreshCommandBar.EditSalesProcess"
0x9410a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9410f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94114  ldstr    aRefreshcommand_22// "RefreshCommandBar.EditSalesProcess"
0x94119  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9411e  ldstr    aConfigureproce// "configureProcessControlButton"
0x94123  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x94128  stloc.0
0x94129  ldloc.0
0x9412a  ldstr    aImgsRefreshcom_20// "/_imgs/RefreshCommandbar/Settings_16.pn"...
0x9412f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94134  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94139  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9413e  ldloc.0
0x9413f  ldc.i4   0xD9
0x94144  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x94149  ldloc.0
0x9414a  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9414f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x94154  ldloc.0
0x94155  stloc.1
0x94156  leave.s  loc_94162
0x94158  ldloc.0
0x94159  brfalse.s loc_94161
0x9415b  ldloc.0
0x9415c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94161  endfinally
0x94162  ldloc.1
0x94163  ret
```
