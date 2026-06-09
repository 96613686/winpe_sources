# Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry

- ea: `0x4320`
- end: `0x4334`
- name: `Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry`
- size: `20`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2f70`
- `0x3060`
- `0x33a0`
- `0x3410`
- `0x3fc0`
- `0x47b0`

## pseudocode

```c

```

## disassembly

```asm
0x4320  ldarg.0
0x4321  ldarg.1
0x4322  call     string [mscorlib]System.String::Format(string, object[])
0x4327  stloc.0
0x4328  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x432d  ldloc.0
0x432e  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogDBUpdateThrottlingEvent(string)
0x4333  ret
```
