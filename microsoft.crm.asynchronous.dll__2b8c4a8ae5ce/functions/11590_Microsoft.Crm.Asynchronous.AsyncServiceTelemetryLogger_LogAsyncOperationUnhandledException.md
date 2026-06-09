# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException

- ea: `0x11590`
- end: `0x115a2`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException`
- size: `18`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x46b0`
- `0x8040`
- `0x8770`
- `0x11d70`
- `0x13700`
- `0x137b0`
- `0x16b90`

## callees

- `0x14000`
- `0x146f0`

## pseudocode

```c

```

## disassembly

```asm
0x11590  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11595  ldarg.1
0x11596  ldarg.2
0x11597  ldarg.3
0x11598  ldarg.s  4
0x1159a  ldarg.s  5
0x1159c  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid organizationId, string stackTrace, int32 operationType, valuetype [mscorlib]System.Guid eventId, string operationName)
0x115a1  ret
```
