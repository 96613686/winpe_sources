# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::UnlockMailboxes

- ea: `0x9550`
- end: `0x961b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::UnlockMailboxes`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbb30`

## callees

- `0xb880`

## string_xrefs

- `0x9563`: `UPDATE Mailboxbase\n					SET \n						HostId = NULL, ProcessingStateCode = @waitingState, PostponeMailboxProcessingUntil = @utcNow\n				\n					WHERE \n						HostId = @hostId`

## pseudocode

```c

```

## disassembly

```asm
0x9550  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x9555  stloc.0
0x9556  ldloc.0
0x9557  ldarg.0
0x9558  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass17_0::<>4__this
0x955d  ldarg.0
0x955e  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x9563  ldstr    aUpdateMailboxb_2// "UPDATE Mailboxbase\r\n\t\t\t\t\tSET \r"...
0x9568  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x956d  stloc.1
0x956e  ldloc.0
0x956f  ldloc.1
0x9570  ldc.i4.1
0x9571  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x9576  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::updateCommand
0x957b  ldloc.0
0x957c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::updateCommand
0x9581  ldstr    aWaitingstate// "@waitingState"
0x9586  ldc.i4.0
0x9587  box      [mscorlib]System.Int32
0x958c  ldloca.s 2
0x958e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9594  ldloc.2
0x9595  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x959a  ldloc.0
0x959b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::updateCommand
0x95a0  ldstr    aUtcnow// "@utcNow"
0x95a5  ldarg.0
0x95a6  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x95ab  box      [mscorlib]System.DateTime
0x95b0  ldloca.s 2
0x95b2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x95b8  ldloc.2
0x95b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x95be  ldloc.0
0x95bf  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass17_0::updateCommand
0x95c4  ldstr    aHostid// "@hostId"
0x95c9  ldarg.0
0x95ca  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x95cf  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x95d4  ldc.i4   0x100
0x95d9  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x95de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x95e3  ldarg.0
0x95e4  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x95e9  ldarg.0
0x95ea  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x95ef  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x95f4  ldstr    aUnlockmailboxe// "_UnlockMailboxes"
0x95f9  call     string [mscorlib]System.String::Concat(string, string)
0x95fe  ldarg.0
0x95ff  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x9604  ldloc.0
0x9605  ldftn    instance void <>c__DisplayClass17_0::<UnlockMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x960b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x9610  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x9615  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x961a  ret
```
