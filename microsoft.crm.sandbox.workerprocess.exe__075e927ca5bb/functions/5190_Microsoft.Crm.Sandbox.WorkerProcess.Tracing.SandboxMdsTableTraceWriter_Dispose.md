# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Dispose

- ea: `0x5190`
- end: `0x51c2`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Dispose`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x51d0`

## callees

- `0x5090`
- `0x5190`

## pseudocode

```c

```

## disassembly

```asm
0x5190  ldarg.0
0x5191  ldfld    bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_isDisposed
0x5196  brfalse.s loc_5199
0x5198  ret
0x5199  ldarg.0
0x519a  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_errorTracer
0x519f  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Dispose()
0x51a4  ldarg.0
0x51a5  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_warningTracer
0x51aa  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Dispose()
0x51af  ldarg.0
0x51b0  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_infoTracer
0x51b5  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Dispose()
0x51ba  ldarg.0
0x51bb  ldc.i4.1
0x51bc  stfld    bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_isDisposed
0x51c1  ret
```
