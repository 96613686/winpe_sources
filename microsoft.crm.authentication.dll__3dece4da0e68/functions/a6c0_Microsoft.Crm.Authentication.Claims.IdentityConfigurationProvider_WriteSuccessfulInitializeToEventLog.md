# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::WriteSuccessfulInitializeToEventLog

- ea: `0xa6c0`
- end: `0xa6de`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::WriteSuccessfulInitializeToEventLog`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0x7670`
- `0xa6c0`

## pseudocode

```c

```

## disassembly

```asm
0xa6c0  ldc.i4.8
0xa6c1  ldc.i4   0x4339
0xa6c6  conv.i8
0xa6c7  ldarg.0
0xa6c8  brtrue.s loc_A6D1
0xa6ca  ldsfld   string [mscorlib]System.String::Empty
0xa6cf  br.s     loc_A6D7
0xa6d1  ldarg.0
0xa6d2  callvirt instance string [mscorlib]System.Object::ToString()
0xa6d7  ldnull
0xa6d8  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xa6dd  ret
```
