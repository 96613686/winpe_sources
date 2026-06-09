# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgExitedLockedState

- ea: `0x11390`
- end: `0x1139c`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgExitedLockedState`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c30`

## callees

- `0x14000`
- `0x140f0`

## pseudocode

```c

```

## disassembly

```asm
0x11390  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11395  ldarg.1
0x11396  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::OrgExitedLockedStateEvent(valuetype [mscorlib]System.Guid organizationId)
0x1139b  ret
```
