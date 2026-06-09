# Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry

- ea: `0x4340`
- end: `0x4354`
- name: `Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry`
- size: `20`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2b30`
- `0x2d10`
- `0x2dc0`
- `0x2f70`
- `0x3060`
- `0x3410`
- `0x3730`
- `0x3b70`
- `0x3e10`
- `0x4360`
- `0x4480`
- `0x45d0`
- `0x47b0`

## pseudocode

```c

```

## disassembly

```asm
0x4340  ldarg.0
0x4341  ldarg.1
0x4342  call     string [mscorlib]System.String::Format(string, object[])
0x4347  stloc.0
0x4348  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x434d  ldloc.0
0x434e  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogDBUpdateScheduledEvent(string)
0x4353  ret
```
