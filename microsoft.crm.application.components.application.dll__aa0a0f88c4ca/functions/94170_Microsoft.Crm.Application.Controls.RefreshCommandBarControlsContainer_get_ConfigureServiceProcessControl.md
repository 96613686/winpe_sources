# Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_ConfigureServiceProcessControl

- ea: `0x94170`
- end: `0x941d4`
- name: `Microsoft.Crm.Application.Controls.RefreshCommandBarControlsContainer::get_ConfigureServiceProcessControl`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x94170`

## string_xrefs

- `0x941ba`: `ms-crm-Menu-ReadForm`
- `0x9418e`: `configureProcessControlButton`
- `0x9419a`: `/_imgs/RefreshCommandbar/Settings_16.png`
- `0x94175`: `RefreshCommandBar.EditServiceProcess`
- `0x94184`: `RefreshCommandBar.EditServiceProcess`

## pseudocode

```c

```

## disassembly

```asm
0x94170  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94175  ldstr    aRefreshcommand_23// "RefreshCommandBar.EditServiceProcess"
0x9417a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9417f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94184  ldstr    aRefreshcommand_23// "RefreshCommandBar.EditServiceProcess"
0x94189  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9418e  ldstr    aConfigureproce// "configureProcessControlButton"
0x94193  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x94198  stloc.0
0x94199  ldloc.0
0x9419a  ldstr    aImgsRefreshcom_20// "/_imgs/RefreshCommandbar/Settings_16.pn"...
0x9419f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x941a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x941a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x941ae  ldloc.0
0x941af  ldc.i4   0xD9
0x941b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x941b9  ldloc.0
0x941ba  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x941bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x941c4  ldloc.0
0x941c5  stloc.1
0x941c6  leave.s  loc_941D2
0x941c8  ldloc.0
0x941c9  brfalse.s loc_941D1
0x941cb  ldloc.0
0x941cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x941d1  endfinally
0x941d2  ldloc.1
0x941d3  ret
```
