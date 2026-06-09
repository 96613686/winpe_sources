# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgEnteredLockedState

- ea: `0x11380`
- end: `0x1138c`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgEnteredLockedState`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c30`

## callees

- `0x14000`
- `0x140d0`

## pseudocode

```c

```

## disassembly

```asm
0x11380  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11385  ldarg.1
0x11386  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::OrgEnteredLockedStateEvent(valuetype [mscorlib]System.Guid organizationId)
0x1138b  ret
```
