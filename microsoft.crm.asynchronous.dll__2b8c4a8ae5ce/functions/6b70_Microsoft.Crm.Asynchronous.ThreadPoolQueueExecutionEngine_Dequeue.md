# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::Dequeue

- ea: `0x6b70`
- end: `0x6c0e`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::Dequeue`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x6ac0`

## callees

- `0x6b70`
- `0xb520`
- `0xb620`
- `0x120e0`

## pseudocode

```c

```

## disassembly

```asm
0x6b70  ldnull
0x6b71  stloc.0
0x6b72  ldarg.0
0x6b73  ldfld    class Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_settings
0x6b78  callvirt instance bool Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings::get_AllowAsynchronousCallbacks()
0x6b7d  brfalse.s loc_6BC4
0x6b7f  ldarg.0
0x6b80  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_priorityEventQueue
0x6b85  callvirt instance int32 Microsoft.Crm.Asynchronous.MultiOrgQueue::get_Count()
0x6b8a  ldc.i4.0
0x6b8b  ble.s    loc_6BC4
0x6b8d  ldarg.0
0x6b8e  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_priorityEventQueue
0x6b93  stloc.1
0x6b94  ldc.i4.0
0x6b95  stloc.2
0x6b96  ldloc.1
0x6b97  ldloca.s 2
0x6b99  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6b9e  ldarg.0
0x6b9f  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_priorityEventQueue
0x6ba4  callvirt instance int32 Microsoft.Crm.Asynchronous.MultiOrgQueue::get_Count()
0x6ba9  ldc.i4.0
0x6baa  ble.s    loc_6BB8
0x6bac  ldarg.0
0x6bad  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_priorityEventQueue
0x6bb2  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation Microsoft.Crm.Asynchronous.MultiOrgQueue::Dequeue()
0x6bb7  stloc.0
0x6bb8  leave.s  loc_6BC4
0x6bba  ldloc.2
0x6bbb  brfalse.s loc_6BC3
0x6bbd  ldloc.1
0x6bbe  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6bc3  endfinally
0x6bc4  ldloc.0
0x6bc5  brtrue.s loc_6C0C
0x6bc7  ldarg.0
0x6bc8  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x6bcd  callvirt instance int32 Microsoft.Crm.Asynchronous.MultiOrgQueue::get_Count()
0x6bd2  ldc.i4.0
0x6bd3  ble.s    loc_6C0C
0x6bd5  ldarg.0
0x6bd6  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x6bdb  stloc.1
0x6bdc  ldc.i4.0
0x6bdd  stloc.2
0x6bde  ldloc.1
0x6bdf  ldloca.s 2
0x6be1  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6be6  ldarg.0
0x6be7  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x6bec  callvirt instance int32 Microsoft.Crm.Asynchronous.MultiOrgQueue::get_Count()
0x6bf1  ldc.i4.0
0x6bf2  ble.s    loc_6C00
0x6bf4  ldarg.0
0x6bf5  ldfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x6bfa  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation Microsoft.Crm.Asynchronous.MultiOrgQueue::Dequeue()
0x6bff  stloc.0
0x6c00  leave.s  loc_6C0C
0x6c02  ldloc.2
0x6c03  brfalse.s loc_6C0B
0x6c05  ldloc.1
0x6c06  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6c0b  endfinally
0x6c0c  ldloc.0
0x6c0d  ret
```
