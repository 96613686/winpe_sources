# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::TimeoutLocked

- ea: `0x7ff0`
- end: `0x81d7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::TimeoutLocked`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x82e0`
- `0xbb00`

## callees

- `0x4da0`
- `0x4e40`
- `0x7ff0`
- `0x9ec0`
- `0xb100`

## string_xrefs

- `0x802e`: `update MailboxBase  WITH  (READPAST,READCOMMITTEDLOCK,UPDLOCK)\n									set\n										ProcessingStateCode = @waitingState,\n										HostId = NULL,\n										ModifiedOn = @utcNow,\n										PostponeMailboxProcessingUntil = @utcNow`
- `0x8067`: `ProcessingLastAttemptedOn < @maximumPermissibleIdleTime and HostId = @hostId`
- `0x80c3`: `ProcessingLastAttemptedOn < @maximumPermissibleIdleTime`

## pseudocode

```c

```

## disassembly

```asm
0x7ff0  ldarg.0
0x7ff1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7ff6  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x7ffb  brtrue.s loc_7FFE
0x7ffd  ret
0x7ffe  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8003  stloc.0
0x8004  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x8009  stloc.1
0x800a  ldloc.1
0x800b  ldarg.0
0x800c  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass8_0::<>4__this
0x8011  ldloc.1
0x8012  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x8017  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::timeoutLockedCommand
0x801c  ldloc.1
0x801d  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::timeoutLockedCommand
0x8022  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8027  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x802c  stloc.2
0x802d  ldloc.0
0x802e  ldstr    aUpdateMailboxb_0// "update MailboxBase  WITH  (READPAST,REA"...
0x8033  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8038  pop
0x8039  ldarga.s 1
0x803b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x8040  brfalse.s loc_80A9
0x8042  ldloc.0
0x8043  ldstr    aLastmailboxfor// ",LastMailboxForcedUnlockOccurredOn = @u"...
0x8048  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x804d  pop
0x804e  ldloc.0
0x804f  ldstr    aForcedunlockco// ",ForcedUnlockCount = ForcedUnlockCount "...
0x8054  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8059  pop
0x805a  ldloc.0
0x805b  ldstr    aWhereProcessin// " where ProcessingStateCode = @lockedSta"...
0x8060  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8065  pop
0x8066  ldloc.0
0x8067  ldstr    aProcessinglast// "ProcessingLastAttemptedOn < @maximumPer"...
0x806c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8071  pop
0x8072  ldloc.2
0x8073  ldstr    aMaximumpermiss// "@maximumPermissibleIdleTime"
0x8078  ldarg.1
0x8079  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x807e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8083  pop
0x8084  ldloc.2
0x8085  ldstr    aHostid// "@hostId"
0x808a  ldarg.0
0x808b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8090  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x8095  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x809a  ldc.i4   0x100
0x809f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x80a4  br       loc_8132
0x80a9  ldloc.0
0x80aa  ldstr    aWhereProcessin// " where ProcessingStateCode = @lockedSta"...
0x80af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x80b4  pop
0x80b5  ldarg.0
0x80b6  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x80bb  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxForcedUnlockingEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x80c0  brfalse.s loc_80FB
0x80c2  ldloc.0
0x80c3  ldstr    aProcessinglast_0// "ProcessingLastAttemptedOn < @maximumPer"...
0x80c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x80cd  pop
0x80ce  ldloc.2
0x80cf  ldstr    aMaximumpermiss// "@maximumPermissibleIdleTime"
0x80d4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x80d9  ldarg.0
0x80da  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x80df  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x80e4  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxProcessingInterval()
0x80e9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x80ee  box      [mscorlib]System.DateTime
0x80f3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x80f8  pop
0x80f9  br.s     loc_8132
0x80fb  ldloc.0
0x80fc  ldstr    aModifiedonMaxi// "ModifiedOn < @maximumPermissibleIdleTim"...
0x8101  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8106  pop
0x8107  ldloc.2
0x8108  ldstr    aMaximumpermiss// "@maximumPermissibleIdleTime"
0x810d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8112  ldarg.0
0x8113  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8118  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x811d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxRetryInterval()
0x8122  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x8127  box      [mscorlib]System.DateTime
0x812c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8131  pop
0x8132  ldloc.2
0x8133  ldstr    aWaitingstate// "@waitingState"
0x8138  ldc.i4.0
0x8139  box      [mscorlib]System.Int32
0x813e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8143  pop
0x8144  ldloc.2
0x8145  ldstr    aLockedstate// "@lockedState"
0x814a  ldc.i4.1
0x814b  box      [mscorlib]System.Int32
0x8150  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8155  pop
0x8156  ldloc.2
0x8157  ldstr    aUtcnow// "@utcNow"
0x815c  ldarg.0
0x815d  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x8162  box      [mscorlib]System.DateTime
0x8167  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x816c  pop
0x816d  ldloc.1
0x816e  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::timeoutLockedCommand
0x8173  ldarg.0
0x8174  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_mailboxQueueAppLock
0x8179  ldloc.0
0x817a  callvirt instance string [mscorlib]System.Object::ToString()
0x817f  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock(string, string)
0x8184  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8189  ldarg.0
0x818a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x818f  ldarg.0
0x8190  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8195  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x819a  ldstr    aTimeout_0// "_TimeOut"
0x819f  call     string [mscorlib]System.String::Concat(string, string)
0x81a4  ldarg.0
0x81a5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x81aa  ldloc.1
0x81ab  ldftn    instance void <>c__DisplayClass8_0::<TimeoutLocked>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x81b1  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x81b6  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x81bb  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x81c0  leave.s  loc_81D6
0x81c2  ldloc.1
0x81c3  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::timeoutLockedCommand
0x81c8  brfalse.s loc_81D5
0x81ca  ldloc.1
0x81cb  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::timeoutLockedCommand
0x81d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x81d5  endfinally
0x81d6  ret
```
