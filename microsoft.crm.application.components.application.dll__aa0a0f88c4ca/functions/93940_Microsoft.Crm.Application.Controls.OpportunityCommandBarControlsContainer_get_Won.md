# Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Won

- ea: `0x93940`
- end: `0x939b2`
- name: `Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Won`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x936a0`

## callees

- `0x93940`
- `0x93ae0`

## string_xrefs

- `0x93998`: `ms-crm-Menu-ReadForm`
- `0x93945`: `RefreshCommandBar.Opportunity.Won`
- `0x93954`: `RefreshCommandBar.Opportunity.Won`
- `0x9396a`: `/_imgs/refreshcommandbar/closeaswon_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x93940  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93945  ldstr    aRefreshcommand_6// "RefreshCommandBar.Opportunity.Won"
0x9394a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9394f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93954  ldstr    aRefreshcommand_6// "RefreshCommandBar.Opportunity.Won"
0x93959  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9395e  ldstr    aCloseaswon// "closeAsWon"
0x93963  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93968  stloc.0
0x93969  ldloc.0
0x9396a  ldstr    aImgsRefreshcom_6// "/_imgs/refreshcommandbar/closeaswon_16."...
0x9396f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93974  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93979  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9397e  ldloc.0
0x9397f  ldc.i4   0xCD
0x93984  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93989  ldloc.0
0x9398a  call     bool Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::IsCloseCommandBarButtonVisible()
0x9398f  ldc.i4.0
0x93990  ceq
0x93992  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_IsTrimmed(bool)
0x93997  ldloc.0
0x93998  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x9399d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x939a2  ldloc.0
0x939a3  stloc.1
0x939a4  leave.s  loc_939B0
0x939a6  ldloc.0
0x939a7  brfalse.s loc_939AF
0x939a9  ldloc.0
0x939aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x939af  endfinally
0x939b0  ldloc.1
0x939b1  ret
```
