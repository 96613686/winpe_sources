# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Finalize

- ea: `0x51d0`
- end: `0x51e0`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Finalize`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5190`
- `0x51d0`

## pseudocode

```c

```

## disassembly

```asm
0x51d0  ldarg.0
0x51d1  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Dispose()
0x51d6  leave.s  loc_51DF
0x51d8  ldarg.0
0x51d9  call     instance void [mscorlib]System.Object::Finalize()
0x51de  endfinally
0x51df  ret
```
