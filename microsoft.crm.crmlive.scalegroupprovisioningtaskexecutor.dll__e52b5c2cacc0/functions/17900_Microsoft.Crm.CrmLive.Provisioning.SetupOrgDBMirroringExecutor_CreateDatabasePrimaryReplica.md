# Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabasePrimaryReplica

- ea: `0x17900`
- end: `0x17ac6`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabasePrimaryReplica`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x170b0`

## callees

- `0x178e0`
- `0x17900`
- `0x17e70`

## string_xrefs

- `0x17939`: `CreateDatabasePrimaryReplica: Availability Group: {0} Primary: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17900  ldarg.1
0x17901  ldstr    aOrganizationid// "organizationId"
0x17906  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1790b  ldarg.2
0x1790c  ldstr    aAvailabilitygr_0// "availabilityGroupName"
0x17911  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17916  ldarg.3
0x17917  ldstr    aOrganizationse_0// "organizationServer"
0x1791c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17921  ldarg.s  4
0x17923  ldstr    aPrimaryreplica// "primaryReplica"
0x17928  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1792d  ldarg.s  5
0x1792f  ldstr    aDatabasename_0// "databaseName"
0x17934  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17939  ldstr    aCreatedatabase// "CreateDatabasePrimaryReplica: Availabil"...
0x1793e  ldc.i4.2
0x1793f  newarr   [mscorlib]System.Object
0x17944  dup
0x17945  ldc.i4.0
0x17946  ldarg.2
0x17947  stelem.ref
0x17948  dup
0x17949  ldc.i4.1
0x1794a  ldarg.s  4
0x1794c  stelem.ref
0x1794d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17952  ldc.i4.0
0x17953  stloc.0
0x17954  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x17959  ldarg.1
0x1795a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0x1795f  stloc.1
0x17960  ldarg.3
0x17961  stloc.2
0x17962  ldloc.1
0x17963  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x17968  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1796d  brtrue.s loc_17986
0x1796f  ldarg.0
0x17970  ldloc.1
0x17971  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x17976  call     instance string Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::TryGetDataSource(string connectionString)
0x1797b  stloc.3
0x1797c  ldloc.3
0x1797d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17982  brtrue.s loc_17986
0x17984  ldloc.3
0x17985  stloc.2
0x17986  ldarg.s  6
0x17988  ldind.ref
0x17989  brtrue   loc_17A10
0x1798e  ldarg.3
0x1798f  ldloc.2
0x17990  ldc.i4.5
0x17991  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x17996  brfalse.s loc_179A2
0x17998  ldarg.3
0x17999  ldarg.s  5
0x1799b  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlIsDBOnline(string, string)
0x179a0  brfalse.s loc_179C9
0x179a2  ldstr    aBackingUpDatab// "Backing up database {0} on replica {1} "
0x179a7  ldc.i4.2
0x179a8  newarr   [mscorlib]System.Object
0x179ad  dup
0x179ae  ldc.i4.0
0x179af  ldarg.s  5
0x179b1  stelem.ref
0x179b2  dup
0x179b3  ldc.i4.1
0x179b4  ldarg.3
0x179b5  stelem.ref
0x179b6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x179bb  ldarg.s  6
0x179bd  ldarg.s  5
0x179bf  ldarg.3
0x179c0  ldarg.1
0x179c1  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::BackupDatabase(string, string, valuetype [mscorlib]System.Guid)
0x179c6  stind.ref
0x179c7  br.s     loc_17A10
0x179c9  ldloc.2
0x179ca  ldarg.s  5
0x179cc  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlIsDBOnline(string, string)
0x179d1  brfalse.s loc_17A10
0x179d3  ldarg.s  4
0x179d5  ldarg.s  5
0x179d7  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlIsDBOnline(string, string)
0x179dc  brtrue.s loc_17A10
0x179de  ldstr    aOrgServerDoesN// "Org Server does not match backup server"...
0x179e3  ldc.i4.2
0x179e4  newarr   [mscorlib]System.Object
0x179e9  dup
0x179ea  ldc.i4.0
0x179eb  ldarg.s  5
0x179ed  stelem.ref
0x179ee  dup
0x179ef  ldc.i4.1
0x179f0  ldloc.2
0x179f1  stelem.ref
0x179f2  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x179f7  ldarg.s  6
0x179f9  ldarg.s  5
0x179fb  ldloc.2
0x179fc  ldarg.1
0x179fd  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::BackupDatabase(string, string, valuetype [mscorlib]System.Guid)
0x17a02  stind.ref
0x17a03  ldloc.2
0x17a04  ldarg.s  4
0x17a06  ldc.i4.5
0x17a07  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x17a0c  brfalse.s loc_17A10
0x17a0e  ldc.i4.1
0x17a0f  stloc.0
0x17a10  ldarg.s  4
0x17a12  ldarg.s  5
0x17a14  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlIsDBOnline(string, string)
0x17a19  brtrue   loc_17AA1
0x17a1e  ldarg.3
0x17a1f  ldarg.s  4
0x17a21  ldc.i4.5
0x17a22  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x17a27  ldc.i4.0
0x17a28  cgt.un
0x17a2a  ldloc.0
0x17a2b  or
0x17a2c  brfalse.s loc_17AA1
0x17a2e  ldarg.s  6
0x17a30  ldind.ref
0x17a31  brfalse.s loc_17A4F
0x17a33  ldarg.s  4
0x17a35  ldarg.s  5
0x17a37  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlDatabaseExists(string, string)
0x17a3c  brfalse.s loc_17A4F
0x17a3e  ldarg.s  4
0x17a40  ldarg.s  5
0x17a42  ldloc.2
0x17a43  ldarg.2
0x17a44  ldarg.2
0x17a45  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::GetReplicaStatus(string)
0x17a4a  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlDropDatabaseReplica(string, string, string, string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus)
0x17a4f  ldarg.0
0x17a50  ldarg.1
0x17a51  ldarg.s  4
0x17a53  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateCustomerManagedKey(valuetype [mscorlib]System.Guid organizationId, string server)
0x17a58  ldstr    aRestoringDatab// "Restoring database {0} on replica {1} "
0x17a5d  ldc.i4.2
0x17a5e  newarr   [mscorlib]System.Object
0x17a63  dup
0x17a64  ldc.i4.0
0x17a65  ldarg.s  5
0x17a67  stelem.ref
0x17a68  dup
0x17a69  ldc.i4.1
0x17a6a  ldarg.s  4
0x17a6c  stelem.ref
0x17a6d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17a72  ldarg.s  5
0x17a74  ldarg.s  4
0x17a76  ldarg.s  6
0x17a78  ldind.ref
0x17a79  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::RestoreDatabase(string, string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData)
0x17a7e  ldstr    aRestoringDatab_0// "Restoring database with recovery {0} on"...
0x17a83  ldc.i4.2
0x17a84  newarr   [mscorlib]System.Object
0x17a89  dup
0x17a8a  ldc.i4.0
0x17a8b  ldarg.s  5
0x17a8d  stelem.ref
0x17a8e  dup
0x17a8f  ldc.i4.1
0x17a90  ldarg.s  4
0x17a92  stelem.ref
0x17a93  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17a98  ldarg.s  5
0x17a9a  ldarg.s  4
0x17a9c  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::RestoreDatabaseWithRecovery(string, string)
0x17aa1  ldstr    aAddingPrimaryD// "Adding primary database {0} on replica "...
0x17aa6  ldc.i4.2
0x17aa7  newarr   [mscorlib]System.Object
0x17aac  dup
0x17aad  ldc.i4.0
0x17aae  ldarg.s  5
0x17ab0  stelem.ref
0x17ab1  dup
0x17ab2  ldc.i4.1
0x17ab3  ldarg.s  4
0x17ab5  stelem.ref
0x17ab6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17abb  ldarg.2
0x17abc  ldarg.s  4
0x17abe  ldarg.s  5
0x17ac0  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::AddPrimaryDatabaseToAvailabilityGroup(string, string, string)
0x17ac5  ret
```
