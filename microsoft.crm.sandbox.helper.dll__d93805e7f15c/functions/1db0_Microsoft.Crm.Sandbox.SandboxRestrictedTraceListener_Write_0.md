# Microsoft.Crm.Sandbox.SandboxRestrictedTraceListener::Write_0

- ea: `0x1db0`
- end: `0x1dcf`
- name: `Microsoft.Crm.Sandbox.SandboxRestrictedTraceListener::Write_0`
- size: `31`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1c60`
- `0x1cb0`
- `0x1d10`
- `0x1d90`
- `0x1da0`

## callees

- `0x1990`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1db5  callvirt instance bool [mscorlib]System.AppDomain::get_IsFullyTrusted()
0x1dba  brtrue.s loc_1DCE
0x1dbc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dc1  ldarg.2
0x1dc2  ldarg.1
0x1dc3  ldarg.0
0x1dc4  ldfld    string Microsoft.Crm.Sandbox.SandboxRestrictedTraceListener::_traceCategory
0x1dc9  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1dce  ret
```
