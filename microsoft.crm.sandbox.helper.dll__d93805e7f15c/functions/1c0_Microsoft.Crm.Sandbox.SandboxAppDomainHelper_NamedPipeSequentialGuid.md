# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::NamedPipeSequentialGuid

- ea: `0x1c0`
- end: `0x1ec`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::NamedPipeSequentialGuid`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x170`
- `0x1c0`
- `0x1990`

## string_xrefs

- `0x1d1`: `NamedPipeSequentialGuid: Could not read sequential newGuid from named pipes. Falling back to Guid.NewGuid()`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ReadSequentialGuidFromNamedPipes()
0x1c6  stloc.0
0x1c7  leave.s  loc_1EA
0x1c9  stloc.1
0x1ca  ldarg.0
0x1cb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_organizationId
0x1d0  ldc.i4.1
0x1d1  ldstr    aNamedpipeseque// "NamedPipeSequentialGuid: Could not read"...
0x1d6  ldloc.1
0x1d7  call     string [mscorlib]System.String::Concat(object, object)
0x1dc  ldnull
0x1dd  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1e2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1e7  stloc.0
0x1e8  leave.s  loc_1EA
0x1ea  ldloc.0
0x1eb  ret
```
