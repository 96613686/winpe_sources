# Microsoft.Crm.Sandbox.SandboxTracingService::Trace

- ea: `0x1e00`
- end: `0x1e7b`
- name: `Microsoft.Crm.Sandbox.SandboxTracingService::Trace`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d0`

## callees

- `0x1990`
- `0x1e00`

## string_xrefs

- `0x1e51`: `SandboxTracingService.Trace: trace buffer exceeded - truncating`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.0
0x1e01  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e06  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x1e0b  ldc.i4.0
0x1e0c  ble.s    loc_1E1A
0x1e0e  ldarg.0
0x1e0f  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1e19  pop
0x1e1a  ldarg.2
0x1e1b  ldlen
0x1e1c  brfalse.s loc_1E2C
0x1e1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e23  ldarg.1
0x1e24  ldarg.2
0x1e25  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e2a  starg.s  1
0x1e2c  ldarg.0
0x1e2d  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e32  ldarg.1
0x1e33  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1e38  pop
0x1e39  ldarg.0
0x1e3a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e3f  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x1e44  ldc.i4   0x2800
0x1e49  ble.s    loc_1E7A
0x1e4b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e50  ldc.i4.2
0x1e51  ldstr    aSandboxtracing// "SandboxTracingService.Trace: trace buff"...
0x1e56  ldnull
0x1e57  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1e5c  ldarg.0
0x1e5d  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e62  ldc.i4.0
0x1e63  ldarg.0
0x1e64  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e69  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x1e6e  ldc.i4   0x2800
0x1e73  sub
0x1e74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x1e79  pop
0x1e7a  ret
```
