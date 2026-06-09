# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::.ctor

- ea: `0x4d40`
- end: `0x4d86`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::.ctor`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4ae0`
- `0x54b0`

## callees

- `0x4e90`

## pseudocode

```c

```

## disassembly

```asm
0x4d40  ldarg.0
0x4d41  ldc.i4.1
0x4d42  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor(valuetype [System.Core]System.Threading.LockRecursionPolicy)
0x4d47  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x4d4c  ldarg.0
0x4d4d  call     instance void [mscorlib]System.Object::.ctor()
0x4d52  ldarg.0
0x4d53  ldarg.1
0x4d54  stfld    string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::containerId
0x4d59  ldarg.0
0x4d5a  ldsfld   string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::basePath
0x4d5f  ldarg.2
0x4d60  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4d65  stfld    string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::workingDirectory
0x4d6a  ldarg.0
0x4d6b  ldarg.3
0x4d6c  stfld    valuetype Microsoft.Crm.Sandbox.WorkerProcess.Tracing.TablePartitioning Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::partitioning
0x4d71  ldarg.0
0x4d72  ldarg.s  4
0x4d74  stfld    valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::level
0x4d79  ldarg.0
0x4d7a  ldarg.0
0x4d7b  ldfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x4d80  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::EnsureValidTableHandle(native int tableHandle)
0x4d85  ret
```
