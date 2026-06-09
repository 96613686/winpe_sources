# UpdateStateAndStatusCommand::TryRemoveEvent

- ea: `0x165c0`
- end: `0x16636`
- name: `UpdateStateAndStatusCommand::TryRemoveEvent`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16870`

## callees

- `0x3090`
- `0x45d0`
- `0x4fc0`
- `0x165c0`
- `0x16640`

## pseudocode

```c

```

## disassembly

```asm
0x165c0  ldarg.0
0x165c1  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x165c6  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEventState::get_CanRemoveEvent()
0x165cb  brfalse.s loc_16634
0x165cd  ldarg.0
0x165ce  call     instance void UpdateStateAndStatusCommand::SetupDeleteCommand()
0x165d3  ldarg.0
0x165d4  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x165d9  isinst   DeleteUsingSqlCommand
0x165de  brfalse.s loc_165FA
0x165e0  ldarg.0
0x165e1  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x165e6  ldarg.0
0x165e7  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x165ec  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x165f1  callvirt instance valuetype CommandResult Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::Execute(class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase queueManager)
0x165f6  brtrue.s loc_165FA
0x165f8  ldc.i4.1
0x165f9  ret
0x165fa  ldarg.1
0x165fb  brfalse.s loc_16634
0x165fd  ldarg.0
0x165fe  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x16603  ldarg.0
0x16604  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x16609  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x1660e  callvirt instance valuetype CommandResult Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::Execute(class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase queueManager)
0x16613  brtrue.s loc_16617
0x16615  ldc.i4.1
0x16616  ret
0x16617  ldarg.0
0x16618  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x1661d  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x16622  ldarg.0
0x16623  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x16628  callvirt instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommand(class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand command)
0x1662d  ldarg.0
0x1662e  ldnull
0x1662f  stfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x16634  ldc.i4.0
0x16635  ret
```
