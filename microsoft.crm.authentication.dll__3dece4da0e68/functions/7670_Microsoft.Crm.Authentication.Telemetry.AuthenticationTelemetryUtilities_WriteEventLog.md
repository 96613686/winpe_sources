# Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog

- ea: `0x7670`
- end: `0x767b`
- name: `Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog`
- size: `11`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d20`
- `0x8090`
- `0x81b0`
- `0xa3d0`
- `0xa6c0`
- `0xa740`
- `0xb9e0`
- `0xf480`

## callees

- `0x7680`

## pseudocode

```c

```

## disassembly

```asm
0x7670  ldarg.0
0x7671  ldarg.1
0x7672  ldnull
0x7673  ldarg.2
0x7674  ldarg.3
0x7675  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventLevel, int64 eventId, class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal, string context, [opt] class [mscorlib]System.Exception exception)
0x767a  ret
```
