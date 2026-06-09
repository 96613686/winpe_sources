# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::IsInitialDirectoryObjectSync

- ea: `0x2a740`
- end: `0x2a7d3`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::IsInitialDirectoryObjectSync`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29cb0`

## callees

- `0x2a740`

## string_xrefs

- `0x2a765`: `DirectoryObjectRevision`
- `0x2a78d`: `DirectoryObjectRevision`
- `0x2a79f`: `DirectoryObjectRevision`
- `0x2a7ac`: `DirectoryObjectRevision`
- `0x2a77e`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2a779`: `IsInitialDirectoryObjectSync`

## pseudocode

```c

```

## disassembly

```asm
0x2a740  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2a745  stloc.0
0x2a746  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2a74b  stloc.1
0x2a74c  ldloc.1
0x2a74d  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x2a752  ldarg.0
0x2a753  box      [mscorlib]System.Guid
0x2a758  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a75d  ldc.i4.1
0x2a75e  newarr   [mscorlib]System.String
0x2a763  dup
0x2a764  ldc.i4.0
0x2a765  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0x2a76a  stelem.ref
0x2a76b  stloc.2
0x2a76c  ldloc.0
0x2a76d  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2a772  ldloc.2
0x2a773  ldloc.1
0x2a774  ldc.i4   0x229
0x2a779  ldstr    aIsinitialdirec// "IsInitialDirectoryObjectSync"
0x2a77e  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2a783  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2a788  stloc.3
0x2a789  ldloc.3
0x2a78a  brfalse.s loc_2A799
0x2a78c  ldloc.3
0x2a78d  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0x2a792  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x2a797  brtrue.s loc_2A79E
0x2a799  ldc.i4.1
0x2a79a  stloc.s  4
0x2a79c  leave.s  loc_2A7D0
0x2a79e  ldloc.3
0x2a79f  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0x2a7a4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a7a9  brfalse.s loc_2A7BD
0x2a7ab  ldloc.3
0x2a7ac  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0x2a7b1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a7b6  unbox.any [mscorlib]System.Int64
0x2a7bb  brtrue.s loc_2A7C2
0x2a7bd  ldc.i4.1
0x2a7be  stloc.s  4
0x2a7c0  leave.s  loc_2A7D0
0x2a7c2  leave.s  loc_2A7CE
0x2a7c4  ldloc.0
0x2a7c5  brfalse.s loc_2A7CD
0x2a7c7  ldloc.0
0x2a7c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a7cd  endfinally
0x2a7ce  ldc.i4.0
0x2a7cf  ret
0x2a7d0  ldloc.s  4
0x2a7d2  ret
```
