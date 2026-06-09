# Microsoft.Crm.Sandbox.SandboxTrace::Trace_0

- ea: `0x1380`
- end: `0x13f6`
- name: `Microsoft.Crm.Sandbox.SandboxTrace::Trace_0`
- size: `118`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xef0`
- `0x1410`
- `0x1440`
- `0x1490`
- `0x14c0`

## callees

- `0xd10`
- `0x1130`
- `0x1380`
- `0x14f0`
- `0x1740`

## string_xrefs

- `0x13b4`: `_traceWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1380  ldarg.2
0x1381  ldarg.3
0x1382  call     bool Microsoft.Crm.Sandbox.SandboxTrace::TraceEnabled(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory)
0x1387  ldarg.s  5
0x1389  or
0x138a  brfalse.s loc_13F5
0x138c  ldarg.1
0x138d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1392  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1397  brfalse.s loc_13A0
0x1399  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x139e  starg.s  1
0x13a0  ldarg.1
0x13a1  ldarg.3
0x13a2  ldarg.s  6
0x13a4  ldarg.s  7
0x13a6  ldloca.s 0
0x13a8  ldloca.s 1
0x13aa  call     void Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args, [out] string& newFormat, [out] object[]& newArgs)
0x13af  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x13b4  ldstr    aTracewriter// "_traceWriter"
0x13b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13be  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x13c3  ldarg.1
0x13c4  ldarg.3
0x13c5  ldarg.2
0x13c6  ldarg.s  4
0x13c8  ldloc.0
0x13c9  ldloc.1
0x13ca  callvirt instance void Microsoft.Crm.Sandbox.ISandboxTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x13cf  ldarg.0
0x13d0  brfalse.s loc_13F5
0x13d2  ldarg.1
0x13d3  ldarg.3
0x13d4  ldarg.0
0x13d5  callvirt instance string [mscorlib]System.Object::ToString()
0x13da  ldnull
0x13db  ldloca.s 0
0x13dd  ldloca.s 1
0x13df  call     void Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args, [out] string& newFormat, [out] object[]& newArgs)
0x13e4  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x13e9  ldarg.1
0x13ea  ldarg.3
0x13eb  ldarg.2
0x13ec  ldarg.s  4
0x13ee  ldloc.0
0x13ef  ldloc.1
0x13f0  callvirt instance void Microsoft.Crm.Sandbox.ISandboxTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x13f5  ret
```
