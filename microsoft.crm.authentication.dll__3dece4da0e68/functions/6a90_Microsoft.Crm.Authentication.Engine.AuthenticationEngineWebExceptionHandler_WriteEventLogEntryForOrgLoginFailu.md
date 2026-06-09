# Microsoft.Crm.Authentication.Engine.AuthenticationEngineWebExceptionHandler::WriteEventLogEntryForOrgLoginFailure

- ea: `0x6a90`
- end: `0x6adb`
- name: `Microsoft.Crm.Authentication.Engine.AuthenticationEngineWebExceptionHandler::WriteEventLogEntryForOrgLoginFailure`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6970`

## callees

- `0x6a90`
- `0x7680`
- `0x78f0`

## string_xrefs

- `0x6a95`: `WriteOrgLoginFailureEvent`
- `0x6abe`: `AuthenticationEngineWebExceptionHandler.WriteEventLogEntryForOrgLoginFailure()`
- `0x6acb`: `AuthenticationEngineWebExceptionHandler.WriteEventLogEntryForOrgLoginFailure()`

## pseudocode

```c

```

## disassembly

```asm
0x6a90  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x6a95  ldstr    aWriteorgloginf// "WriteOrgLoginFailureEvent"
0x6a9a  ldc.i4.0
0x6a9b  callvirt T0x2B000005
0x6aa0  stloc.0
0x6aa1  ldloca.s 0
0x6aa3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6aa8  brfalse.s loc_6AD5
0x6aaa  ldloca.s 0
0x6aac  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6ab1  brfalse.s loc_6AD5
0x6ab3  ldarg.1
0x6ab4  brfalse.s loc_6AD5
0x6ab6  ldc.i4.1
0x6ab7  ldc.i4   0xC0004677
0x6abc  conv.u8
0x6abd  ldarg.1
0x6abe  ldstr    aAuthentication_3// "AuthenticationEngineWebExceptionHandler"...
0x6ac3  ldarg.2
0x6ac4  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventLevel, int64 eventId, class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal, string context, [opt] class [mscorlib]System.Exception exception)
0x6ac9  ldarg.2
0x6aca  ldarg.1
0x6acb  ldstr    aAuthentication_3// "AuthenticationEngineWebExceptionHandler"...
0x6ad0  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal, [opt] string context)
0x6ad5  leave.s  loc_6ADA
0x6ad7  pop
0x6ad8  leave.s  loc_6ADA
0x6ada  ret
```
