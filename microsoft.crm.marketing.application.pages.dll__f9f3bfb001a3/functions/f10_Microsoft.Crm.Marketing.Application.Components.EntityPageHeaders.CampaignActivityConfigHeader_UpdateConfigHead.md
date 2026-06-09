# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::UpdateConfigHeaderForEntityRecord

- ea: `0xf10`
- end: `0xfb3`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::UpdateConfigHeaderForEntityRecord`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0xf10`
- `0xfc0`
- `0x1040`
- `0x10c0`

## string_xrefs

- `0xf19`: `UserHasCreateActivityPrivilege`
- `0xf2e`: `UserHasMailMergePrivilege`
- `0xf80`: `IsCampaignActivityTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldarg.0
0xf11  ldarg.1
0xf12  ldarg.2
0xf13  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::UpdateConfigHeaderForEntityRecord(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xf18  ldarg.1
0xf19  ldstr    aUserhascreatea// "UserHasCreateActivityPrivilege"
0xf1e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xf23  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::CurrentUserHasPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition privilege)
0xf28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf2d  ldarg.1
0xf2e  ldstr    aUserhasmailmer// "UserHasMailMergePrivilege"
0xf33  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_MailMerge()
0xf38  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::CurrentUserHasPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition privilege)
0xf3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf42  ldarg.1
0xf43  ldstr    aIsmarketingexe// "IsMarketingExecutionEnabled"
0xf48  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::IsMarketingExecutionEnable()
0xf4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf52  ldarg.1
0xf53  ldstr    aMarketingautom// "MarketingAutomation"
0xf58  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xf5d  ldc.i4.0
0xf5e  stloc.0
0xf5f  ldarg.2
0xf60  ldstr    aRegardingobjec// "regardingobjectid"
0xf65  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf6a  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xf6f  stloc.1
0xf70  ldloc.1
0xf71  brfalse.s loc_F7F
0xf73  ldloc.1
0xf74  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xf79  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityTemplateFlag(string entityId)
0xf7e  stloc.0
0xf7f  ldarg.1
0xf80  ldstr    aIscampaignacti// "IsCampaignActivityTemplate"
0xf85  ldloc.0
0xf86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf8b  ldarg.1
0xf8c  ldstr    aCampaignactivi_0// "CampaignActivityState"
0xf91  ldarg.2
0xf92  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0xf97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf9c  ldarg.1
0xf9d  ldstr    aIscampaignacti_0// "IsCampaignActivityDistributed"
0xfa2  ldarg.2
0xfa3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xfa8  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityPropagationFlag(string entityId)
0xfad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfb2  ret
```
