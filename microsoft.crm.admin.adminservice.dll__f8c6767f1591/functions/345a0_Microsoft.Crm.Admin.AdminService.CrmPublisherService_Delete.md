# Microsoft.Crm.Admin.AdminService.CrmPublisherService::Delete

- ea: `0x345a0`
- end: `0x3464c`
- name: `Microsoft.Crm.Admin.AdminService.CrmPublisherService::Delete`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x345a0`

## string_xrefs

- `0x345e2`: `Delete`
- `0x345d2`: `PluginPublishers`
- `0x345e7`: `D:\a\1\s\src\CrmLive\Admin\Publisher\CrmPublisherService.cs`
- `0x34604`: `Deleted Publisher, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x345a0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x345a5  ldc.i4.s 0x14
0x345a7  ldstr    aDeletingPublis// "Deleting Publisher, Id=({0})"
0x345ac  ldc.i4.1
0x345ad  newarr   [mscorlib]System.Object
0x345b2  dup
0x345b3  ldc.i4.0
0x345b4  ldarg.1
0x345b5  box      [mscorlib]System.Guid
0x345ba  stelem.ref
0x345bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x345c0  ldarg.1
0x345c1  ldstr    aPublisherid// "publisherId"
0x345c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x345cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x345d0  stloc.0
0x345d1  ldloc.0
0x345d2  ldstr    aPluginpublishe// "PluginPublishers"
0x345d7  ldarg.1
0x345d8  box      [mscorlib]System.Guid
0x345dd  ldc.i4   0x132
0x345e2  ldstr    aDelete// "Delete"
0x345e7  ldstr    aDA1SSrcCrmlive_60// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Publi"...
0x345ec  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x345f1  leave.s  loc_345FD
0x345f3  ldloc.0
0x345f4  brfalse.s loc_345FC
0x345f6  ldloc.0
0x345f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x345fc  endfinally
0x345fd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34602  ldc.i4.s 0x14
0x34604  ldstr    aDeletedPublish// "Deleted Publisher, Id=({0})"
0x34609  ldc.i4.1
0x3460a  newarr   [mscorlib]System.Object
0x3460f  dup
0x34610  ldc.i4.0
0x34611  ldarg.1
0x34612  box      [mscorlib]System.Guid
0x34617  stelem.ref
0x34618  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3461d  leave.s  loc_3464B
0x3461f  stloc.1
0x34620  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34625  ldc.i4.s 0x14
0x34627  ldstr    aExceptionDelet_9// "Exception deleting Publisher, Id=({0} :"...
0x3462c  ldc.i4.2
0x3462d  newarr   [mscorlib]System.Object
0x34632  dup
0x34633  ldc.i4.0
0x34634  ldarg.1
0x34635  box      [mscorlib]System.Guid
0x3463a  stelem.ref
0x3463b  dup
0x3463c  ldc.i4.1
0x3463d  ldloc.1
0x3463e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x34643  stelem.ref
0x34644  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34649  rethrow
0x3464b  ret
```
