# Microsoft.Crm.WebServices.LangProvisioningService::WriteSystemEventLog

- ea: `0xe8a0`
- end: `0xe8d8`
- name: `Microsoft.Crm.WebServices.LangProvisioningService::WriteSystemEventLog`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe7b0`

## callees

- `0xe8a0`

## string_xrefs

- `0xe8a7`: `MSCRMWebService`

## pseudocode

```c

```

## disassembly

```asm
0xe8a0  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0xe8a5  stloc.0
0xe8a6  ldloc.0
0xe8a7  ldstr    aMscrmwebservic// "MSCRMWebService"
0xe8ac  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0xe8b1  ldloc.0
0xe8b2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0xe8b7  stloc.1
0xe8b8  ldloc.1
0xe8b9  ldarg.1
0xe8ba  ldarg.2
0xe8bb  ldarg.3
0xe8bc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xe8c1  leave.s  loc_E8D7
0xe8c3  ldloc.1
0xe8c4  brfalse.s loc_E8CC
0xe8c6  ldloc.1
0xe8c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8cc  endfinally
0xe8cd  ldloc.0
0xe8ce  brfalse.s loc_E8D6
0xe8d0  ldloc.0
0xe8d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8d6  endfinally
0xe8d7  ret
```
