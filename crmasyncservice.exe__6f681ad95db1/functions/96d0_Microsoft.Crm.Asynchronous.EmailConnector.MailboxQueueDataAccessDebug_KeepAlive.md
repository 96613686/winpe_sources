# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::KeepAlive

- ea: `0x96d0`
- end: `0x97d2`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::KeepAlive`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9ee0`
- `0xb8f0`

## string_xrefs

- `0x96e3`: `update MailboxBase WITH  (READPAST,READCOMMITTEDLOCK,UPDLOCK)\n								set\n									ModifiedOn = @modifiedOn\n								where \n									HostId = @hostId and MailboxId = @mailboxId`

## pseudocode

```c

```

## disassembly

```asm
0x96d0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x96d5  stloc.0
0x96d6  ldloc.0
0x96d7  ldarg.0
0x96d8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug <>c__DisplayClass1_0::<>4__this
0x96dd  ldarg.0
0x96de  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x96e3  ldstr    aUpdateMailboxb_3// "update MailboxBase WITH  (READPAST,READ"...
0x96e8  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x96ed  stloc.1
0x96ee  ldloc.0
0x96ef  ldloc.1
0x96f0  ldc.i4.1
0x96f1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x96f6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass1_0::keepAliveCommand
0x96fb  ldloc.0
0x96fc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass1_0::keepAliveCommand
0x9701  ldstr    aLockedstate// "@lockedState"
0x9706  ldc.i4.1
0x9707  box      [mscorlib]System.Int32
0x970c  ldloca.s 2
0x970e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9714  ldloc.2
0x9715  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x971a  ldloc.0
0x971b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass1_0::keepAliveCommand
0x9720  ldstr    aModifiedon// "@modifiedOn"
0x9725  ldarg.0
0x9726  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x972b  box      [mscorlib]System.DateTime
0x9730  ldloca.s 2
0x9732  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9738  ldloc.2
0x9739  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x973e  ldloc.0
0x973f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass1_0::keepAliveCommand
0x9744  ldstr    aHostid// "@hostId"
0x9749  ldarg.0
0x974a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x974f  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9754  ldstr    aDebugger// "Debugger"
0x9759  call     string [mscorlib]System.String::Concat(string, string)
0x975e  ldloca.s 2
0x9760  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9766  ldloc.2
0x9767  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x976c  ldloc.0
0x976d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass1_0::keepAliveCommand
0x9772  ldstr    aMailboxid_0// "@mailboxId"
0x9777  ldarg.0
0x9778  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x977d  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_DebugContext()
0x9782  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext::get_MailboxId()
0x9787  box      [mscorlib]System.Guid
0x978c  ldloca.s 2
0x978e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9794  ldloc.2
0x9795  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x979a  ldarg.0
0x979b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x97a0  ldarg.0
0x97a1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x97a6  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x97ab  ldstr    aKeepalive// "_KeepAlive"
0x97b0  call     string [mscorlib]System.String::Concat(string, string)
0x97b5  ldarg.0
0x97b6  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x97bb  ldloc.0
0x97bc  ldftn    instance void <>c__DisplayClass1_0::<KeepAlive>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x97c2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x97c7  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x97cc  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x97d1  ret
```
