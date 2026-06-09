# Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::TryCleanupBackupsForDeletedOrganization

- ea: `0x14260`
- end: `0x142cc`
- name: `Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::TryCleanupBackupsForDeletedOrganization`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14110`

## callees

- `0x14260`
- `0x1bea0`
- `0x1c3b0`

## string_xrefs

- `0x1429d`: `TryCleanupBackupsForDeletedOrganization`
- `0x142a2`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\DeleteOrganizationBackupExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x14260  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x14265  stloc.0
0x14266  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1426b  stloc.1
0x1426c  ldloc.1
0x1426d  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x14272  ldarg.0
0x14273  box      [mscorlib]System.Guid
0x14278  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1427d  ldloc.0
0x1427e  ldstr    aOrganizationli// "OrganizationLifecycle"
0x14283  ldc.i4.1
0x14284  newarr   [mscorlib]System.String
0x14289  dup
0x1428a  ldc.i4.0
0x1428b  ldstr    aId// "Id"
0x14290  stelem.ref
0x14291  ldc.i4.1
0x14292  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x14297  dup
0x14298  ldc.i4.0
0x14299  ldloc.1
0x1429a  stelem.ref
0x1429b  ldc.i4.s 0x41
0x1429d  ldstr    aTrycleanupback// "TryCleanupBackupsForDeletedOrganization"
0x142a2  ldstr    aDDbsShDccm2110_27// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x142a7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x142ac  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x142b1  brfalse.s loc_142BF
0x142b3  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x142b8  ldarg.0
0x142b9  ldarg.1
0x142ba  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::TryCleanupBackups(valuetype [mscorlib]System.Guid orgId, string backupPath)
0x142bf  leave.s  loc_142CB
0x142c1  ldloc.0
0x142c2  brfalse.s loc_142CA
0x142c4  ldloc.0
0x142c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x142ca  endfinally
0x142cb  ret
```
