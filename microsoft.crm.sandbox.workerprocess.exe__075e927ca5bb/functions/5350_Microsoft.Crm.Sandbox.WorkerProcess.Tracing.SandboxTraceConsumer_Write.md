# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Write

- ea: `0x5350`
- end: `0x5365`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Write`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5250`

## callees

- `0x5120`

## pseudocode

```c

```

## disassembly

```asm
0x5350  ldarg.0
0x5351  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tableWriter
0x5356  ldarg.1
0x5357  ldarg.2
0x5358  ldarg.3
0x5359  ldarg.s  4
0x535b  ldarg.s  5
0x535d  ldarg.s  6
0x535f  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x5364  ret
```
