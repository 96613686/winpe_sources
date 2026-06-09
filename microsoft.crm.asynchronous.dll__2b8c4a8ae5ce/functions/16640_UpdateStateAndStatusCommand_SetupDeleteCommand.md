# UpdateStateAndStatusCommand::SetupDeleteCommand

- ea: `0x16640`
- end: `0x166ad`
- name: `UpdateStateAndStatusCommand::SetupDeleteCommand`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x165c0`

## callees

- `0x2f10`
- `0x3070`
- `0x3090`
- `0x63f0`
- `0xd5a0`
- `0x16640`
- `0x16940`

## string_xrefs

- `0x1664b`: `SetupDeleteCommand requires CanRemoveEvent=true`

## pseudocode

```c

```

## disassembly

```asm
0x16640  ldarg.0
0x16641  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x16646  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEventState::get_CanRemoveEvent()
0x1664b  ldstr    aSetupdeletecom// "SetupDeleteCommand requires CanRemoveEv"...
0x16650  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x16655  ldarg.0
0x16656  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x1665b  brtrue.s loc_166AC
0x1665d  ldarg.0
0x1665e  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x16663  callvirt instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.AsyncEventState::get_HandlerResult()
0x16668  isinst   Microsoft.Crm.Asynchronous.AsyncRemoveEventResult
0x1666d  stloc.0
0x1666e  ldloc.0
0x1666f  brfalse.s loc_166AC
0x16671  ldarg.0
0x16672  ldloc.0
0x16673  callvirt instance class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::get_DeleteCommand()
0x16678  stfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x1667d  ldarg.0
0x1667e  ldfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x16683  brtrue.s loc_166AC
0x16685  ldarg.0
0x16686  ldarg.0
0x16687  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x1668c  ldarg.0
0x1668d  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x16692  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x16697  ldarg.0
0x16698  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x1669d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x166a2  newobj   instance void DeleteUsingSqlCommand::.ctor(class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration, valuetype [mscorlib]System.Guid eventId)
0x166a7  stfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand UpdateStateAndStatusCommand::_deleteCommand
0x166ac  ret
```
