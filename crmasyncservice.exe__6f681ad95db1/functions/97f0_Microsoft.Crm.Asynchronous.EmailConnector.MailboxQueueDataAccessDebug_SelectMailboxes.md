# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::SelectMailboxes

- ea: `0x97f0`
- end: `0x99ab`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug::SelectMailboxes`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9ee0`
- `0xb950`

## string_xrefs

- `0x9804`: `UPDATE Mailboxbase WITH (READPAST, READCOMMITTEDLOCK, UPDLOCK)\n				SET \n					HostId = @hostId,\n					ModifiedOn = @dateTimeNow,\n					ProcessingLastAttemptedOn = @dateTimeNow,`

## pseudocode

```c

```

## disassembly

```asm
0x97f0  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x97f5  stloc.0
0x97f6  ldloc.0
0x97f7  ldarg.0
0x97f8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccessDebug <>c__DisplayClass3_0::<>4__this
0x97fd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9802  stloc.1
0x9803  ldloc.1
0x9804  ldstr    aUpdateMailboxb_1// "UPDATE Mailboxbase WITH (READPAST, READ"...
0x9809  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x980e  pop
0x980f  ldloc.1
0x9810  ldstr    aProcessingstat_0// "ProcessingStateCode = @lockedState,\r\n"...
0x9815  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x981a  pop
0x981b  ldloc.1
0x981c  ldstr    aWhereMailboxid_0// " WHERE \r\n\t\t\t\t\tMailboxId = @mailb"...
0x9821  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9826  pop
0x9827  ldloc.0
0x9828  ldarg.0
0x9829  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x982e  ldloc.1
0x982f  callvirt instance string [mscorlib]System.Object::ToString()
0x9834  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x9839  ldc.i4.1
0x983a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x983f  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x9844  ldloc.0
0x9845  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x984a  ldstr    aDatetimenow// "@dateTimeNow"
0x984f  ldarg.0
0x9850  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x9855  box      [mscorlib]System.DateTime
0x985a  ldloca.s 2
0x985c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9862  ldloc.2
0x9863  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9868  ldloc.0
0x9869  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x986e  ldstr    aLockedstate// "@lockedState"
0x9873  ldc.i4.1
0x9874  box      [mscorlib]System.Int32
0x9879  ldloca.s 2
0x987b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9881  ldloc.2
0x9882  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9887  ldloc.0
0x9888  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x988d  ldstr    aMaxdatetime// "@maxDateTime"
0x9892  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9897  box      [mscorlib]System.DateTime
0x989c  ldloca.s 2
0x989e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x98a4  ldloc.2
0x98a5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x98aa  ldloc.0
0x98ab  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x98b0  ldstr    aMailboxestosel// "@mailboxesToSelect"
0x98b5  ldarg.1
0x98b6  box      [mscorlib]System.Int32
0x98bb  ldloca.s 2
0x98bd  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x98c3  ldloc.2
0x98c4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x98c9  ldloc.0
0x98ca  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x98cf  ldstr    aWaitingstate// "@waitingState"
0x98d4  ldc.i4.0
0x98d5  box      [mscorlib]System.Int32
0x98da  ldloca.s 2
0x98dc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x98e2  ldloc.2
0x98e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x98e8  ldloc.0
0x98e9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x98ee  ldstr    aHostid// "@hostId"
0x98f3  ldarg.0
0x98f4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x98f9  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x98fe  ldstr    aDebugger// "Debugger"
0x9903  call     string [mscorlib]System.String::Concat(string, string)
0x9908  ldloca.s 2
0x990a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9910  ldloc.2
0x9911  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9916  ldloc.0
0x9917  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x991c  ldstr    aMailboxid_0// "@mailboxId"
0x9921  ldarg.0
0x9922  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9927  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_DebugContext()
0x992c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext::get_MailboxId()
0x9931  box      [mscorlib]System.Guid
0x9936  ldloca.s 2
0x9938  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x993e  ldloc.2
0x993f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9944  ldloc.0
0x9945  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass3_0::selectCommand
0x994a  ldstr    aInitialhostidv// "@initialHostIdValue"
0x994f  ldstr    aDebugger// "Debugger"
0x9954  ldloca.s 2
0x9956  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x995c  ldloc.2
0x995d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x9962  ldloc.0
0x9963  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper>::.ctor()
0x9968  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> <>c__DisplayClass3_0::mailboxes
0x996d  ldarg.0
0x996e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x9973  ldarg.0
0x9974  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x9979  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x997e  ldstr    aSelectevents// "_SelectEvents"
0x9983  call     string [mscorlib]System.String::Concat(string, string)
0x9988  ldarg.0
0x9989  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x998e  ldloc.0
0x998f  ldftn    instance void <>c__DisplayClass3_0::<SelectMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x9995  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x999a  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x999f  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x99a4  ldloc.0
0x99a5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> <>c__DisplayClass3_0::mailboxes
0x99aa  ret
```
