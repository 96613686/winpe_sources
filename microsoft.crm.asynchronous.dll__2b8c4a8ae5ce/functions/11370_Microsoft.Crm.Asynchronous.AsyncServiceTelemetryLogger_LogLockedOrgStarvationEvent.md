# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogLockedOrgStarvationEvent

- ea: `0x11370`
- end: `0x1137e`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogLockedOrgStarvationEvent`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb9b0`

## callees

- `0x14000`
- `0x14090`

## pseudocode

```c

```

## disassembly

```asm
0x11370  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11375  ldarg.1
0x11376  ldarg.2
0x11377  ldarg.3
0x11378  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LockedOrgStarvationEvent(valuetype [mscorlib]System.DateTime lastAcquiredTime, int32 lockedOrgCount, string orgs)
0x1137d  ret
```
