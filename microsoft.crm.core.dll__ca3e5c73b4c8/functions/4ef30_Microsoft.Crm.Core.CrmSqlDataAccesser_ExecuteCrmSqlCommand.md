# Microsoft.Crm.Core.CrmSqlDataAccesser::ExecuteCrmSqlCommand

- ea: `0x4ef30`
- end: `0x4efd0`
- name: `Microsoft.Crm.Core.CrmSqlDataAccesser::ExecuteCrmSqlCommand`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1eaa0`
- `0x1f4d0`
- `0x331c0`
- `0x331e0`
- `0x352e0`
- `0x4ef30`
- `0x54770`
- `0x548c0`
- `0x55d00`
- `0x55d20`
- `0x58230`
- `0x5aec0`
- `0x5af20`

## string_xrefs

- `0x4ef8a`: `CommandCompleted`
- `0x4efa6`: `CommandCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x4ef30  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x4ef35  stloc.0
0x4ef36  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x4ef3b  stloc.1
0x4ef3c  ldsfld   string [mscorlib]System.String::Empty
0x4ef41  stloc.2
0x4ef42  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4ef47  ldc.i4.s 0x1D
0x4ef49  ldstr    a0// "{0}"
0x4ef4e  ldc.i4.1
0x4ef4f  newarr   [mscorlib]System.Object
0x4ef54  dup
0x4ef55  ldc.i4.0
0x4ef56  ldarg.2
0x4ef57  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x4ef5c  stelem.ref
0x4ef5d  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4ef62  ldloc.0
0x4ef63  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x4ef68  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0x4ef6d  stloc.s  4
0x4ef6f  ldarg.1
0x4ef70  ldarg.2
0x4ef71  callvirt instance var<u1> class [mscorlib]System.Func`2<class Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, mvar<u1>>::Invoke(void)
0x4ef76  stloc.3
0x4ef77  leave.s  loc_4EF85
0x4ef79  ldloc.s  4
0x4ef7b  brfalse.s loc_4EF84
0x4ef7d  ldloc.s  4
0x4ef7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ef84  endfinally
0x4ef85  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0x4ef8a  ldstr    aCommandcomplet// "CommandCompleted"
0x4ef8f  ldarg.2
0x4ef90  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x4ef95  ldc.i4.1
0x4ef96  ldloc.1
0x4ef97  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x4ef9c  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::CommandExecuted(string eventName, class [System.Data]System.Data.IDbCommand command, bool includeCommandText, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x4efa1  ldloc.3
0x4efa2  stloc.s  5
0x4efa4  leave.s  loc_4EFCD
0x4efa6  ldstr    aCommandcomplet// "CommandCompleted"
0x4efab  ldarg.2
0x4efac  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x4efb1  ldloc.1
0x4efb2  ldstr    aErrorExecuting// "Error executing executeMethod"
0x4efb7  call     string Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::ExceptionHandler(class [mscorlib]System.Exception exception, string eventName, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, string error)
0x4efbc  stloc.2
0x4efbd  rethrow
0x4efbf  ldarg.2
0x4efc0  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x4efc5  ldloc.0
0x4efc6  ldloc.2
0x4efc7  call     void Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.TimeTracker timer, string errorCode)
0x4efcc  endfinally
0x4efcd  ldloc.s  5
0x4efcf  ret
```
