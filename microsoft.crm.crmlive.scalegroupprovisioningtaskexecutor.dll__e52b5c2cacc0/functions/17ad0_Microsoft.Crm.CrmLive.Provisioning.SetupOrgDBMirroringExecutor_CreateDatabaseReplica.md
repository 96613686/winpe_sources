# Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabaseReplica

- ea: `0x17ad0`
- end: `0x17c19`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateDatabaseReplica`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x170b0`

## callees

- `0x17700`
- `0x17ad0`
- `0x17e70`

## string_xrefs

- `0x17b17`: `CreateDatabaseReplica: Availability Group: {0} Primary: {1} Secondary: {2}`
- `0x17bcf`: `Error in CreateDatabaseReplica attempting to create replica for database {0} on server: {1}. Primary server was {2} Exception {3}`
- `0x17bfb`: `Error in CreateDatabaseReplica attempting to create replica for database {0} on server: {1}. Primary server was {2}`

## pseudocode

```c

```

## disassembly

```asm
0x17ad0  ldarg.1
0x17ad1  ldstr    aQueueitemid// "queueItemId"
0x17ad6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x17adb  ldarg.2
0x17adc  ldstr    aOrganizationid// "organizationId"
0x17ae1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x17ae6  ldarg.3
0x17ae7  ldstr    aAvailabilitygr_0// "availabilityGroupName"
0x17aec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17af1  ldarg.s  4
0x17af3  ldstr    aPrimaryreplica// "primaryReplica"
0x17af8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17afd  ldarg.s  6
0x17aff  ldstr    aDatabasename_0// "databaseName"
0x17b04  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17b09  ldarg.s  5
0x17b0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17b10  brfalse.s loc_17B17
0x17b12  leave    loc_17C18
0x17b17  ldstr    aCreatedatabase_0// "CreateDatabaseReplica: Availability Gro"...
0x17b1c  ldc.i4.3
0x17b1d  newarr   [mscorlib]System.Object
0x17b22  dup
0x17b23  ldc.i4.0
0x17b24  ldarg.3
0x17b25  stelem.ref
0x17b26  dup
0x17b27  ldc.i4.1
0x17b28  ldarg.s  4
0x17b2a  stelem.ref
0x17b2b  dup
0x17b2c  ldc.i4.2
0x17b2d  ldarg.s  5
0x17b2f  stelem.ref
0x17b30  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17b35  ldarg.0
0x17b36  ldarg.1
0x17b37  ldarg.2
0x17b38  ldarg.3
0x17b39  ldarg.s  4
0x17b3b  ldarg.s  5
0x17b3d  ldarg.s  6
0x17b3f  ldc.i4.0
0x17b40  ldc.i4.1
0x17b41  call     instance bool Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, bool forceRemove, bool dropDatabase)
0x17b46  brtrue.s loc_17B4D
0x17b48  leave    loc_17C18
0x17b4d  ldarg.s  7
0x17b4f  ldind.ref
0x17b50  brtrue.s loc_17B79
0x17b52  ldstr    aBackingUpDatab// "Backing up database {0} on replica {1} "
0x17b57  ldc.i4.2
0x17b58  newarr   [mscorlib]System.Object
0x17b5d  dup
0x17b5e  ldc.i4.0
0x17b5f  ldarg.s  6
0x17b61  stelem.ref
0x17b62  dup
0x17b63  ldc.i4.1
0x17b64  ldarg.s  4
0x17b66  stelem.ref
0x17b67  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17b6c  ldarg.s  7
0x17b6e  ldarg.s  6
0x17b70  ldarg.s  4
0x17b72  ldarg.2
0x17b73  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::BackupDatabase(string, string, valuetype [mscorlib]System.Guid)
0x17b78  stind.ref
0x17b79  ldarg.0
0x17b7a  ldarg.2
0x17b7b  ldarg.s  5
0x17b7d  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::CreateCustomerManagedKey(valuetype [mscorlib]System.Guid organizationId, string server)
0x17b82  ldstr    aRestoringDatab// "Restoring database {0} on replica {1} "
0x17b87  ldc.i4.2
0x17b88  newarr   [mscorlib]System.Object
0x17b8d  dup
0x17b8e  ldc.i4.0
0x17b8f  ldarg.s  6
0x17b91  stelem.ref
0x17b92  dup
0x17b93  ldc.i4.1
0x17b94  ldarg.s  5
0x17b96  stelem.ref
0x17b97  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17b9c  ldarg.s  6
0x17b9e  ldarg.s  5
0x17ba0  ldarg.s  7
0x17ba2  ldind.ref
0x17ba3  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::RestoreDatabase(string, string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData)
0x17ba8  ldstr    aAddingSecondar// "Adding secondary database {0} on replic"...
0x17bad  ldc.i4.2
0x17bae  newarr   [mscorlib]System.Object
0x17bb3  dup
0x17bb4  ldc.i4.0
0x17bb5  ldarg.s  6
0x17bb7  stelem.ref
0x17bb8  dup
0x17bb9  ldc.i4.1
0x17bba  ldarg.s  5
0x17bbc  stelem.ref
0x17bbd  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17bc2  ldarg.3
0x17bc3  ldarg.s  5
0x17bc5  ldarg.s  6
0x17bc7  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::AddSecondaryDatabaseToAvailabilityGroup(string, string, string)
0x17bcc  leave.s  loc_17C18
0x17bce  stloc.0
0x17bcf  ldstr    aErrorInCreated// "Error in CreateDatabaseReplica attempti"...
0x17bd4  ldc.i4.4
0x17bd5  newarr   [mscorlib]System.Object
0x17bda  dup
0x17bdb  ldc.i4.0
0x17bdc  ldarg.s  6
0x17bde  stelem.ref
0x17bdf  dup
0x17be0  ldc.i4.1
0x17be1  ldarg.s  5
0x17be3  stelem.ref
0x17be4  dup
0x17be5  ldc.i4.2
0x17be6  ldarg.s  4
0x17be8  stelem.ref
0x17be9  dup
0x17bea  ldc.i4.3
0x17beb  ldloc.0
0x17bec  callvirt instance string [mscorlib]System.Object::ToString()
0x17bf1  stelem.ref
0x17bf2  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17bf7  ldloc.0
0x17bf8  ldarg.2
0x17bf9  ldc.i4.s 0xA
0x17bfb  ldstr    aErrorInCreated_0// "Error in CreateDatabaseReplica attempti"...
0x17c00  ldarg.s  6
0x17c02  ldarg.s  5
0x17c04  ldarg.s  4
0x17c06  call     string [mscorlib]System.String::Format(string, object, object, object)
0x17c0b  ldc.i4.0
0x17c0c  newarr   [mscorlib]System.Object
0x17c11  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17c16  rethrow
0x17c18  ret
```
