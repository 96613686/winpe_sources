# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::Enqueue_0

- ea: `0x6970`
- end: `0x6998`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::Enqueue_0`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x68d0`
- `0x68e0`

## callees

- `0x6970`
- `0x69a0`
- `0xb690`
- `0x13050`
- `0x15670`
- `0x15680`

## pseudocode

```c

```

## disassembly

```asm
0x6970  ldarg.1
0x6971  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation::get_SemaphoreManager()
0x6976  brfalse.s loc_698A
0x6978  ldarg.1
0x6979  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation::get_SemaphoreManager()
0x697e  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager::ReleaseSemaphores()
0x6983  ldarg.1
0x6984  ldnull
0x6985  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation::set_SemaphoreManager(class Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager value)
0x698a  ldarg.2
0x698b  ldarg.1
0x698c  callvirt instance void Microsoft.Crm.Asynchronous.MultiOrgQueue::Enqueue(class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation operation)
0x6991  ldarg.0
0x6992  call     instance void Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeStartNewThread()
0x6997  ret
```
