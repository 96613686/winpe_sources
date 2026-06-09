# Microsoft.Crm.Sandbox.SandboxWorker::StopListening

- ea: `0x3970`
- end: `0x399f`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::StopListening`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x45f0`
- `0x4720`

## callees

- `0x3970`

## pseudocode

```c

```

## disassembly

```asm
0x3970  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3975  ldc.i4.s 0x26
0x3977  ldstr    aSandboxworkerS_1// "SandboxWorker.StopListening"
0x397c  ldc.i4.0
0x397d  newarr   [mscorlib]System.Object
0x3982  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3987  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxWorker::_listener
0x398c  brfalse.s loc_399E
0x398e  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxWorker::_listener
0x3993  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3998  ldnull
0x3999  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxWorker::_listener
0x399e  ret
```
