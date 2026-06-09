# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::UpdateOrganizationDirectoryLinkRevision

- ea: `0x2b690`
- end: `0x2b71e`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::UpdateOrganizationDirectoryLinkRevision`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x29cb0`
- `0x2b240`

## callees

- `0x2b690`

## string_xrefs

- `0x2b706`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2b69d`: `DirectoryLinkRevision`
- `0x2b6ae`: `DirectoryLinkRevisionUpdateTime`
- `0x2b701`: `UpdateOrganizationDirectoryLinkRevision`

## pseudocode

```c

```

## disassembly

```asm
0x2b690  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2b695  stloc.0
0x2b696  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b69b  stloc.1
0x2b69c  ldloc.1
0x2b69d  ldstr    aDirectorylinkr// "DirectoryLinkRevision"
0x2b6a2  ldarg.1
0x2b6a3  box      [mscorlib]System.Int64
0x2b6a8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b6ad  ldloc.1
0x2b6ae  ldstr    aDirectorylinkr_0// "DirectoryLinkRevisionUpdateTime"
0x2b6b3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2b6b8  box      [mscorlib]System.DateTime
0x2b6bd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b6c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b6c7  stloc.2
0x2b6c8  ldloc.2
0x2b6c9  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x2b6ce  ldarg.0
0x2b6cf  box      [mscorlib]System.Guid
0x2b6d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b6d9  ldloc.2
0x2b6da  ldstr    aContextid// "ContextId"
0x2b6df  ldc.i4.5
0x2b6e0  ldnull
0x2b6e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b6e6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b6eb  ldloc.0
0x2b6ec  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2b6f1  ldloc.1
0x2b6f2  ldc.i4.1
0x2b6f3  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2b6f8  dup
0x2b6f9  ldc.i4.0
0x2b6fa  ldloc.2
0x2b6fb  stelem.ref
0x2b6fc  ldc.i4   0x464
0x2b701  ldstr    aUpdateorganiza_2// "UpdateOrganizationDirectoryLinkRevision"
0x2b706  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2b70b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2b710  pop
0x2b711  leave.s  loc_2B71D
0x2b713  ldloc.0
0x2b714  brfalse.s loc_2B71C
0x2b716  ldloc.0
0x2b717  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b71c  endfinally
0x2b71d  ret
```
