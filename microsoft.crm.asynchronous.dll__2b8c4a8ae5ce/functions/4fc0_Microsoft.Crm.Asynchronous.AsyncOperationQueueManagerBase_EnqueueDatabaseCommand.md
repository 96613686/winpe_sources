# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommand

- ea: `0x4fc0`
- end: `0x4fea`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommand`
- size: `42`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2cc0`
- `0x37e0`
- `0x3810`
- `0x165c0`

## callees

- `0x4fc0`

## pseudocode

```c

```

## disassembly

```asm
0x4fc0  ldarg.0
0x4fc1  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::_executionQueue
0x4fc6  stloc.0
0x4fc7  ldc.i4.0
0x4fc8  stloc.1
0x4fc9  ldloc.0
0x4fca  ldloca.s 1
0x4fcc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4fd1  ldarg.0
0x4fd2  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::_executionQueue
0x4fd7  ldarg.1
0x4fd8  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::Enqueue(var<u1>)
0x4fdd  leave.s  loc_4FE9
0x4fdf  ldloc.1
0x4fe0  brfalse.s loc_4FE8
0x4fe2  ldloc.0
0x4fe3  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4fe8  endfinally
0x4fe9  ret
```
