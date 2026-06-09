# Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Do

- ea: `0x2580`
- end: `0x26d2`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Do`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x470`
- `0x2580`
- `0x2710`
- `0x28c0`
- `0x2910`
- `0x29c0`
- `0x2b20`
- `0x64b0`
- `0x6520`
- `0x6550`
- `0x9130`
- `0x91b0`
- `0x9250`
- `0x1bed0`
- `0x1c310`
- `0x1c3b0`

## string_xrefs

- `0x25b1`: `AddInitialUserToConfigDBAction.Start`
- `0x26b1`: `AddInitialUserToConfigDBAction.Exit`

## pseudocode

```c

```

## disassembly

```asm
0x2580  ldarg.0
0x2581  ldarg.0
0x2582  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2587  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x258c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2591  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x2596  ldarg.0
0x2597  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x259c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x25a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x25a6  ldarg.0
0x25a7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x25ac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x25b1  ldstr    aAddinitialuser// "AddInitialUserToConfigDBAction.Start"
0x25b6  call     void Microsoft.Crm.CrmLive.ProvisioningOrgDBStateCollector::CollectAndSendToEventSource(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId, [opt] string additionalDetails)
0x25bb  ldarg.0
0x25bc  ldarg.0
0x25bd  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x25c2  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x25c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x25cc  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::GetInitialUserId(valuetype [mscorlib]System.Guid organizationId)
0x25d1  ldarg.0
0x25d2  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemapInitialUser()
0x25d7  ldarg.0
0x25d8  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemoveSalesRepRoleForInitialUserId()
0x25dd  ldarg.0
0x25de  ldarg.0
0x25df  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x25e4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x25e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x25ee  ldarg.0
0x25ef  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x25f4  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x25f9  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_Puid()
0x25fe  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::SetSystemUserPuid(valuetype [mscorlib]System.Guid organizationId, string initialUserPuid)
0x2603  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x2608  stloc.0
0x2609  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x260e  ldarg.0
0x260f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2614  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2619  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x261e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x2623  brfalse.s loc_265B
0x2625  ldarg.0
0x2626  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_objectId
0x262b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2630  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2635  brfalse.s loc_2681
0x2637  ldloc.0
0x2638  ldarg.0
0x2639  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x263e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2643  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2648  ldarg.0
0x2649  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x264e  ldarg.0
0x264f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_objectId
0x2654  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::SetUserObjectIdUsingSql(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid objectId)
0x2659  br.s     loc_2681
0x265b  ldloc.0
0x265c  ldarg.0
0x265d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2662  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2667  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x266c  ldarg.0
0x266d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2672  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x2677  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_UserLiveId()
0x267c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateUserInviteStatusAccepted(valuetype [mscorlib]System.Guid orgId, string windowsLiveId)
0x2681  ldarg.0
0x2682  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2687  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x268c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2691  call     void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::SetUserLicensesInUseCount(valuetype [mscorlib]System.Guid organizationId)
0x2696  ldarg.0
0x2697  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x269c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x26a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x26a6  ldarg.0
0x26a7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x26ac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x26b1  ldstr    aAddinitialuser_0// "AddInitialUserToConfigDBAction.Exit"
0x26b6  call     void Microsoft.Crm.CrmLive.ProvisioningOrgDBStateCollector::CollectAndSendToEventSource(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId, [opt] string additionalDetails)
0x26bb  ldarg.0
0x26bc  ldarg.0
0x26bd  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x26c2  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x26c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x26cc  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x26d1  ret
```
