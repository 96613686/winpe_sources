# Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace

- ea: `0x1990`
- end: `0x19e1`
- name: `Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace`
- size: `81`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe0`
- `0x1c0`
- `0x3a0`
- `0x510`
- `0x610`
- `0x720`
- `0x7b0`
- `0xe70`
- `0x10d0`
- `0x1240`
- `0x18d0`
- `0x1930`
- `0x19f0`
- `0x1a20`
- `0x1db0`
- `0x1e00`
- `0x2060`
- `0x2150`

## callees

- `0x1990`
- `0x1b30`
- `0x1b50`

## pseudocode

```c

```

## disassembly

```asm
0x1990  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Sandbox.SandboxRestrictedTrace::get_TracingService()
0x1995  brtrue.s loc_1999
0x1997  leave.s  loc_19E0
0x1999  call     valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.SandboxRestrictedTrace::get_TraceLevel()
0x199e  brfalse.s loc_19A8
0x19a0  call     valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.SandboxRestrictedTrace::get_TraceLevel()
0x19a5  ldarg.1
0x19a6  bge.s    loc_19AA
0x19a8  leave.s  loc_19E0
0x19aa  ldc.i4.4
0x19ab  newarr   [mscorlib]System.Object
0x19b0  stloc.0
0x19b1  ldloc.0
0x19b2  ldc.i4.0
0x19b3  ldarg.0
0x19b4  box      [mscorlib]System.Guid
0x19b9  stelem.ref
0x19ba  ldloc.0
0x19bb  ldc.i4.1
0x19bc  ldarg.1
0x19bd  box      [System]System.Diagnostics.TraceLevel
0x19c2  stelem.ref
0x19c3  ldloc.0
0x19c4  ldc.i4.2
0x19c5  ldarg.3
0x19c6  stelem.ref
0x19c7  ldloc.0
0x19c8  ldc.i4.3
0x19c9  ldsfld   object Microsoft.Crm.Sandbox.SandboxTraceContextHelper::TraceParameters
0x19ce  stelem.ref
0x19cf  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Sandbox.SandboxRestrictedTrace::get_TracingService()
0x19d4  ldarg.2
0x19d5  ldloc.0
0x19d6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x19db  leave.s  loc_19E0
0x19dd  pop
0x19de  leave.s  loc_19E0
0x19e0  ret
```
