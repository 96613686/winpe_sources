# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetPendingServiceInstanceMoveContext

- ea: `0x2a570`
- end: `0x2a5fe`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetPendingServiceInstanceMoveContext`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a4b0`

## callees

- `0x2a570`

## string_xrefs

- `0x2a5b6`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2a5b1`: `GetPendingServiceInstanceMoveContext`

## pseudocode

```c

```

## disassembly

```asm
0x2a570  ldloca.s 0
0x2a572  ldc.i4.0
0x2a573  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2a578  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2a57d  stloc.1
0x2a57e  ldloc.1
0x2a57f  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x2a584  ldarg.1
0x2a585  box      [mscorlib]System.Guid
0x2a58a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a58f  ldarg.0
0x2a590  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2a595  ldc.i4.2
0x2a596  newarr   [mscorlib]System.String
0x2a59b  dup
0x2a59c  ldc.i4.0
0x2a59d  ldstr    aContextid// "ContextId"
0x2a5a2  stelem.ref
0x2a5a3  dup
0x2a5a4  ldc.i4.1
0x2a5a5  ldstr    aIspendinguserd// "IsPendingUserDataSync"
0x2a5aa  stelem.ref
0x2a5ab  ldloc.1
0x2a5ac  ldc.i4   0x1F0
0x2a5b1  ldstr    aGetpendingserv// "GetPendingServiceInstanceMoveContext"
0x2a5b6  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2a5bb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2a5c0  stloc.2
0x2a5c1  ldloc.2
0x2a5c2  brfalse.s loc_2A5F8
0x2a5c4  ldloc.2
0x2a5c5  ldstr    aIspendinguserd// "IsPendingUserDataSync"
0x2a5ca  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a5cf  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x2a5d4  stloc.0
0x2a5d5  ldloca.s 0
0x2a5d7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2a5dc  brfalse.s loc_2A5F8
0x2a5de  ldloca.s 0
0x2a5e0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2a5e5  brfalse.s loc_2A5F8
0x2a5e7  ldloc.2
0x2a5e8  ldstr    aContextid// "ContextId"
0x2a5ed  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a5f2  unbox.any [mscorlib]System.Guid
0x2a5f7  ret
0x2a5f8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a5fd  ret
```
