# Microsoft.Crm.Asynchronous.AsyncService::AsyncServiceStop

- ea: `0x12c0`
- end: `0x13bb`
- name: `Microsoft.Crm.Asynchronous.AsyncService::AsyncServiceStop`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x12b0`

## callees

- `0xc40`
- `0xc50`
- `0x1270`
- `0x12c0`
- `0x16a0`
- `0x1830`
- `0x1850`

## string_xrefs

- `0x1300`: `Stopping service`
- `0x1372`: `AsyncService has been stopped: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldarg.0
0x12c1  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x12c6  ldc.i4.3
0x12c7  beq.s    loc_12E6
0x12c9  ldarg.0
0x12ca  ldc.r8   5.0
0x12d3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x12d8  stloc.0
0x12d9  ldloca.s 0
0x12db  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x12e0  conv.i4
0x12e1  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::RequestAdditionalTime(int32)
0x12e6  ldarg.0
0x12e7  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WaitForStartupSequenceComplete()
0x12ec  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x12f1  ldc.i4.s 0x15
0x12f3  ldstr    a0// "{0}"
0x12f8  ldc.i4.1
0x12f9  newarr   [mscorlib]System.Object
0x12fe  dup
0x12ff  ldc.i4.0
0x1300  ldstr    aStoppingServic// "Stopping service"
0x1305  stelem.ref
0x1306  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x130b  ldarg.0
0x130c  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StopComponents()
0x1311  ldarg.0
0x1312  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePeriodicWorker Microsoft.Crm.Asynchronous.AsyncService::heartbeatWorker
0x1317  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x131c  call     void [Microsoft.Crm.Sandbox.Client]Microsoft.Crm.Sandbox.SandboxHostManager::Shutdown()
0x1321  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x1326  ldarg.0
0x1327  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncService::get_AsyncStartStopActivityId()
0x132c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceProcessSettings::get_Identifier()
0x1331  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncStop(valuetype [mscorlib]System.Guid, string)
0x1336  ldarg.0
0x1337  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0x133c  brfalse.s loc_136B
0x133e  ldarg.0
0x133f  ldc.i4.4
0x1340  ldc.i4   0x40004401
0x1345  conv.i8
0x1346  ldc.i4.1
0x1347  newarr   [mscorlib]System.Object
0x134c  dup
0x134d  ldc.i4.0
0x134e  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0x1353  stelem.ref
0x1354  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0x1359  ldarg.0
0x135a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0x135f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1364  ldarg.0
0x1365  ldnull
0x1366  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0x136b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1370  ldc.i4.s 0x15
0x1372  ldstr    aAsyncserviceHa// "AsyncService has been stopped: {0}"
0x1377  ldc.i4.1
0x1378  newarr   [mscorlib]System.Object
0x137d  dup
0x137e  ldc.i4.0
0x137f  ldarg.0
0x1380  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x1385  stelem.ref
0x1386  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x138b  ldarg.0
0x138c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener Microsoft.Crm.Asynchronous.AsyncService::_miniDumpTraceListener
0x1391  brfalse.s loc_13AA
0x1393  call     class [System]System.Diagnostics.TraceListenerCollection [System]System.Diagnostics.Trace::get_Listeners()
0x1398  ldarg.0
0x1399  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener Microsoft.Crm.Asynchronous.AsyncService::_miniDumpTraceListener
0x139e  callvirt instance void [System]System.Diagnostics.TraceListenerCollection::Remove(class [System]System.Diagnostics.TraceListener)
0x13a3  ldarg.0
0x13a4  ldnull
0x13a5  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener Microsoft.Crm.Asynchronous.AsyncService::_miniDumpTraceListener
0x13aa  ldarg.0
0x13ab  ldfld    class [mscorlib]System.IDisposable Microsoft.Crm.Asynchronous.AsyncService::webApp
0x13b0  dup
0x13b1  brtrue.s loc_13B5
0x13b3  pop
0x13b4  ret
0x13b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13ba  ret
```
