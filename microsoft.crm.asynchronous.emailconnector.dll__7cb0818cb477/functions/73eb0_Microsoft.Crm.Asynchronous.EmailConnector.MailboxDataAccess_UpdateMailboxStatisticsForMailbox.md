# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateMailboxStatisticsForMailbox

- ea: `0x73eb0`
- end: `0x742e3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateMailboxStatisticsForMailbox`
- size: `1075`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x73a40`
- `0x73bc0`
- `0x76f60`
- `0x77560`

## callees

- `0x411e0`
- `0x41210`
- `0x71c20`
- `0x71cf0`
- `0x71d00`
- `0x71e10`
- `0x71e30`
- `0x71e50`
- `0x71e90`
- `0x71ea0`
- `0x71ec0`
- `0x71f00`
- `0x71f20`
- `0x73eb0`
- `0x745a0`

## string_xrefs

- `0x741f5`: `lastsuccessfulsynccompletedon`
- `0x74209`: `lastsuccessfulsynccompletedon`
- `0x73fac`: `INSERT INTO MailboxStatisticsBase (MailboxStatisticsId, OrganizationId, MailboxId, OperationTypeId, ItemsProcessed, ItemsFailed, ProcessResult, \n										MachineName, MailboxProcessScheduledOn, MailboxProcessStartedOn, MailboxProcessCompletedOn, CrmItemsBacklog, IndividualStepDurations `
- `0x73fca`: `,ScheduledTimeIntervalInMinutes, ProcessTimeIntervalInMinutes`
- `0x73fff`: `VALUES (@mailboxStatisticsId, @organizationId, @mailboxId, @operationTypeId, @itemsProcessed, @itemsFailed, @processResult, \n										@machineName, @mailboxProcessScheduledOn, @mailboxProcessStartedOn, @mailboxProcessCompletedOn, @crmItemsBacklog, @individualStepDurations `
- `0x74010`: `,@scheduledtimeintervalinminutes, @processtimeintervalinminutes`
- `0x74048`: `@mailboxStatisticsId`
- `0x74131`: `@mailboxProcessScheduledOn`
- `0x7421c`: `@mailboxProcessCompletedOn`
- `0x74249`: `@scheduledtimeintervalinminutes`
- `0x742c6`: `Exception encountered while updating Incoming email and ACT information in MailboxStatistics table: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x73eb0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x73eb5  ldarg.0
0x73eb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73ebb  ldarg.0
0x73ebc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73ec1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x73ec6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x73ecb  ldstr    aMailboxstatist// "MailboxStatisticsPersistenceTimeInDays"
0x73ed0  ldc.i4.0
0x73ed1  box      [mscorlib]System.Int32
0x73ed6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x73edb  unbox.any [mscorlib]System.Int32
0x73ee0  brtrue.s loc_73EE7
0x73ee2  leave    loc_742E2
0x73ee7  ldarg.0
0x73ee8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73eed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x73ef2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73ef7  ldc.i4   0x2587
0x73efc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x73f01  brtrue.s loc_73F08
0x73f03  leave    loc_742E2
0x73f08  ldarg.1
0x73f09  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x73f0e  stloc.0
0x73f0f  ldc.i4.1
0x73f10  ldloc.0
0x73f11  beq.s    loc_73F19
0x73f13  ldc.i4.2
0x73f14  ldloc.0
0x73f15  ceq
0x73f17  br.s     loc_73F1A
0x73f19  ldc.i4.1
0x73f1a  stloc.1
0x73f1b  ldarg.2
0x73f1c  ldc.i4.2
0x73f1d  beq.s    loc_73F2D
0x73f1f  ldarg.1
0x73f20  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_MailboxProcessingScheduledOnForEC()
0x73f25  ldc.i4.1
0x73f26  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x73f2b  br.s     loc_73F39
0x73f2d  ldarg.1
0x73f2e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_MailboxProcessingScheduledOnForACT()
0x73f33  ldc.i4.1
0x73f34  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x73f39  stloc.2
0x73f3a  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x73f3f  stloc.3
0x73f40  ldarg.2
0x73f41  ldc.i4.2
0x73f42  bne.un.s loc_73F53
0x73f44  ldarg.1
0x73f45  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForACT()
0x73f4a  ldc.i4.1
0x73f4b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x73f50  stloc.3
0x73f51  br.s     loc_73F73
0x73f53  ldarg.2
0x73f54  ldc.i4.4
0x73f55  bne.un.s loc_73F66
0x73f57  ldarg.1
0x73f58  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForManualEC()
0x73f5d  ldc.i4.1
0x73f5e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x73f63  stloc.3
0x73f64  br.s     loc_73F73
0x73f66  ldarg.1
0x73f67  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForEC()
0x73f6c  ldc.i4.1
0x73f6d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x73f72  stloc.3
0x73f73  ldarg.2
0x73f74  brfalse.s loc_73F7A
0x73f76  ldarg.2
0x73f77  ldc.i4.4
0x73f78  bne.un.s loc_73F9C
0x73f7a  ldarg.1
0x73f7b  ldstr    aIndividualstep// "individualstepdurations"
0x73f80  ldarg.1
0x73f81  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_IndividualStepDuration()
0x73f86  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_Item(string attributeName, object value)
0x73f8b  ldarg.1
0x73f8c  ldstr    aCrmitemsbacklo// "crmitemsbacklog"
0x73f91  ldc.i4.0
0x73f92  box      [mscorlib]System.Int32
0x73f97  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_Item(string attributeName, object value)
0x73f9c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x73fa1  stloc.s  4
0x73fa3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x73fa8  stloc.s  5
0x73faa  ldloc.s  5
0x73fac  ldstr    aInsertIntoMail// "INSERT INTO MailboxStatisticsBase (Mail"...
0x73fb1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73fb6  pop
0x73fb7  ldarg.0
0x73fb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73fbd  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToCarina(valuetype [mscorlib]System.Guid organizationId)
0x73fc2  stloc.s  6
0x73fc4  ldloc.s  6
0x73fc6  brfalse.s loc_73FD5
0x73fc8  ldloc.s  5
0x73fca  ldstr    aScheduledtimei// ",ScheduledTimeIntervalInMinutes, Proces"...
0x73fcf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73fd4  pop
0x73fd5  ldarg.0
0x73fd6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73fdb  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToAra(valuetype [mscorlib]System.Guid organizationId)
0x73fe0  dup
0x73fe1  brfalse.s loc_73FF0
0x73fe3  ldloc.s  5
0x73fe5  ldstr    aAsynceventid// ",AsyncEventId"
0x73fea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73fef  pop
0x73ff0  ldloc.s  5
0x73ff2  ldstr    asc_B2A9C// ")"
0x73ff7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73ffc  pop
0x73ffd  ldloc.s  5
0x73fff  ldstr    aValuesMailboxs// "VALUES (@mailboxStatisticsId, @organiza"...
0x74004  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x74009  pop
0x7400a  ldloc.s  6
0x7400c  brfalse.s loc_7401B
0x7400e  ldloc.s  5
0x74010  ldstr    aScheduledtimei_0// ",@scheduledtimeintervalinminutes, @proc"...
0x74015  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7401a  pop
0x7401b  dup
0x7401c  brfalse.s loc_7402B
0x7401e  ldloc.s  5
0x74020  ldstr    aAsynceventid_0// ",@asyncEventId"
0x74025  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7402a  pop
0x7402b  ldloc.s  5
0x7402d  ldstr    asc_B2A9C// ")"
0x74032  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x74037  pop
0x74038  ldloc.s  4
0x7403a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7403f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x74044  stloc.s  7
0x74046  ldloc.s  7
0x74048  ldstr    aMailboxstatist_0// "@mailboxStatisticsId"
0x7404d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x74052  box      [mscorlib]System.Guid
0x74057  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7405c  pop
0x7405d  ldloc.s  7
0x7405f  ldstr    aOrganizationid// "@organizationId"
0x74064  ldarg.1
0x74065  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x7406a  box      [mscorlib]System.Guid
0x7406f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74074  pop
0x74075  ldloc.s  7
0x74077  ldstr    aMailboxid_1// "@mailboxId"
0x7407c  ldarg.1
0x7407d  ldstr    aMailboxid// "mailboxid"
0x74082  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x74087  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7408c  pop
0x7408d  ldloc.s  7
0x7408f  ldstr    aOperationtypei// "@operationTypeId"
0x74094  ldarg.2
0x74095  box      Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType
0x7409a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7409f  pop
0x740a0  ldloc.s  7
0x740a2  ldstr    aItemsprocessed_2// "@itemsProcessed"
0x740a7  ldarg.1
0x740a8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x740ad  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x740b2  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x740b7  brtrue.s loc_740C1
0x740b9  ldc.i4.0
0x740ba  box      [mscorlib]System.Int32
0x740bf  br.s     loc_740CC
0x740c1  ldarg.1
0x740c2  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x740c7  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x740cc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x740d1  pop
0x740d2  ldloc.s  7
0x740d4  ldstr    aItemsfailed// "@itemsFailed"
0x740d9  ldarg.1
0x740da  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x740df  ldstr    aItemsfailedfor// "itemsfailedforlastsync"
0x740e4  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x740e9  brtrue.s loc_740F3
0x740eb  ldc.i4.0
0x740ec  box      [mscorlib]System.Int32
0x740f1  br.s     loc_740FE
0x740f3  ldarg.1
0x740f4  ldstr    aItemsfailedfor// "itemsfailedforlastsync"
0x740f9  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x740fe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74103  pop
0x74104  ldloc.s  7
0x74106  ldstr    aProcessresult_0// "@processResult"
0x7410b  ldloc.1
0x7410c  brtrue.s loc_74111
0x7410e  ldc.i4.1
0x7410f  br.s     loc_74112
0x74111  ldc.i4.0
0x74112  box      [mscorlib]System.Int32
0x74117  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7411c  pop
0x7411d  ldloc.s  7
0x7411f  ldstr    aMachinename_1// "@machineName"
0x74124  call     string [mscorlib]System.Environment::get_MachineName()
0x74129  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7412e  pop
0x7412f  ldloc.s  7
0x74131  ldstr    aMailboxprocess// "@mailboxProcessScheduledOn"
0x74136  ldloc.2
0x74137  box      [mscorlib]System.DateTime
0x7413c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74141  pop
0x74142  ldloc.s  7
0x74144  ldstr    aMailboxprocess_0// "@mailboxProcessStartedOn"
0x74149  ldloc.3
0x7414a  box      [mscorlib]System.DateTime
0x7414f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74154  pop
0x74155  ldloc.s  7
0x74157  ldstr    aCrmitemsbacklo_0// "@crmItemsBacklog"
0x7415c  ldarg.1
0x7415d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x74162  ldstr    aCrmitemsbacklo// "crmitemsbacklog"
0x74167  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x7416c  brtrue.s loc_74176
0x7416e  ldc.i4.0
0x7416f  box      [mscorlib]System.Int32
0x74174  br.s     loc_74181
0x74176  ldarg.1
0x74177  ldstr    aCrmitemsbacklo// "crmitemsbacklog"
0x7417c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x74181  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74186  pop
0x74187  ldloc.s  7
0x74189  ldstr    aIndividualstep_0// "@individualStepDurations"
0x7418e  ldarg.1
0x7418f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x74194  ldstr    aIndividualstep// "individualstepdurations"
0x74199  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x7419e  brtrue.s loc_741A7
0x741a0  ldsfld   string [mscorlib]System.String::Empty
0x741a5  br.s     loc_741B2
0x741a7  ldarg.1
0x741a8  ldstr    aIndividualstep// "individualstepdurations"
0x741ad  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x741b2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x741b7  pop
0x741b8  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MinValue()
0x741bd  stloc.s  8
0x741bf  ldloc.1
0x741c0  brfalse.s loc_741EF
0x741c2  ldarg.1
0x741c3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x741c8  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x741cd  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x741d2  brtrue.s loc_741DB
0x741d4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x741d9  br.s     loc_741EB
0x741db  ldarg.1
0x741dc  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x741e1  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x741e6  unbox.any [mscorlib]System.DateTime
0x741eb  stloc.s  8
0x741ed  br.s     loc_7421A
0x741ef  ldarg.1
0x741f0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x741f5  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x741fa  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x741ff  brtrue.s loc_74208
0x74201  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x74206  br.s     loc_74218
0x74208  ldarg.1
0x74209  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x7420e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x74213  unbox.any [mscorlib]System.DateTime
0x74218  stloc.s  8
0x7421a  ldloc.s  7
0x7421c  ldstr    aMailboxprocess_1// "@mailboxProcessCompletedOn"
0x74221  ldloc.s  8
0x74223  box      [mscorlib]System.DateTime
0x74228  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7422d  pop
0x7422e  ldloc.s  6
0x74230  brfalse.s loc_7426F
0x74232  ldarg.0
0x74233  ldloc.2
0x74234  ldloc.3
0x74235  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::PreventOverflowingCheck(valuetype [mscorlib]System.DateTime duration, valuetype [mscorlib]System.DateTime baseDuration)
0x7423a  stloc.s  9
0x7423c  ldarg.0
0x7423d  ldloc.3
0x7423e  ldloc.s  8
0x74240  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::PreventOverflowingCheck(valuetype [mscorlib]System.DateTime duration, valuetype [mscorlib]System.DateTime baseDuration)
  ... truncated ...
```
