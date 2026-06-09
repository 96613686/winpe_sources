# Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::RetrieveDatabaseRevision

- ea: `0xe970`
- end: `0xe9ff`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::RetrieveDatabaseRevision`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xe7d0`
- `0xe890`

## callees

- `0xe930`
- `0xe970`

## string_xrefs

- `0xe99d`: `DirectoryObjectRevision`
- `0xe9c1`: `DirectoryObjectRevision`
- `0xe9cf`: `DirectoryObjectRevision`
- `0xe9dd`: `DirectoryObjectRevision`
- `0xe9b3`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\OrganizationObjectRevisionUpdater.cs`

## pseudocode

```c

```

## disassembly

```asm
0xe970  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xe975  stloc.0
0xe976  ldc.i4.m1
0xe977  conv.i8
0xe978  stloc.1
0xe979  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe97e  stloc.2
0xe97f  ldloc.2
0xe980  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xe985  ldarg.0
0xe986  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::get_OrganizationId()
0xe98b  box      [mscorlib]System.Guid
0xe990  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe995  ldc.i4.1
0xe996  newarr   [mscorlib]System.String
0xe99b  dup
0xe99c  ldc.i4.0
0xe99d  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0xe9a2  stelem.ref
0xe9a3  stloc.3
0xe9a4  ldloc.0
0xe9a5  ldstr    aOrganizationli// "OrganizationLifecycle"
0xe9aa  ldloc.3
0xe9ab  ldloc.2
0xe9ac  ldc.i4.s 0x25
0xe9ae  ldstr    aRetrievedataba// "RetrieveDatabaseRevision"
0xe9b3  ldstr    aDDbsShDccm2110_18// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xe9b8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe9bd  stloc.s  4
0xe9bf  ldloc.s  4
0xe9c1  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0xe9c6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xe9cb  brfalse.s loc_E9ED
0xe9cd  ldloc.s  4
0xe9cf  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0xe9d4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe9d9  brfalse.s loc_E9ED
0xe9db  ldloc.s  4
0xe9dd  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0xe9e2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe9e7  unbox.any [mscorlib]System.Int64
0xe9ec  stloc.1
0xe9ed  ldloc.1
0xe9ee  stloc.s  5
0xe9f0  leave.s  loc_E9FC
0xe9f2  ldloc.0
0xe9f3  brfalse.s loc_E9FB
0xe9f5  ldloc.0
0xe9f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe9fb  endfinally
0xe9fc  ldloc.s  5
0xe9fe  ret
```
