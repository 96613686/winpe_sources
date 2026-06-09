# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::KeepAlive

- ea: `0x7f10`
- end: `0x7fe9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::KeepAlive`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbaf0`

## callees

- `0x4e40`
- `0x7f10`
- `0xb0b0`

## string_xrefs

- `0x7f31`: `update MailboxBase WITH  (READPAST,READCOMMITTEDLOCK,UPDLOCK)\n					set\n						ModifiedOn = @modifiedOn\n					where \n							ProcessingStateCode = @lockedState\n							and HostId = @hostId`

## pseudocode

```c

```

## disassembly

```asm
0x7f10  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x7f15  stloc.0
0x7f16  ldloc.0
0x7f17  ldarg.0
0x7f18  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass7_0::<>4__this
0x7f1d  ldarg.0
0x7f1e  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7f23  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x7f28  brtrue.s loc_7F2B
0x7f2a  ret
0x7f2b  ldarg.0
0x7f2c  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x7f31  ldstr    aUpdateMailboxb// "update MailboxBase WITH  (READPAST,READ"...
0x7f36  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x7f3b  stloc.1
0x7f3c  ldloc.0
0x7f3d  ldloc.1
0x7f3e  ldc.i4.1
0x7f3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x7f44  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::keepAliveCommand
0x7f49  ldloc.0
0x7f4a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::keepAliveCommand
0x7f4f  ldstr    aLockedstate// "@lockedState"
0x7f54  ldc.i4.1
0x7f55  box      [mscorlib]System.Int32
0x7f5a  ldloca.s 2
0x7f5c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x7f62  ldloc.2
0x7f63  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x7f68  ldloc.0
0x7f69  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::keepAliveCommand
0x7f6e  ldstr    aHostid// "@hostId"
0x7f73  ldarg.0
0x7f74  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7f79  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x7f7e  ldc.i4   0x100
0x7f83  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x7f88  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x7f8d  ldloc.0
0x7f8e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass7_0::keepAliveCommand
0x7f93  ldstr    aModifiedon// "@modifiedOn"
0x7f98  ldarg.0
0x7f99  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x7f9e  box      [mscorlib]System.DateTime
0x7fa3  ldloca.s 2
0x7fa5  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x7fab  ldloc.2
0x7fac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x7fb1  ldarg.0
0x7fb2  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x7fb7  ldarg.0
0x7fb8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7fbd  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x7fc2  ldstr    aKeepalive// "_KeepAlive"
0x7fc7  call     string [mscorlib]System.String::Concat(string, string)
0x7fcc  ldarg.0
0x7fcd  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7fd2  ldloc.0
0x7fd3  ldftn    instance void <>c__DisplayClass7_0::<KeepAlive>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x7fd9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x7fde  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x7fe3  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x7fe8  ret
```
