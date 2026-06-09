# Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::Delete

- ea: `0x1bf10`
- end: `0x1bf6b`
- name: `Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::Delete`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1bf70`

## callees

- `0x1bf10`

## string_xrefs

- `0x1bf2f`: `Delete`
- `0x1bf34`: `D:\a\1\s\src\CrmLive\Admin\MonitoringResults\CrmMonitoringResultsService.cs`
- `0x1bf45`: `Deleted MonitoringResult, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1bf10  ldarg.1
0x1bf11  ldstr    aMonitoringresu_0// "MonitoringResult identifier"
0x1bf16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1bf1b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1bf20  stloc.0
0x1bf21  ldloc.0
0x1bf22  ldstr    aMonitoringresu// "MonitoringResults"
0x1bf27  ldarg.1
0x1bf28  box      [mscorlib]System.Guid
0x1bf2d  ldc.i4.s 0x47
0x1bf2f  ldstr    aDelete// "Delete"
0x1bf34  ldstr    aDA1SSrcCrmlive_38// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Monit"...
0x1bf39  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1bf3e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1bf43  ldc.i4.s 9
0x1bf45  ldstr    aDeletedMonitor// "Deleted MonitoringResult, Id=({0})"
0x1bf4a  ldc.i4.1
0x1bf4b  newarr   [mscorlib]System.Object
0x1bf50  dup
0x1bf51  ldc.i4.0
0x1bf52  ldarg.1
0x1bf53  box      [mscorlib]System.Guid
0x1bf58  stelem.ref
0x1bf59  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1bf5e  leave.s  loc_1BF6A
0x1bf60  ldloc.0
0x1bf61  brfalse.s loc_1BF69
0x1bf63  ldloc.0
0x1bf64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bf69  endfinally
0x1bf6a  ret
```
