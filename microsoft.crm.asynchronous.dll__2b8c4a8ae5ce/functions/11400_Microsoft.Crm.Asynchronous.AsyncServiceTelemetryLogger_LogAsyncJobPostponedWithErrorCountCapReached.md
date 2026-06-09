# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncJobPostponedWithErrorCountCapReached

- ea: `0x11400`
- end: `0x11414`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncJobPostponedWithErrorCountCapReached`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2950`

## callees

- `0x14000`
- `0x142b0`

## pseudocode

```c

```

## disassembly

```asm
0x11400  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11405  ldarg.1
0x11406  ldarg.2
0x11407  ldarg.3
0x11408  ldarg.s  4
0x1140a  ldarg.s  5
0x1140c  ldarg.s  6
0x1140e  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::AsyncJobPostponedWithErrorCountCapReached(valuetype [mscorlib]System.Guid organizationId, int32 errorCount, int32 timeUnitInMinutes, int32 operationType, valuetype [mscorlib]System.Guid workflowId, bool isSuspended)
0x11413  ret
```
