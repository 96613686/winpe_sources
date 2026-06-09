# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::CreateConnection

- ea: `0x6a40`
- end: `0x6a5c`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::CreateConnection`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x69f0`

## callees

- `0x6a40`

## pseudocode

```c

```

## disassembly

```asm
0x6a40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x6a45  stloc.0
0x6a46  ldloc.0
0x6a47  ldc.i4.1
0x6a48  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x6a4d  stloc.1
0x6a4e  leave.s  loc_6A5A
0x6a50  ldloc.0
0x6a51  brfalse.s loc_6A59
0x6a53  ldloc.0
0x6a54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a59  endfinally
0x6a5a  ldloc.1
0x6a5b  ret
```
