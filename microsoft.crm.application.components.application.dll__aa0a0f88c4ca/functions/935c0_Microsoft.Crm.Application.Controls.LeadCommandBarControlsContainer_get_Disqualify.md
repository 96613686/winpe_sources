# Microsoft.Crm.Application.Controls.LeadCommandBarControlsContainer::get_Disqualify

- ea: `0x935c0`
- end: `0x93621`
- name: `Microsoft.Crm.Application.Controls.LeadCommandBarControlsContainer::get_Disqualify`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x932c0`

## callees

- `0x935c0`

## string_xrefs

- `0x93607`: `ms-crm-Menu-ReadForm`
- `0x935c5`: `RefreshCommandBar.Lead.Disqualify`
- `0x935d4`: `RefreshCommandBar.Lead.Disqualify`
- `0x935ea`: `/_imgs/refreshcommandbar/disqualify_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x935c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x935c5  ldstr    aRefreshcommand_4// "RefreshCommandBar.Lead.Disqualify"
0x935ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x935cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x935d4  ldstr    aRefreshcommand_4// "RefreshCommandBar.Lead.Disqualify"
0x935d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x935de  ldstr    aDisqualifylead// "disqualifyLead"
0x935e3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x935e8  stloc.0
0x935e9  ldloc.0
0x935ea  ldstr    aImgsRefreshcom_4// "/_imgs/refreshcommandbar/disqualify_16."...
0x935ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x935f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x935f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x935fe  ldloc.0
0x935ff  ldc.i4.s 0x10
0x93601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93606  ldloc.0
0x93607  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9360c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93611  ldloc.0
0x93612  stloc.1
0x93613  leave.s  loc_9361F
0x93615  ldloc.0
0x93616  brfalse.s loc_9361E
0x93618  ldloc.0
0x93619  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9361e  endfinally
0x9361f  ldloc.1
0x93620  ret
```
