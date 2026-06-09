# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_ThreadId

- ea: `0x4cf0`
- end: `0x4d0c`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_ThreadId`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d90`

## callees

- `0x4cf0`

## pseudocode

```c

```

## disassembly

```asm
0x4cf0  ldsfld   int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::threadId
0x4cf5  brtrue.s loc_4D06
0x4cf7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x4cfc  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x4d01  stsfld   int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::threadId
0x4d06  ldsfld   int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::threadId
0x4d0b  ret
```
