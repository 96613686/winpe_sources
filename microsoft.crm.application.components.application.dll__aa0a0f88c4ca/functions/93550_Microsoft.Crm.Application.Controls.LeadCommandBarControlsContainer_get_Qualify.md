# Microsoft.Crm.Application.Controls.LeadCommandBarControlsContainer::get_Qualify

- ea: `0x93550`
- end: `0x935b1`
- name: `Microsoft.Crm.Application.Controls.LeadCommandBarControlsContainer::get_Qualify`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x932c0`

## callees

- `0x93550`

## string_xrefs

- `0x93597`: `ms-crm-Menu-ReadForm`
- `0x93555`: `RefreshCommandBar.Lead.Qualify`
- `0x93564`: `RefreshCommandBar.Lead.Qualify`
- `0x9357a`: `/_imgs/refreshcommandbar/qualify_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93550  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93555  ldstr    aRefreshcommand_3// "RefreshCommandBar.Lead.Qualify"
0x9355a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9355f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93564  ldstr    aRefreshcommand_3// "RefreshCommandBar.Lead.Qualify"
0x93569  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9356e  ldstr    aQualifylead_2// "qualifyLead"
0x93573  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93578  stloc.0
0x93579  ldloc.0
0x9357a  ldstr    aImgsRefreshcom_3// "/_imgs/refreshcommandbar/qualify_16.png"
0x9357f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93584  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93589  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9358e  ldloc.0
0x9358f  ldc.i4.s 0xF
0x93591  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93596  ldloc.0
0x93597  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9359c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x935a1  ldloc.0
0x935a2  stloc.1
0x935a3  leave.s  loc_935AF
0x935a5  ldloc.0
0x935a6  brfalse.s loc_935AE
0x935a8  ldloc.0
0x935a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x935ae  endfinally
0x935af  ldloc.1
0x935b0  ret
```
