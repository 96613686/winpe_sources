# Microsoft.Crm.Sandbox.SandboxTraceWriter::Write

- ea: `0x1c70`
- end: `0x1ced`
- name: `Microsoft.Crm.Sandbox.SandboxTraceWriter::Write`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cf0`

## callees

- `0x1170`
- `0x1c70`

## string_xrefs

- `0x1cac`: `SandboxTrace.Write: Failed to run trace function. Format {0}, Args {1}, Exception {2} `

## pseudocode

```c

```

## disassembly

```asm
0x1c70  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::Instance
0x1c75  ldc.i4.0
0x1c76  ldarg.1
0x1c77  ldarg.2
0x1c78  ldarg.3
0x1c79  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c7e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_RequestId()
0x1c83  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c88  ldarg.s  5
0x1c8a  ldarg.s  6
0x1c8c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::LogTrace(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TraceRedirection, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, valuetype [System]System.Diagnostics.TraceLevel, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, object[])
0x1c91  leave.s  loc_1CEC
0x1c93  stloc.0
0x1c94  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::Instance
0x1c99  ldc.i4.0
0x1c9a  ldarg.1
0x1c9b  ldarg.2
0x1c9c  ldc.i4.1
0x1c9d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ca2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_RequestId()
0x1ca7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1cac  ldstr    aSandboxtraceWr// "SandboxTrace.Write: Failed to run trace"...
0x1cb1  ldc.i4.3
0x1cb2  newarr   [mscorlib]System.Object
0x1cb7  dup
0x1cb8  ldc.i4.0
0x1cb9  ldarg.s  5
0x1cbb  brfalse.s loc_1CC1
0x1cbd  ldarg.s  5
0x1cbf  br.s     loc_1CC6
0x1cc1  ldstr    aNull// "null"
0x1cc6  stelem.ref
0x1cc7  dup
0x1cc8  ldc.i4.1
0x1cc9  ldarg.s  6
0x1ccb  brfalse.s loc_1CDB
0x1ccd  ldarg.s  6
0x1ccf  ldlen
0x1cd0  conv.i4
0x1cd1  stloc.1
0x1cd2  ldloca.s 1
0x1cd4  call     instance string [mscorlib]System.Int32::ToString()
0x1cd9  br.s     loc_1CE0
0x1cdb  ldstr    aNull// "null"
0x1ce0  stelem.ref
0x1ce1  dup
0x1ce2  ldc.i4.2
0x1ce3  ldloc.0
0x1ce4  stelem.ref
0x1ce5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::LogTrace(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TraceRedirection, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, valuetype [System]System.Diagnostics.TraceLevel, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, object[])
0x1cea  leave.s  loc_1CEC
0x1cec  ret
```
