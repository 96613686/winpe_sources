# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::UnlockMailboxes

- ea: `0x99b0`
- end: `0x9ab2`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::UnlockMailboxes`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9ee0`
- `0xba10`

## string_xrefs

- `0x99c3`: `UPDATE Mailboxbase\n					SET \n						HostId = NULL, ProcessingStateCode = @waitingState, PostponeMailboxProcessingUntil = @utcNow\n					WHERE \n						HostId = @hostId and MailboxId = @mailboxId`

## pseudocode

```c

```

## disassembly

```asm
0x99b0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x99b5  stloc.0
0x99b6  ldloc.0
0x99b7  ldarg.0
0x99b8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug <>c__DisplayClass4_0::<>4__this
0x99bd  ldarg.0
0x99be  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x99c3  ldstr    aUpdateMailboxb_4// "UPDATE Mailboxbase\r\n\t\t\t\t\tSET \r"...
0x99c8  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x99cd  stloc.1
0x99ce  ldloc.0
0x99cf  ldloc.1
0x99d0  ldc.i4.1
0x99d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x99d6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass4_0::updateCommand
0x99db  ldloc.0
0x99dc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass4_0::updateCommand
0x99e1  ldstr    aWaitingstate// "@waitingState"
0x99e6  ldc.i4.0
0x99e7  box      [mscorlib]System.Int32
0x99ec  ldloca.s 2
0x99ee  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x99f4  ldloc.2
0x99f5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x99fa  ldloc.0
0x99fb  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass4_0::updateCommand
0x9a00  ldstr    aHostid// "@hostId"
0x9a05  ldarg.0
0x9a06  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9a0b  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9a10  ldstr    aDebugger// "Debugger"
0x9a15  call     string [mscorlib]System.String::Concat(string, string)
0x9a1a  ldloca.s 2
0x9a1c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9a22  ldloc.2
0x9a23  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9a28  ldloc.0
0x9a29  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass4_0::updateCommand
0x9a2e  ldstr    aMailboxid_0// "@mailboxId"
0x9a33  ldarg.0
0x9a34  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9a39  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_DebugContext()
0x9a3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext::get_MailboxId()
0x9a43  box      [mscorlib]System.Guid
0x9a48  ldloca.s 2
0x9a4a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9a50  ldloc.2
0x9a51  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9a56  ldloc.0
0x9a57  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass4_0::updateCommand
0x9a5c  ldstr    aUtcnow// "@utcNow"
0x9a61  ldarg.0
0x9a62  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x9a67  box      [mscorlib]System.DateTime
0x9a6c  ldloca.s 2
0x9a6e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9a74  ldloc.2
0x9a75  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9a7a  ldarg.0
0x9a7b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x9a80  ldarg.0
0x9a81  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9a86  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x9a8b  ldstr    aUnlockmailboxe// "_UnlockMailboxes"
0x9a90  call     string [mscorlib]System.String::Concat(string, string)
0x9a95  ldarg.0
0x9a96  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x9a9b  ldloc.0
0x9a9c  ldftn    instance void <>c__DisplayClass4_0::<UnlockMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x9aa2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x9aa7  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x9aac  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x9ab1  ret
```
