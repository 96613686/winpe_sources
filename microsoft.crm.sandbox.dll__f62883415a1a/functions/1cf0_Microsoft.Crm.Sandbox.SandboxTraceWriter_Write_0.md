# Microsoft.Crm.Sandbox.SandboxTraceWriter::Write_0

- ea: `0x1cf0`
- end: `0x1d35`
- name: `Microsoft.Crm.Sandbox.SandboxTraceWriter::Write_0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1170`
- `0x1c70`
- `0x1cf0`

## string_xrefs

- `0x1d1e`: `SandboxTrace.Write: Failed to run trace function. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldarg.0
0x1cf1  ldarg.1
0x1cf2  ldarg.2
0x1cf3  ldarg.3
0x1cf4  ldarg.s  4
0x1cf6  ldarg.s  5
0x1cf8  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x1cfd  ldnull
0x1cfe  call     instance void Microsoft.Crm.Sandbox.SandboxTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x1d03  leave.s  loc_1D34
0x1d05  stloc.0
0x1d06  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::Instance
0x1d0b  ldc.i4.0
0x1d0c  ldarg.1
0x1d0d  ldarg.2
0x1d0e  ldc.i4.1
0x1d0f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d14  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_RequestId()
0x1d19  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d1e  ldstr    aSandboxtraceWr_0// "SandboxTrace.Write: Failed to run trace"...
0x1d23  ldc.i4.1
0x1d24  newarr   [mscorlib]System.Object
0x1d29  dup
0x1d2a  ldc.i4.0
0x1d2b  ldloc.0
0x1d2c  stelem.ref
0x1d2d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TracingEventSource::LogTrace(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.TraceRedirection, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, valuetype [System]System.Diagnostics.TraceLevel, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, object[])
0x1d32  leave.s  loc_1D34
0x1d34  ret
```
