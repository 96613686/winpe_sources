# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncDelay

- ea: `0x11570`
- end: `0x1158c`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncDelay`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe0d0`

## callees

- `0x14000`
- `0x14670`

## pseudocode

```c

```

## disassembly

```asm
0x11570  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11575  ldarg.1
0x11576  ldarg.2
0x11577  ldarg.3
0x11578  ldarg.s  4
0x1157a  ldarg.s  5
0x1157c  ldarg.s  6
0x1157e  ldarg.s  7
0x11580  ldarg.s  8
0x11582  ldarg.s  9
0x11584  ldarg.s  0xA
0x11586  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogOrgAsyncDelay(string queueName, valuetype [mscorlib]System.Guid organizationId, float64 averageDbDelay, float64 maxDbDelay, float64 averageInMemoryQueueDelay, float64 maxInMemoryQueueDelay, float64 averageExecutionTime, float64 maxExecutionTime, int32 completedEventCount, float64 timeIntervalInMinutes)
0x1158b  ret
```
