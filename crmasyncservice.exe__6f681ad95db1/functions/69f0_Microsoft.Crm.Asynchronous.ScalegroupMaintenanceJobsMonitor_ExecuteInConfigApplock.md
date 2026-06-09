# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ExecuteInConfigApplock

- ea: `0x69f0`
- end: `0x6a34`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ExecuteInConfigApplock`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6380`
- `0x63f0`

## callees

- `0x69f0`
- `0x6a40`

## pseudocode

```c

```

## disassembly

```asm
0x69f0  ldarg.0
0x69f1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::CreateConnection()
0x69f6  stloc.0
0x69f7  ldloc.0
0x69f8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x69fd  ldloc.0
0x69fe  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::BeginTransaction()
0x6a03  stloc.1
0x6a04  ldarg.1
0x6a05  ldloc.0
0x6a06  ldloc.1
0x6a07  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, class [System.Data]System.Data.IDbTransaction)
0x6a0c  stloc.2
0x6a0d  ldarg.2
0x6a0e  callvirt instance void [mscorlib]System.Action::Invoke()
0x6a13  leave.s  loc_6A33
0x6a15  ldloc.2
0x6a16  brfalse.s loc_6A1E
0x6a18  ldloc.2
0x6a19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a1e  endfinally
0x6a1f  ldloc.1
0x6a20  brfalse.s loc_6A28
0x6a22  ldloc.1
0x6a23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a28  endfinally
0x6a29  ldloc.0
0x6a2a  brfalse.s loc_6A32
0x6a2c  ldloc.0
0x6a2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a32  endfinally
0x6a33  ret
```
