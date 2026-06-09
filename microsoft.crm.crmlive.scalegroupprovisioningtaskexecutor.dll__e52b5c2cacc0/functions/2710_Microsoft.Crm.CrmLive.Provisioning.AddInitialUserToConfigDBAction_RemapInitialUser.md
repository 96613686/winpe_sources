# Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemapInitialUser

- ea: `0x2710`
- end: `0x2885`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemapInitialUser`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2580`

## callees

- `0x26e0`
- `0x2710`
- `0x64b0`
- `0x9130`
- `0x91b0`
- `0x9250`
- `0x9480`
- `0x94a0`
- `0x1d460`
- `0x201a0`
- `0x24210`

## string_xrefs

- `0x27c5`: `blank_1@crmdemo.dynamics.com`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.0
0x2711  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2716  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x271b  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserScenario()
0x2720  stloc.0
0x2721  ldarg.0
0x2722  ldstr    aRemapinitialus// "RemapInitialUser ScenarioToUse : "
0x2727  ldloc.0
0x2728  call     string [mscorlib]System.String::Concat(string, string)
0x272d  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x2732  ldloc.0
0x2733  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2738  brfalse.s loc_2746
0x273a  ldarg.0
0x273b  ldstr    aRemapinitialus_0// "RemapInitialUser exiting since scenario"...
0x2740  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x2745  ret
0x2746  ldarg.0
0x2747  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x274c  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_UseMtpProvisioning()
0x2751  brtrue.s loc_275E
0x2753  ldstr    aMtpProvisionin// "MTP provisioning must always be set"
0x2758  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x275d  throw
0x275e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::.ctor()
0x2763  stloc.1
0x2764  ldloc.1
0x2765  ldarg.0
0x2766  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x276b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2770  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2775  ldloc.0
0x2776  ldnull
0x2777  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::PickUserToMapTo(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo[])
0x277c  stloc.2
0x277d  ldloc.2
0x277e  brtrue.s loc_278C
0x2780  ldarg.0
0x2781  ldstr    aRemapinitialus_1// "RemapInitialUser exiting since no user "...
0x2786  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x278b  ret
0x278c  ldarg.0
0x278d  ldstr    aRemapinitialus_2// "RemapInitialUser newUserToMapTo : "
0x2792  ldloc.2
0x2793  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_DomainName()
0x2798  call     string [mscorlib]System.String::Concat(string, string)
0x279d  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x27a2  ldarg.0
0x27a3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x27a8  stloc.3
0x27a9  ldarg.0
0x27aa  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x27af  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x27b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x27b9  ldc.i4.0
0x27ba  ldloc.3
0x27bb  ldstr    asc_3635C// "---"
0x27c0  ldstr    asc_3635C// "---"
0x27c5  ldstr    aBlank1CrmdemoD// "blank_1@crmdemo.dynamics.com"
0x27ca  ldarg.0
0x27cb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x27d0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x27d5  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSystemUserReferences(valuetype [mscorlib]System.Guid orgId, bool changeInitialCrmUserId, valuetype [mscorlib]System.Guid initialUserSystemUserId, string newFirstName, string newLastName, string newEmail, valuetype [mscorlib]System.Guid queueItemId)
0x27da  ldloc.1
0x27db  ldarg.0
0x27dc  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x27e1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x27e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x27eb  ldloc.2
0x27ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_SystemUserId()
0x27f1  ldarg.0
0x27f2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x27f7  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x27fc  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_UserLiveId()
0x2801  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::MapDemoUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string)
0x2806  ldarg.0
0x2807  ldloc.2
0x2808  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_SystemUserId()
0x280d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x2812  ldarg.0
0x2813  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2818  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x281d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2822  ldc.i4.0
0x2823  ldloc.2
0x2824  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_SystemUserId()
0x2829  ldarg.0
0x282a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x282f  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x2834  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_FirstName()
0x2839  ldarg.0
0x283a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x283f  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x2844  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_LastName()
0x2849  ldarg.0
0x284a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x284f  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x2854  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_UserLiveId()
0x2859  ldarg.0
0x285a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x285f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x2864  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSystemUserReferences(valuetype [mscorlib]System.Guid orgId, bool changeInitialCrmUserId, valuetype [mscorlib]System.Guid initialUserSystemUserId, string newFirstName, string newLastName, string newEmail, valuetype [mscorlib]System.Guid queueItemId)
0x2869  ldarg.0
0x286a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x286f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2874  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2879  ldloc.2
0x287a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.DemoUserInfo::get_SystemUserId()
0x287f  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::EnableUserIfDisabled(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid systemUserId)
0x2884  ret
```
