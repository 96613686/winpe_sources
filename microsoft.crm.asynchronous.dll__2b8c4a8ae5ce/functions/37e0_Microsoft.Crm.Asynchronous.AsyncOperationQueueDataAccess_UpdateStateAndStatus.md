# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateStateAndStatus

- ea: `0x37e0`
- end: `0x3806`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateStateAndStatus`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x37e0`
- `0x45d0`
- `0x4fc0`
- `0x16530`

## pseudocode

```c

```

## disassembly

```asm
0x37e0  ldarg.0
0x37e1  ldarg.1
0x37e2  ldarg.2
0x37e3  ldc.i4.0
0x37e4  newobj   instance void UpdateStateAndStatusCommand::.ctor(class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess queueDataAccess, class Microsoft.Crm.Asynchronous.AsyncEventState newEventState, class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, [opt] bool checkForCompltedJobs)
0x37e9  stloc.0
0x37ea  ldloc.0
0x37eb  ldarg.0
0x37ec  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x37f1  callvirt instance valuetype CommandResult Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::Execute(class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase queueManager)
0x37f6  ldc.i4.2
0x37f7  bne.un.s loc_3805
0x37f9  ldarg.0
0x37fa  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x37ff  ldloc.0
0x3800  callvirt instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommand(class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand command)
0x3805  ret
```
