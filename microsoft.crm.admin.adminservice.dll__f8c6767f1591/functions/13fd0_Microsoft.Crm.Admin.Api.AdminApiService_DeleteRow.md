# Microsoft.Crm.Admin.Api.AdminApiService::DeleteRow

- ea: `0x13fd0`
- end: `0x14031`
- name: `Microsoft.Crm.Admin.Api.AdminApiService::DeleteRow`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x34a10`

## callees

- `0x13fd0`
- `0x14040`

## string_xrefs

- `0x13fe9`: `D:\a\1\s\src\CrmLive\Admin\Common\AdminApiService.cs`
- `0x13fe4`: `DeleteRow`
- `0x13ff5`: `Record does not exist or delete failed`
- `0x14007`: `Deleted {0}, conditions=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x13fd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x13fd5  stloc.0
0x13fd6  ldloc.0
0x13fd7  ldarg.0
0x13fd8  ldc.i4.1
0x13fd9  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x13fde  dup
0x13fdf  ldc.i4.0
0x13fe0  ldarg.1
0x13fe1  stelem.ref
0x13fe2  ldc.i4.s 0x50
0x13fe4  ldstr    aDeleterow// "DeleteRow"
0x13fe9  ldstr    aDA1SSrcCrmlive_26// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Commo"...
0x13fee  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x13ff3  brtrue.s loc_14000
0x13ff5  ldstr    aRecordDoesNotE// "Record does not exist or delete failed"
0x13ffa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x13fff  throw
0x14000  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x14005  ldc.i4.s 9
0x14007  ldstr    aDeleted0Condit// "Deleted {0}, conditions=({0})"
0x1400c  ldc.i4.2
0x1400d  newarr   [mscorlib]System.Object
0x14012  dup
0x14013  ldc.i4.0
0x14014  ldarg.0
0x14015  stelem.ref
0x14016  dup
0x14017  ldc.i4.1
0x14018  ldarg.1
0x14019  call     string Microsoft.Crm.Admin.Api.AdminApiService::ConditionToString(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag condition)
0x1401e  stelem.ref
0x1401f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14024  leave.s  loc_14030
0x14026  ldloc.0
0x14027  brfalse.s loc_1402F
0x14029  ldloc.0
0x1402a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1402f  endfinally
0x14030  ret
```
