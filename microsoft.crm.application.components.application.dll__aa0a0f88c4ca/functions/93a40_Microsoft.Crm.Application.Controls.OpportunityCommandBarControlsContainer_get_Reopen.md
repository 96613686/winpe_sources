# Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Reopen

- ea: `0x93a40`
- end: `0x93ad2`
- name: `Microsoft.Crm.Application.Controls.OpportunityCommandBarControlsContainer::get_Reopen`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x936a0`

## callees

- `0x93a40`

## string_xrefs

- `0x93ab8`: `ms-crm-Menu-ReadForm`
- `0x93a8c`: `/_imgs/refreshcommandbar/reactivatecase_16.png`
- `0x93a67`: `RefreshCommandBar.Opportunity.Reopen`
- `0x93a76`: `Mscrm_Form_opportunity_MainTab_Actions_ReopenOpp_ToolTipDescription`
- `0x93a80`: `ReopenOpp`

## pseudocode

```c

```

## disassembly

```asm
0x93a40  ldstr    aOpportunityclo// "opportunityclose"
0x93a45  ldc.i4.2
0x93a46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93a4b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93a50  stloc.0
0x93a51  ldstr    aOpportunity// "opportunity"
0x93a56  ldc.i4.2
0x93a57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93a5c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93a61  stloc.1
0x93a62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93a67  ldstr    aRefreshcommand_8// "RefreshCommandBar.Opportunity.Reopen"
0x93a6c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93a71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93a76  ldstr    aMscrmFormOppor// "Mscrm_Form_opportunity_MainTab_Actions_"...
0x93a7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93a80  ldstr    aReopenopp// "ReopenOpp"
0x93a85  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::.ctor(string, string, string)
0x93a8a  stloc.2
0x93a8b  ldloc.2
0x93a8c  ldstr    aImgsRefreshcom_5// "/_imgs/refreshcommandbar/reactivatecase"...
0x93a91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93a96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93a9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x93aa0  ldloc.2
0x93aa1  ldc.i4   0xD5
0x93aa6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_ActionId(int32)
0x93aab  ldloc.2
0x93aac  ldloc.0
0x93aad  ldloc.1
0x93aae  and
0x93aaf  ldc.i4.0
0x93ab0  ceq
0x93ab2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_IsTrimmed(bool)
0x93ab7  ldloc.2
0x93ab8  ldstr    aMsCrmMenuReadf// "ms-crm-Menu-ReadForm"
0x93abd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::set_CssClass(string)
0x93ac2  ldloc.2
0x93ac3  stloc.3
0x93ac4  leave.s  loc_93AD0
0x93ac6  ldloc.2
0x93ac7  brfalse.s loc_93ACF
0x93ac9  ldloc.2
0x93aca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93acf  endfinally
0x93ad0  ldloc.3
0x93ad1  ret
```
