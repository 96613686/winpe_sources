# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommandsFromQueue

- ea: `0x4e60`
- end: `0x4ea7`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommandsFromQueue`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4df0`
- `0x174a0`

## callees

- `0x4e60`

## pseudocode

```c

```

## disassembly

```asm
0x4e60  ldarg.1
0x4e61  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::get_Count()
0x4e66  ldc.i4.0
0x4e67  ble.s    loc_4EA6
0x4e69  ldarg.0
0x4e6a  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::_executionQueue
0x4e6f  stloc.0
0x4e70  ldc.i4.0
0x4e71  stloc.1
0x4e72  ldloc.0
0x4e73  ldloca.s 1
0x4e75  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4e7a  ldnull
0x4e7b  stloc.2
0x4e7c  br.s     loc_4E91
0x4e7e  ldarg.1
0x4e7f  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::Dequeue()
0x4e84  stloc.2
0x4e85  ldarg.0
0x4e86  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::_executionQueue
0x4e8b  ldloc.2
0x4e8c  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::Enqueue(var<u1>)
0x4e91  ldarg.1
0x4e92  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::get_Count()
0x4e97  ldc.i4.0
0x4e98  bgt.s    loc_4E7E
0x4e9a  leave.s  loc_4EA6
0x4e9c  ldloc.1
0x4e9d  brfalse.s loc_4EA5
0x4e9f  ldloc.0
0x4ea0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4ea5  endfinally
0x4ea6  ret
```
