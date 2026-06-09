# Microsoft.Crm.Asynchronous.AsyncOperationExecutionManager::CreateHandler

- ea: `0x3170`
- end: `0x31a1`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationExecutionManager::CreateHandler`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2cd0`
- `0x2e60`
- `0x3170`
- `0x11e50`

## pseudocode

```c

```

## disassembly

```asm
0x3170  ldarg.0
0x3171  call     instance var<u1> class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase, class Microsoft.Crm.Asynchronous.AsyncEvent>::get_InternalEvent()
0x3176  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEvent::get_IsRecurrenceEvent()
0x317b  brfalse.s loc_3199
0x317d  ldarg.1
0x317e  ldtoken  Microsoft.Crm.Asynchronous.CreateOneOperationFromRecurrencePatternCommand
0x3183  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3188  ldarg.0
0x3189  call     instance var<u1> class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase, class Microsoft.Crm.Asynchronous.AsyncEvent>::get_InternalEvent()
0x318e  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x3193  callvirt instance class Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand Microsoft.Crm.Asynchronous.IAsyncEventHandlerFactory::CreateCommand(class [mscorlib]System.Type commandType, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0x3198  ret
0x3199  ldarg.0
0x319a  ldarg.1
0x319b  call     instance class Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase, class Microsoft.Crm.Asynchronous.AsyncEvent>::CreateHandler(class Microsoft.Crm.Asynchronous.IAsyncEventHandlerFactory)
0x31a0  ret
```
