# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogs

- ea: `0x11270`
- end: `0x11284`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrganizationBacklogs`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x127c0`

## callees

- `0x14000`
- `0x14630`

## pseudocode

```c

```

## disassembly

```asm
0x11270  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x11275  stloc.0
0x11276  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x1127b  ldarg.1
0x1127c  ldarg.2
0x1127d  ldloc.0
0x1127e  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::OrgAsyncBacklogDiagnosticsEvent(valuetype [mscorlib]System.Guid organizationId, int32 count, valuetype [mscorlib]System.Guid telemetryActivityId)
0x11283  ret
```
