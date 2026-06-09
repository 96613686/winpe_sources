# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Write_0

- ea: `0x5370`
- end: `0x538e`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Write_0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5120`

## pseudocode

```c

```

## disassembly

```asm
0x5370  ldarg.0
0x5371  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tableWriter
0x5376  ldarg.1
0x5377  ldarg.2
0x5378  ldarg.3
0x5379  ldarg.s  4
0x537b  ldarg.s  5
0x537d  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x5382  ldc.i4.0
0x5383  newarr   [mscorlib]System.Object
0x5388  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x538d  ret
```
