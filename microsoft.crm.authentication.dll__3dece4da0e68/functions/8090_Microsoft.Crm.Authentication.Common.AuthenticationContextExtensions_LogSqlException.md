# Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::LogSqlException

- ea: `0x8090`
- end: `0x80e4`
- name: `Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::LogSqlException`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8030`
- `0x14150`

## callees

- `0x7670`
- `0x78e0`

## string_xrefs

- `0x809c`: `AuthenticationContextExtensions.LogSqlException: Server: {0}, exception: {1}`
- `0x80c5`: `AuthenticationContextExtensions.LogSqlException: Server: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8090  ldarg.1
0x8091  ldc.i4   0xC0004336
0x8096  conv.u8
0x8097  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x809c  ldstr    aAuthentication_15// "AuthenticationContextExtensions.LogSqlE"...
0x80a1  ldc.i4.2
0x80a2  newarr   [mscorlib]System.Object
0x80a7  dup
0x80a8  ldc.i4.0
0x80a9  ldarg.0
0x80aa  callvirt instance string [System.Data]System.Data.SqlClient.SqlException::get_Server()
0x80af  stelem.ref
0x80b0  dup
0x80b1  ldc.i4.1
0x80b2  ldarg.0
0x80b3  stelem.ref
0x80b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80b9  ldnull
0x80ba  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0x80bf  ldarg.0
0x80c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80c5  ldstr    aAuthentication_16// "AuthenticationContextExtensions.LogSqlE"...
0x80ca  ldc.i4.1
0x80cb  newarr   [mscorlib]System.Object
0x80d0  dup
0x80d1  ldc.i4.0
0x80d2  ldarg.0
0x80d3  callvirt instance string [System.Data]System.Data.SqlClient.SqlException::get_Server()
0x80d8  stelem.ref
0x80d9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80de  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x80e3  ret
```
