# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateMailboxStatisticsForOutgoingEmail

- ea: `0x742f0`
- end: `0x74596`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateMailboxStatisticsForOutgoingEmail`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x72750`

## callees

- `0x41210`
- `0x71c40`
- `0x71d60`
- `0x71d80`
- `0x71da0`
- `0x71dc0`
- `0x71de0`
- `0x742f0`
- `0x745a0`

## string_xrefs

- `0x7449a`: `@mailboxProcessScheduledOn`
- `0x744e4`: `@mailboxProcessCompletedOn`
- `0x7451a`: `@scheduledtimeintervalinminutes`
- `0x74340`: `INSERT INTO MailboxStatisticsBase (MailboxStatisticsId, AsyncEventId, OrganizationId, MailboxId, OperationTypeId, ItemsProcessed, ItemsFailed, ProcessResult, \n										MachineName, MailboxProcessScheduledOn, MailboxProcessStartedOn, MailboxProcessCompletedOn, CrmItemsBacklog, IndividualStepDurations, ScheduledTimeIntervalInMinutes, ProcessTimeIntervalInMinutes`
- `0x74358`: `VALUES (NEWID(), @asyncEventId, @organizationId, @mailboxId, @operationTypeId, @itemsProcessed, @itemsFailed, @processResult, \n										@machineName, @mailboxProcessScheduledOn, @mailboxProcessStartedOn, @mailboxProcessCompletedOn, @crmItemsBacklog, @individualStepDurations, @scheduledtimeintervalinminutes, @processtimeintervalinminutes`

## pseudocode

```c

```

## disassembly

```asm
0x742f0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x742f5  ldarg.0
0x742f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x742fb  ldarg.0
0x742fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74301  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x74306  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x7430b  ldstr    aMailboxstatist// "MailboxStatisticsPersistenceTimeInDays"
0x74310  ldc.i4.0
0x74311  box      [mscorlib]System.Int32
0x74316  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x7431b  unbox.any [mscorlib]System.Int32
0x74320  brtrue.s loc_74323
0x74322  ret
0x74323  ldarg.2
0x74324  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x74329  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToAra(valuetype [mscorlib]System.Guid organizationId)
0x7432e  brfalse  loc_74595
0x74333  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x74338  stloc.0
0x74339  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7433e  stloc.1
0x7433f  ldloc.1
0x74340  ldstr    aInsertIntoMail_0// "INSERT INTO MailboxStatisticsBase (Mail"...
0x74345  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7434a  pop
0x7434b  ldloc.1
0x7434c  ldstr    asc_B2A9C// ")"
0x74351  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x74356  pop
0x74357  ldloc.1
0x74358  ldstr    aValuesNewidAsy// "VALUES (NEWID(), @asyncEventId, @organi"...
0x7435d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x74362  pop
0x74363  ldloc.1
0x74364  ldstr    asc_B2A9C// ")"
0x74369  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7436e  pop
0x7436f  ldloc.0
0x74370  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x74375  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7437a  dup
0x7437b  ldstr    aAsynceventid_1// "@asyncEventId"
0x74380  ldarg.2
0x74381  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x74386  box      [mscorlib]System.Guid
0x7438b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74390  pop
0x74391  dup
0x74392  ldstr    aOrganizationid// "@organizationId"
0x74397  ldarg.2
0x74398  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x7439d  box      [mscorlib]System.Guid
0x743a2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x743a7  pop
0x743a8  dup
0x743a9  ldstr    aMailboxid_1// "@mailboxId"
0x743ae  ldarg.1
0x743af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x743b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x743b9  box      [mscorlib]System.Guid
0x743be  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x743c3  pop
0x743c4  dup
0x743c5  ldstr    aOperationtypei// "@operationTypeId"
0x743ca  ldc.i4.1
0x743cb  box      Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType
0x743d0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x743d5  pop
0x743d6  dup
0x743d7  ldstr    aItemsprocessed_2// "@itemsProcessed"
0x743dc  ldarg.1
0x743dd  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ItemsProcessedForOutgoingEmail()
0x743e2  box      [mscorlib]System.Int32
0x743e7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x743ec  pop
0x743ed  dup
0x743ee  ldstr    aItemsfailed// "@itemsFailed"
0x743f3  ldarg.1
0x743f4  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ItemsFailedForOutgoingEmail()
0x743f9  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x743fe  box      [mscorlib]System.Int32
0x74403  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74408  pop
0x74409  dup
0x7440a  ldstr    aProcessresult_0// "@processResult"
0x7440f  ldarg.1
0x74410  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ItemsFailedForOutgoingEmail()
0x74415  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x7441a  ldc.i4.0
0x7441b  bgt.s    loc_74420
0x7441d  ldc.i4.1
0x7441e  br.s     loc_74421
0x74420  ldc.i4.0
0x74421  box      [mscorlib]System.Int32
0x74426  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7442b  pop
0x7442c  dup
0x7442d  ldstr    aMachinename_1// "@machineName"
0x74432  call     string [mscorlib]System.Environment::get_MachineName()
0x74437  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7443c  pop
0x7443d  ldarg.1
0x7443e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessScheduledOn()
0x74443  ldloca.s 5
0x74445  initobj  [mscorlib]System.DateTime
0x7444b  ldloc.s  5
0x7444d  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x74452  brtrue.s loc_74464
0x74454  ldsfld   valuetype [System.Data]System.Data.SqlTypes.SqlDateTime [System.Data]System.Data.SqlTypes.SqlDateTime::MinValue
0x74459  stloc.s  6
0x7445b  ldloca.s 6
0x7445d  call     instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.SqlTypes.SqlDateTime::get_Value()
0x74462  br.s     loc_7446A
0x74464  ldarg.1
0x74465  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessScheduledOn()
0x7446a  stloc.2
0x7446b  ldarg.1
0x7446c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessingStarted()
0x74471  ldloca.s 5
0x74473  initobj  [mscorlib]System.DateTime
0x74479  ldloc.s  5
0x7447b  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x74480  brtrue.s loc_74492
0x74482  ldsfld   valuetype [System.Data]System.Data.SqlTypes.SqlDateTime [System.Data]System.Data.SqlTypes.SqlDateTime::MinValue
0x74487  stloc.s  6
0x74489  ldloca.s 6
0x7448b  call     instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.SqlTypes.SqlDateTime::get_Value()
0x74490  br.s     loc_74498
0x74492  ldarg.1
0x74493  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessingStarted()
0x74498  stloc.3
0x74499  dup
0x7449a  ldstr    aMailboxprocess// "@mailboxProcessScheduledOn"
0x7449f  ldloc.2
0x744a0  box      [mscorlib]System.DateTime
0x744a5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x744aa  pop
0x744ab  dup
0x744ac  ldstr    aMailboxprocess_0// "@mailboxProcessStartedOn"
0x744b1  ldloc.3
0x744b2  box      [mscorlib]System.DateTime
0x744b7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x744bc  pop
0x744bd  ldarg.1
0x744be  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessCompleted()
0x744c3  ldloca.s 5
0x744c5  initobj  [mscorlib]System.DateTime
0x744cb  ldloc.s  5
0x744cd  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x744d2  brtrue.s loc_744DB
0x744d4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x744d9  br.s     loc_744E1
0x744db  ldarg.1
0x744dc  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessCompleted()
0x744e1  stloc.s  4
0x744e3  dup
0x744e4  ldstr    aMailboxprocess_1// "@mailboxProcessCompletedOn"
0x744e9  ldloc.s  4
0x744eb  box      [mscorlib]System.DateTime
0x744f0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x744f5  pop
0x744f6  dup
0x744f7  ldstr    aCrmitemsbacklo_0// "@crmItemsBacklog"
0x744fc  ldc.i4.0
0x744fd  box      [mscorlib]System.Int32
0x74502  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74507  pop
0x74508  dup
0x74509  ldstr    aIndividualstep_0// "@individualStepDurations"
0x7450e  ldsfld   string [mscorlib]System.String::Empty
0x74513  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74518  pop
0x74519  dup
0x7451a  ldstr    aScheduledtimei_1// "@scheduledtimeintervalinminutes"
0x7451f  ldarg.0
0x74520  ldloc.2
0x74521  ldloc.3
0x74522  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::PreventOverflowingCheck(valuetype [mscorlib]System.DateTime duration, valuetype [mscorlib]System.DateTime baseDuration)
0x74527  box      [mscorlib]System.Int32
0x7452c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74531  pop
0x74532  ldstr    aProcesstimeint// "@processtimeintervalinminutes"
0x74537  ldarg.0
0x74538  ldloc.3
0x74539  ldloc.s  4
0x7453b  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::PreventOverflowingCheck(valuetype [mscorlib]System.DateTime duration, valuetype [mscorlib]System.DateTime baseDuration)
0x74540  box      [mscorlib]System.Int32
0x74545  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7454a  pop
0x7454b  ldloc.0
0x7454c  ldloc.1
0x7454d  callvirt instance string [mscorlib]System.Object::ToString()
0x74552  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x74557  ldarg.0
0x74558  ldloc.0
0x74559  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x7455e  pop
0x7455f  leave.s  loc_7456B
0x74561  ldloc.0
0x74562  brfalse.s loc_7456A
0x74564  ldloc.0
0x74565  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7456a  endfinally
0x7456b  leave.s  loc_74595
0x7456d  stloc.s  7
0x7456f  ldloc.s  7
0x74571  ldarg.0
0x74572  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74577  ldc.i4.s 0x3D
0x74579  ldstr    aExceptionEncou_6// "Exception encountered while updating Ou"...
0x7457e  ldc.i4.1
0x7457f  newarr   [mscorlib]System.Object
0x74584  dup
0x74585  ldc.i4.0
0x74586  ldloc.s  7
0x74588  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x7458d  stelem.ref
0x7458e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74593  leave.s  loc_74595
0x74595  ret
```
