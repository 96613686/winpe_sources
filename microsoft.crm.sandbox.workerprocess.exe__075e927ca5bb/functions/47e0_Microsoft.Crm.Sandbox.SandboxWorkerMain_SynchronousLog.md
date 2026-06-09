# Microsoft.Crm.Sandbox.SandboxWorkerMain::SynchronousLog

- ea: `0x47e0`
- end: `0x47fc`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::SynchronousLog`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x45f0`
- `0x4750`

## callees

- `0x47e0`
- `0x5240`

## pseudocode

```c

```

## disassembly

```asm
0x47e0  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerMain::_drawbridgeEnabled
0x47e5  brfalse.s loc_47FB
0x47e7  ldsfld   class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer Microsoft.Crm.Sandbox.SandboxWorkerMain::_traceConsumer
0x47ec  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::OverrideTraceWriter(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxTraceWriter)
0x47f1  ldsfld   class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer Microsoft.Crm.Sandbox.SandboxWorkerMain::_traceConsumer
0x47f6  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Stop()
0x47fb  ret
```
