# Microsoft.Crm.CrmLive.Provisioning.Organization::RestoreDatabaseToTarget

- ea: `0x198c0`
- end: `0x19af3`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::RestoreDatabaseToTarget`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x198c0`
- `0x19e70`
- `0x1a250`
- `0x1baa0`
- `0x1be30`
- `0x1be60`
- `0x1c3b0`

## string_xrefs

- `0x19974`: `Restore -- Register new availability group and servers in config`
- `0x199bd`: `Restore -- Restore primary availability group {0} primary server={1}, db={2}, backup path={3}, backup log path={4}, backup locations={5}, restore point id = {6}`

## pseudocode

```c

```

## disassembly

```asm
0x198c0  ldarg.1
0x198c1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x198c6  stloc.0
0x198c7  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x198cc  stloc.1
0x198cd  ldloc.0
0x198ce  ldarg.2
0x198cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x198d4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::RetrieveDBInfo(valuetype [mscorlib]System.Guid)
0x198d9  stloc.2
0x198da  ldarg.2
0x198db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x198e0  ldc.i4.s 0x42
0x198e2  ldstr    aRestoringDatab_1// "Restoring Database {0}"
0x198e7  ldc.i4.1
0x198e8  newarr   [mscorlib]System.Object
0x198ed  dup
0x198ee  ldc.i4.0
0x198ef  ldloc.2
0x198f0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x198f5  stelem.ref
0x198f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x198fb  ldloc.0
0x198fc  ldloc.2
0x198fd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::VerifyOrAssignNewServers(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData)
0x19902  ldarg.2
0x19903  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19908  ldc.i4.s 0x42
0x1990a  ldstr    aRestoreDetermi// "Restore -- Determining StorageGroupId f"...
0x1990f  ldc.i4.1
0x19910  newarr   [mscorlib]System.Object
0x19915  dup
0x19916  ldc.i4.0
0x19917  ldloc.2
0x19918  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1991d  stelem.ref
0x1991e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19923  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x19928  ldloc.2
0x19929  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1992e  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(string)
0x19933  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_StorageGroupId()
0x19938  stloc.3
0x19939  ldarg.2
0x1993a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x1993f  ldc.i4.s 0x42
0x19941  ldstr    aRetrievedStora// "Retrieved StorageGroupId: {0}"
0x19946  ldc.i4.1
0x19947  newarr   [mscorlib]System.Object
0x1994c  dup
0x1994d  ldc.i4.0
0x1994e  ldloc.3
0x1994f  box      [mscorlib]System.Guid
0x19954  stelem.ref
0x19955  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1995a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::.ctor()
0x1995f  ldloc.2
0x19960  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_ScaleGroupId()
0x19965  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Retrieve(valuetype [mscorlib]System.Guid)
0x1996a  stloc.s  4
0x1996c  ldarg.2
0x1996d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19972  ldc.i4.s 0x42
0x19974  ldstr    aRestoreRegiste// "Restore -- Register new availability gr"...
0x19979  ldc.i4.0
0x1997a  newarr   [mscorlib]System.Object
0x1997f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19984  ldarg.2
0x19985  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x1998a  ldloc.2
0x1998b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_AvailabilityGroupName()
0x19990  ldloc.2
0x19991  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19996  ldloc.2
0x19997  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_SecondaryServer()
0x1999c  ldloc.2
0x1999d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_ScaleGroupId()
0x199a2  ldloc.3
0x199a3  ldloc.s  4
0x199a5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x199aa  ldloc.2
0x199ab  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x199b0  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::RegisterMappingInConfigDB(valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primarySqlServer, string secondarySqlServer, valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid storageGroupId, string reportServerUrl, string dbName)
0x199b5  ldarg.2
0x199b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x199bb  ldc.i4.s 0x42
0x199bd  ldstr    aRestoreRestore_0// "Restore -- Restore primary availability"...
0x199c2  ldc.i4.7
0x199c3  newarr   [mscorlib]System.Object
0x199c8  dup
0x199c9  ldc.i4.0
0x199ca  ldloc.2
0x199cb  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_AvailabilityGroupName()
0x199d0  stelem.ref
0x199d1  dup
0x199d2  ldc.i4.1
0x199d3  ldloc.2
0x199d4  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x199d9  stelem.ref
0x199da  dup
0x199db  ldc.i4.2
0x199dc  ldloc.2
0x199dd  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x199e2  stelem.ref
0x199e3  dup
0x199e4  ldc.i4.3
0x199e5  ldarg.2
0x199e6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupDataShare()
0x199eb  stelem.ref
0x199ec  dup
0x199ed  ldc.i4.4
0x199ee  ldarg.2
0x199ef  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLogShare()
0x199f4  stelem.ref
0x199f5  dup
0x199f6  ldc.i4.5
0x199f7  ldarg.2
0x199f8  callvirt instance string[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLocations()
0x199fd  brtrue.s loc_19A06
0x199ff  ldsfld   string [mscorlib]System.String::Empty
0x19a04  br.s     loc_19A16
0x19a06  ldstr    asc_354F4// ","
0x19a0b  ldarg.2
0x19a0c  callvirt instance string[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLocations()
0x19a11  call     string [mscorlib]System.String::Join(string, string[])
0x19a16  stelem.ref
0x19a17  dup
0x19a18  ldc.i4.6
0x19a19  ldarg.2
0x19a1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_RestorePointId()
0x19a1f  box      [mscorlib]System.Guid
0x19a24  stelem.ref
0x19a25  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19a2a  ldarg.2
0x19a2b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19a30  ldloc.2
0x19a31  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19a36  ldnull
0x19a37  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::CreateCustomerManagedKey(valuetype [mscorlib]System.Guid organizationId, string server, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace trace)
0x19a3c  ldarg.2
0x19a3d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19a42  ldstr    aOrganization// "Organization"
0x19a47  ldstr    aAttachrestored// "AttachRestoreDb"
0x19a4c  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x19a51  ldnull
0x19a52  stloc.s  5
0x19a54  ldarg.2
0x19a55  callvirt instance string[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLocations()
0x19a5a  brfalse.s loc_19A72
0x19a5c  ldarg.2
0x19a5d  callvirt instance string[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLocations()
0x19a62  call     T0x2B00008D
0x19a67  ldc.i4.1
0x19a68  ble.s    loc_19A72
0x19a6a  ldarg.2
0x19a6b  call     string[] Microsoft.Crm.CrmLive.Provisioning.Organization::GetBackupFiles(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo restoreInfo)
0x19a70  stloc.s  5
0x19a72  ldloc.s  5
0x19a74  brfalse.s loc_19AA0
0x19a76  ldloc.s  5
0x19a78  ldlen
0x19a79  conv.i4
0x19a7a  ldc.i4.1
0x19a7b  ble.s    loc_19AA0
0x19a7d  ldloc.1
0x19a7e  ldarg.2
0x19a7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19a84  ldloc.s  5
0x19a86  ldloc.2
0x19a87  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19a8c  ldloc.2
0x19a8d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x19a92  ldarg.2
0x19a93  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_RestoreTime()
0x19a98  ldc.i4.0
0x19a99  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestoreToPointInTime(valuetype [mscorlib]System.Guid organizationId, string[] backupLocations, string primaryServer, string dbName, valuetype [mscorlib]System.DateTime restoreTime, bool isNoRecovery)
0x19a9e  br.s     loc_19ADD
0x19aa0  ldarg.2
0x19aa1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupDataShare()
0x19aa6  brtrue.s loc_19AB9
0x19aa8  ldloc.s  5
0x19aaa  brfalse.s loc_19AB9
0x19aac  ldarg.2
0x19aad  ldloc.s  5
0x19aaf  call     T0x2B00007B
0x19ab4  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::set_BackupDataShare(string)
0x19ab9  ldloc.1
0x19aba  ldarg.2
0x19abb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19ac0  ldarg.2
0x19ac1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupDataShare()
0x19ac6  ldarg.2
0x19ac7  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_BackupLogShare()
0x19acc  ldloc.2
0x19acd  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x19ad2  ldloc.2
0x19ad3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x19ad8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RestorePrimary(valuetype [mscorlib]System.Guid organizationId, string backupFileName, string logFileName, string primaryServer, string dbName)
0x19add  ldarg.2
0x19ade  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreInfo::get_OrganizationId()
0x19ae3  ldstr    aOrganization// "Organization"
0x19ae8  ldstr    aAttachrestored// "AttachRestoreDb"
0x19aed  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x19af2  ret
```
