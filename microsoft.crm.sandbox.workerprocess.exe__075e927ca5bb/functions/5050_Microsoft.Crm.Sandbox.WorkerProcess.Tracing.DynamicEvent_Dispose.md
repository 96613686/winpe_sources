# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Dispose

- ea: `0x5050`
- end: `0x5081`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Dispose`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5090`
- `0x50a0`

## callees

- `0x4f20`
- `0x5050`

## pseudocode

```c

```

## disassembly

```asm
0x5050  ldarg.0
0x5051  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x5056  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterWriteLock()
0x505b  ldarg.0
0x505c  ldarg.0
0x505d  ldfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x5062  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::CloseHandle(native int tableHandle)
0x5067  ldarg.0
0x5068  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x506d  stfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x5072  leave.s  loc_5080
0x5074  ldarg.0
0x5075  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x507a  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x507f  endfinally
0x5080  ret
```
