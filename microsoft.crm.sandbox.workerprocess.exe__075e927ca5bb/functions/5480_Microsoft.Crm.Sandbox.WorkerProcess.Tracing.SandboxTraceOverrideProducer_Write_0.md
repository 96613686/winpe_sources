# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::Write_0

- ea: `0x5480`
- end: `0x5494`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::Write_0`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x53e0`

## pseudocode

```c

```

## disassembly

```asm
0x5480  ldarg.0
0x5481  ldarg.1
0x5482  ldarg.2
0x5483  ldarg.3
0x5484  ldarg.s  4
0x5486  ldarg.s  5
0x5488  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x548d  ldnull
0x548e  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x5493  ret
```
