# Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Lost

- ea: `0x939c0`
- end: `0x93a32`
- name: `Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Lost`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x936a0`

## callees

- `0x939c0`
- `0x93ae0`

## string_xrefs

- `0x93a18`: `ms-crm-Menu-ReadForm`
- `0x939c5`: `RefreshCommandBar.Opportunity.Lost`
- `0x939d4`: `RefreshCommandBar.Opportunity.Lost`
- `0x939ea`: `/_imgs/refreshcommandbar/closeaslost_16.png`

## pseudocode

```c

```

## disassembly

```asm
0x939c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x939c5  ldstr    aRefreshcommand_7// "RefreshCommandBar.Opportunity.Lost"
0x939ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x939cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x939d4  ldstr    aRefreshcommand_7// "RefreshCommandBar.Opportunity.Lost"
0x939d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x939de  ldstr    aCloseaslost// "closeAsLost"
0x939e3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x939e8  stloc.0
0x939e9  ldloc.0
0x939ea  ldstr    aImgsRefreshcom_7// "/_imgs/refreshcommandbar/closeaslost_16"...
0x939ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x939f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x939f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x939fe  ldloc.0
0x939ff  ldc.i4   0xCE
0x93a04  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93a09  ldloc.0
0x93a0a  call     bool Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::IsCloseCommandBarButtonVisible()
0x93a0f  ldc.i4.0
0x93a10  ceq
0x93a12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_IsTrimmed(bool)
0x93a17  ldloc.0
0x93a18  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93a1d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93a22  ldloc.0
0x93a23  stloc.1
0x93a24  leave.s  loc_93A30
0x93a26  ldloc.0
0x93a27  brfalse.s loc_93A2F
0x93a29  ldloc.0
0x93a2a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93a2f  endfinally
0x93a30  ldloc.1
0x93a31  ret
```
