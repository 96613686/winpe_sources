# Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Do

- ea: `0x9920`
- end: `0x99dd`
- name: `Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Do`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x470`
- `0x64b0`
- `0x6520`
- `0x6550`
- `0x9130`
- `0x91b0`
- `0x9480`
- `0x9920`
- `0x99e0`
- `0x9a10`
- `0x9b50`
- `0x24270`

## string_xrefs

- `0x996c`: `RemoveUserSysAdminRole`
- `0x9997`: `Skip RemoveUserSysAdminRoleAction because it is not needed anymore.`
- `0x99bc`: `RemoveUserSysAdminRoleAction.Exit`

## pseudocode

```c

```

## disassembly

```asm
0x9920  ldarg.0
0x9921  ldarg.0
0x9922  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9927  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x992c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9931  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x9936  ldarg.0
0x9937  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x993c  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x9941  dup
0x9942  brtrue.s loc_9948
0x9944  pop
0x9945  ldnull
0x9946  br.s     loc_994D
0x9948  call     instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_DemoUserRoleBehavior()
0x994d  stloc.0
0x994e  ldloc.0
0x994f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9954  brtrue.s loc_9982
0x9956  ldstr    aLegacy// "Legacy"
0x995b  ldloc.0
0x995c  ldc.i4.3
0x995d  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x9962  brfalse.s loc_996C
0x9964  ldarg.0
0x9965  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::LegacyBehavior()
0x996a  br.s     loc_99A1
0x996c  ldstr    aRemoveusersysa// "RemoveUserSysAdminRole"
0x9971  ldloc.0
0x9972  ldc.i4.3
0x9973  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x9978  brfalse.s loc_99A1
0x997a  ldarg.0
0x997b  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::RemoveAdminRoleUnlessAdminDemoUser()
0x9980  br.s     loc_99A1
0x9982  ldstr    aUselegacydemou// "UseLegacyDemoUserRoleBehavior"
0x9987  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabled(string)
0x998c  brfalse.s loc_9996
0x998e  ldarg.0
0x998f  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::LegacyBehavior()
0x9994  br.s     loc_99A1
0x9996  ldarg.0
0x9997  ldstr    aSkipRemoveuser// "Skip RemoveUserSysAdminRoleAction becau"...
0x999c  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x99a1  ldarg.0
0x99a2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x99a7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x99ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x99b1  ldarg.0
0x99b2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x99b7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x99bc  ldstr    aRemoveusersysa_0// "RemoveUserSysAdminRoleAction.Exit"
0x99c1  call     void Microsoft.Crm.CrmLive.ProvisioningOrgDBStateCollector::CollectAndSendToEventSource(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId, [opt] string additionalDetails)
0x99c6  ldarg.0
0x99c7  ldarg.0
0x99c8  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x99cd  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x99d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x99d7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x99dc  ret
```
