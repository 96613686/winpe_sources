# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogExecutingOperationElapsedTime

- ea: `0x11480`
- end: `0x114a3`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogExecutingOperationElapsedTime`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xae90`

## callees

- `0x14000`
- `0x143d0`

## pseudocode

```c

```

## disassembly

```asm
0x11480  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11485  ldarg.1
0x11486  ldarg.2
0x11487  ldarg.3
0x11488  ldarg.s  4
0x1148a  ldarg.s  5
0x1148c  ldarg.s  6
0x1148e  ldarg.s  7
0x11490  ldarga.s 8
0x11492  constrained. Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus
0x11498  callvirt instance string [mscorlib]System.Object::ToString()
0x1149d  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogExecutingOperationElapsedTime(string queueName, valuetype [mscorlib]System.Guid organizationId, int32 operationType, valuetype [mscorlib]System.Guid eventId, valuetype [mscorlib]System.DateTime enqueueTime, valuetype [mscorlib]System.DateTime startTime, float64 elapsedTimeInSec, string eventStatus)
0x114a2  ret
```
