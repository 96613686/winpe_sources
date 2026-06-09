# Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::LegacyBehavior

- ea: `0x9a10`
- end: `0x9b42`
- name: `Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::LegacyBehavior`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x64b0`
- `0x91b0`
- `0x94e0`
- `0x99e0`
- `0x9a10`
- `0x1c1b0`
- `0x1c320`
- `0x1c3b0`

## string_xrefs

- `0x9a30`: `Skip RemoveUserSysAdminRoleAction because no solution packages have been installed.`
- `0x9ae6`: `Caling RemoveUserRole`

## pseudocode

```c

```

## disassembly

```asm
0x9a10  ldarg.0
0x9a11  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9a16  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x9a1b  brfalse.s loc_9A2F
0x9a1d  ldarg.0
0x9a1e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9a23  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x9a28  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::get_Count()
0x9a2d  brtrue.s loc_9A3B
0x9a2f  ldarg.0
0x9a30  ldstr    aSkipRemoveuser_0// "Skip RemoveUserSysAdminRoleAction becau"...
0x9a35  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9a3a  ret
0x9a3b  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x9a40  stloc.0
0x9a41  ldloc.0
0x9a42  ldarg.0
0x9a43  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9a48  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9a4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9a52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetInitialCrmUsersUsingEntityExpression(valuetype [mscorlib]System.Guid organizationId)
0x9a57  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x9a5c  stloc.1
0x9a5d  br       loc_9B20
0x9a62  ldloc.1
0x9a63  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9a68  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x9a6d  stloc.2
0x9a6e  ldloc.2
0x9a6f  ldstr    aDomainname_0// "domainname"
0x9a74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9a79  isinst   [mscorlib]System.String
0x9a7e  stloc.3
0x9a7f  ldarg.0
0x9a80  ldstr    aCheckingUser// "Checking user : "
0x9a85  ldloc.3
0x9a86  call     string [mscorlib]System.String::Concat(string, string)
0x9a8b  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9a90  ldloc.3
0x9a91  call     bool [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::IsAdminDemoUserUpn(string)
0x9a96  brfalse.s loc_9AA5
0x9a98  ldarg.0
0x9a99  ldstr    aIsadmindemouse// "IsAdminDemoUserUpn, skipping"
0x9a9e  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9aa3  br.s     loc_9B20
0x9aa5  ldstr    aKeepadminrolef// "KeepAdminRoleForSmbDemoUsers"
0x9aaa  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabled(string)
0x9aaf  brfalse.s loc_9AE5
0x9ab1  ldloc.3
0x9ab2  ldstr    aSmbsales// "SmbSales"
0x9ab7  call     bool [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::IsFirstDemoUserForScenario(string, string)
0x9abc  brfalse.s loc_9ACB
0x9abe  ldarg.0
0x9abf  ldstr    aIsfirstdemouse// "IsFirstDemoUserForScenario for SmbSales"...
0x9ac4  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9ac9  br.s     loc_9B20
0x9acb  ldloc.3
0x9acc  ldstr    aSmbmarketing// "SmbMarketing"
0x9ad1  call     bool [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::IsFirstDemoUserForScenario(string, string)
0x9ad6  brfalse.s loc_9AE5
0x9ad8  ldarg.0
0x9ad9  ldstr    aIsfirstdemouse_0// "IsFirstDemoUserForScenario for SmbMarke"...
0x9ade  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9ae3  br.s     loc_9B20
0x9ae5  ldarg.0
0x9ae6  ldstr    aCalingRemoveus// "Caling RemoveUserRole"
0x9aeb  call     instance void Microsoft.Crm.CrmLive.Provisioning.RemoveUserSysAdminRoleAction::Log(string log)
0x9af0  ldloc.0
0x9af1  ldarg.0
0x9af2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9af7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9afc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9b01  ldstr    a627090ff40a340// "{627090FF-40A3-4053-8790-584EDC5BE201}"
0x9b06  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9b0b  ldloc.2
0x9b0c  ldstr    aSystemuserid_0// "systemuserid"
0x9b11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9b16  unbox.any [mscorlib]System.Guid
0x9b1b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RemoveUserRole(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleTemplateId, valuetype [mscorlib]System.Guid crmUserId)
0x9b20  ldloc.1
0x9b21  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9b26  brtrue   loc_9A62
0x9b2b  leave.s  loc_9B41
0x9b2d  ldloc.1
0x9b2e  isinst   [mscorlib]System.IDisposable
0x9b33  stloc.s  4
0x9b35  ldloc.s  4
0x9b37  brfalse.s loc_9B40
0x9b39  ldloc.s  4
0x9b3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9b40  endfinally
0x9b41  ret
```
