# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncJobErrorCountInTimeUnit

- ea: `0x113e0`
- end: `0x113f2`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncJobErrorCountInTimeUnit`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7c50`

## callees

- `0x14000`
- `0x14260`

## pseudocode

```c

```

## disassembly

```asm
0x113e0  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x113e5  ldarg.1
0x113e6  ldarg.2
0x113e7  ldarg.3
0x113e8  ldarg.s  4
0x113ea  ldarg.s  5
0x113ec  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::AsyncJobErrorCountInTimeUnit(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid operationTypeId, int32 errorCount, int32 maxErrorAllowed, int32 timeUnitInMinutes)
0x113f1  ret
```
