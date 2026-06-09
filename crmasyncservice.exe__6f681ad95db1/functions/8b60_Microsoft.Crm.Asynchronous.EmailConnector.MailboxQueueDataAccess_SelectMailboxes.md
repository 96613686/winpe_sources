# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SelectMailboxes

- ea: `0x8b60`
- end: `0x8da4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SelectMailboxes`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x7e40`

## callees

- `0x8b60`
- `0xb7d0`

## string_xrefs

- `0x8b74`: `UPDATE Mailboxbase WITH (READPAST, READCOMMITTEDLOCK, UPDLOCK)\n				SET \n					HostId = @hostId,\n					ModifiedOn = @dateTimeNow,\n					ProcessingLastAttemptedOn = @dateTimeNow,`
- `0x8b80`: `ProcessingStateCode = @lockedState,\n					PostponeMailboxProcessingUntil = @maxDateTime\n				OUTPUT\n					INSERTED.MailboxId,\n					INSERTED.CreatedOn,\n					INSERTED.ModifiedOn,\n					INSERTED.ReceivingPostponedUntil,\n					INSERTED.NoEmailCount,\n					INSERTED.ProcessEmailReceivedAfter,\n					INSERTED.IsForwardMailbox,\n					INSERTED.EmailAddress,\n					INSERTED.ProcessAndDeleteEmails,\n					INSERTED.LastMessageId,\n					INSERTED.TestEmailConfigurationScheduled,\n					INSERTED.Po`
- `0x8bd6`: `,INSERTED.VerboseLoggingEnabled, INSERTED.IsServiceAccount`
- `0x8be2`: `,INSERTED.OfficeAppsDeploymentScheduled, INSERTED.OfficeAppsDeploymentStatus`
- `0x8bfc`: `,INSERTED.IncomingEmailStatus`
- `0x8c20`: `,INSERTED.ProcessingLastAttemptedOn`
- `0x8c50`: `,INSERTED.IsExchangeContactsImportScheduled`
- `0x8c6a`: ` WHERE \n					MailboxId \n					IN \n					(SELECT \n						TOP (@mailboxesToSelect) MailboxId \n					FROM \n						MailboxBase WITH (READPAST, READCOMMITTEDLOCK, UPDLOCK) \n					WHERE\n						( \n							ProcessingStateCode = @waitingState\n							AND\n							PostponeMailboxProcessingUntil <= @dateTimeNow\n						)\n					ORDER BY \n						PostponeMailboxProcessingUntil\n					)`

## pseudocode

```c

```

## disassembly

```asm
0x8b60  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x8b65  stloc.0
0x8b66  ldloc.0
0x8b67  ldarg.0
0x8b68  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass15_0::<>4__this
0x8b6d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8b72  stloc.1
0x8b73  ldloc.1
0x8b74  ldstr    aUpdateMailboxb_1// "UPDATE Mailboxbase WITH (READPAST, READ"...
0x8b79  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8b7e  pop
0x8b7f  ldloc.1
0x8b80  ldstr    aProcessingstat// "ProcessingStateCode = @lockedState,\r\n"...
0x8b85  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8b8a  pop
0x8b8b  ldarg.0
0x8b8c  ldarg.0
0x8b8d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8b92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8b97  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::CarinaVersion
0x8b9c  call     instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::CheckHasNewColumnsAdded(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8ba1  brfalse.s loc_8BB1
0x8ba3  ldloc.1
0x8ba4  ldstr    aInsertedFolder// ",INSERTED.FolderHierarchy"
0x8ba9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8bae  pop
0x8baf  br.s     loc_8BBD
0x8bb1  ldloc.1
0x8bb2  ldstr    a0_0// ",0"
0x8bb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8bbc  pop
0x8bbd  ldarg.0
0x8bbe  ldarg.0
0x8bbf  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8bc4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8bc9  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::AraVersion
0x8bce  call     instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::CheckHasNewColumnsAdded(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8bd3  brfalse.s loc_8BEF
0x8bd5  ldloc.1
0x8bd6  ldstr    aInsertedVerbos// ",INSERTED.VerboseLoggingEnabled, INSERT"...
0x8bdb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8be0  pop
0x8be1  ldloc.1
0x8be2  ldstr    aInsertedOffice// ",INSERTED.OfficeAppsDeploymentScheduled"...
0x8be7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8bec  pop
0x8bed  br.s     loc_8BFB
0x8bef  ldloc.1
0x8bf0  ldstr    a0000// ", 0, 0, 0, 0"
0x8bf5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8bfa  pop
0x8bfb  ldloc.1
0x8bfc  ldstr    aInsertedIncomi// ",INSERTED.IncomingEmailStatus"
0x8c01  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c06  pop
0x8c07  ldloc.1
0x8c08  ldstr    aInsertedOutgoi// ",INSERTED.OutgoingEmailStatus"
0x8c0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c12  pop
0x8c13  ldloc.1
0x8c14  ldstr    aInsertedActsta// ",INSERTED.ACTStatus"
0x8c19  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c1e  pop
0x8c1f  ldloc.1
0x8c20  ldstr    aInsertedProces// ",INSERTED.ProcessingLastAttemptedOn"
0x8c25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c2a  pop
0x8c2b  ldloc.1
0x8c2c  ldstr    aInsertedEmails// ",INSERTED.EmailServerProfile"
0x8c31  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c36  pop
0x8c37  ldarg.0
0x8c38  ldarg.0
0x8c39  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8c3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8c43  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::PotassiumVersion
0x8c48  call     instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::CheckHasNewColumnsAdded(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8c4d  brfalse.s loc_8C5D
0x8c4f  ldloc.1
0x8c50  ldstr    aInsertedIsexch// ",INSERTED.IsExchangeContactsImportSched"...
0x8c55  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c5a  pop
0x8c5b  br.s     loc_8C69
0x8c5d  ldloc.1
0x8c5e  ldstr    a0_0// ",0"
0x8c63  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c68  pop
0x8c69  ldloc.1
0x8c6a  ldstr    aWhereMailboxid// " WHERE \r\n\t\t\t\t\tMailboxId \r\n\t\t"...
0x8c6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8c74  pop
0x8c75  ldloc.0
0x8c76  ldarg.0
0x8c77  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x8c7c  ldloc.1
0x8c7d  callvirt instance string [mscorlib]System.Object::ToString()
0x8c82  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x8c87  ldc.i4.1
0x8c88  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x8c8d  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8c92  ldloc.0
0x8c93  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8c98  ldstr    aHostid// "@hostId"
0x8c9d  ldarg.0
0x8c9e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8ca3  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x8ca8  ldc.i4   0x100
0x8cad  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8cb2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8cb7  ldloc.0
0x8cb8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8cbd  ldstr    aDatetimenow// "@dateTimeNow"
0x8cc2  ldarg.0
0x8cc3  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x8cc8  box      [mscorlib]System.DateTime
0x8ccd  ldloca.s 2
0x8ccf  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8cd5  ldloc.2
0x8cd6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8cdb  ldloc.0
0x8cdc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8ce1  ldstr    aLockedstate// "@lockedState"
0x8ce6  ldc.i4.1
0x8ce7  box      [mscorlib]System.Int32
0x8cec  ldloca.s 2
0x8cee  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8cf4  ldloc.2
0x8cf5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8cfa  ldloc.0
0x8cfb  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8d00  ldstr    aMaxdatetime// "@maxDateTime"
0x8d05  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x8d0a  box      [mscorlib]System.DateTime
0x8d0f  ldloca.s 2
0x8d11  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8d17  ldloc.2
0x8d18  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8d1d  ldloc.0
0x8d1e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8d23  ldstr    aMailboxestosel// "@mailboxesToSelect"
0x8d28  ldarg.1
0x8d29  box      [mscorlib]System.Int32
0x8d2e  ldloca.s 2
0x8d30  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8d36  ldloc.2
0x8d37  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8d3c  ldloc.0
0x8d3d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass15_0::updateCommand
0x8d42  ldstr    aWaitingstate// "@waitingState"
0x8d47  ldc.i4.0
0x8d48  box      [mscorlib]System.Int32
0x8d4d  ldloca.s 2
0x8d4f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8d55  ldloc.2
0x8d56  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8d5b  ldloc.0
0x8d5c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper>::.ctor()
0x8d61  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> <>c__DisplayClass15_0::mailBoxEntityWrappers
0x8d66  ldarg.0
0x8d67  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x8d6c  ldarg.0
0x8d6d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8d72  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x8d77  ldstr    aSelectevents// "_SelectEvents"
0x8d7c  call     string [mscorlib]System.String::Concat(string, string)
0x8d81  ldarg.0
0x8d82  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8d87  ldloc.0
0x8d88  ldftn    instance void <>c__DisplayClass15_0::<SelectMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x8d8e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x8d93  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x8d98  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x8d9d  ldloc.0
0x8d9e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> <>c__DisplayClass15_0::mailBoxEntityWrappers
0x8da3  ret
```
