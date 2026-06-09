# Microsoft.Crm.DeletionService::<ShrinkMailboxStatisticsTable>b__30_0

- ea: `0x1ea0`
- end: `0x2075`
- name: `Microsoft.Crm.DeletionService::<ShrinkMailboxStatisticsTable>b__30_0`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e0`
- `0x640`
- `0x1ea0`
- `0xaf40`
- `0xaf50`
- `0x86c40`
- `0x96cd0`

## string_xrefs

- `0x1f7f`: `@numOfRecordsToBeDeleted`
- `0x1ea8`: `DeletionService: Inside DeletionService.ShrinkMailboxStatisticsTable`
- `0x1ec8`: `DeletionService: Inside DeletionService.ShrinkMailboxStatisticsTable`
- `0x1f1f`: `DELETE TOP(@numOfRecordsToBeDeleted) MailboxStatisticsBase FROM MailboxStatisticsBase where MailboxProcessStartedOn < DATEADD(DAY,@numberofdays,GETUTCDATE())`
- `0x1fc1`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from MailboxStatisticsBase for MailboxProcessStartedOn older than {2}. Completed all Deletes : {3}`
- `0x2008`: `DeletionService: Execution of ShrinkMailboxStatisticsTable is completed.`
- `0x204b`: `DeletionService: Error cleaning up Mailbox Statistics Table`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.0
0x1ea1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1ea6  ldc.i4.s 0x14
0x1ea8  ldstr    aDeletionservic_47// "DeletionService: Inside DeletionService"...
0x1ead  ldc.i4.0
0x1eae  newarr   [mscorlib]System.Object
0x1eb3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1eb8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1ebd  ldarg.0
0x1ebe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1ec3  ldstr    aShrinkmailboxs// "ShrinkMailboxStatisticsTable"
0x1ec8  ldstr    aDeletionservic_47// "DeletionService: Inside DeletionService"...
0x1ecd  ldc.i4.0
0x1ece  ldc.i4.0
0x1ecf  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1ed4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1ed9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1ede  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1ee3  ldc.i4.0
0x1ee4  ldsfld   string [mscorlib]System.String::Empty
0x1ee9  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1eee  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1ef3  ldarg.0
0x1ef4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1ef9  ldarg.0
0x1efa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1eff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1f04  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1f09  ldstr    aMailboxstatist// "MailboxStatisticsPersistenceTimeInDays"
0x1f0e  ldc.i4.0
0x1f0f  box      [mscorlib]System.Int32
0x1f14  callvirt instance object Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string orgSetting, object defaultValue)
0x1f19  unbox.any [mscorlib]System.Int32
0x1f1e  stloc.0
0x1f1f  ldstr    aDeleteTopNumof_4// "DELETE TOP(@numOfRecordsToBeDeleted) Ma"...
0x1f24  stloc.1
0x1f25  ldarg.0
0x1f26  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1f2b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1f30  ldc.i4.0
0x1f31  ldc.i4.0
0x1f32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f37  stloc.2
0x1f38  ldloc.2
0x1f39  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f3e  ldloc.2
0x1f3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1f44  stloc.3
0x1f45  ldsfld   string [mscorlib]System.String::Empty
0x1f4a  stloc.s  4
0x1f4c  ldloc.2
0x1f4d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1f52  stloc.s  5
0x1f54  ldc.i4.m1
0x1f55  stloc.s  6
0x1f57  ldc.i4.0
0x1f58  stloc.s  7
0x1f5a  ldloc.s  5
0x1f5c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1f61  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1f66  dup
0x1f67  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1f6c  dup
0x1f6d  ldstr    aNumberofdays// "@numberofdays"
0x1f72  ldloc.0
0x1f73  neg
0x1f74  box      [mscorlib]System.Int32
0x1f79  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f7e  pop
0x1f7f  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x1f84  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1f89  box      [mscorlib]System.Int32
0x1f8e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f93  pop
0x1f94  ldloc.s  5
0x1f96  ldloc.1
0x1f97  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1f9c  ldloc.s  5
0x1f9e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fa3  stloc.s  4
0x1fa5  ldloc.3
0x1fa6  ldloc.s  5
0x1fa8  ldarg.0
0x1fa9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1fae  ldloca.s 6
0x1fb0  ldloca.s 7
0x1fb2  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x1fb7  stloc.s  8
0x1fb9  ldarg.0
0x1fba  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1fbf  ldc.i4.s 0x14
0x1fc1  ldstr    aDeletionservic_48// "DeletionService: Deletion Service delet"...
0x1fc6  ldc.i4.4
0x1fc7  newarr   [mscorlib]System.Object
0x1fcc  dup
0x1fcd  ldc.i4.0
0x1fce  ldloc.s  8
0x1fd0  box      [mscorlib]System.Int32
0x1fd5  stelem.ref
0x1fd6  dup
0x1fd7  ldc.i4.1
0x1fd8  ldloc.s  6
0x1fda  box      [mscorlib]System.Int32
0x1fdf  stelem.ref
0x1fe0  dup
0x1fe1  ldc.i4.2
0x1fe2  ldloc.0
0x1fe3  box      [mscorlib]System.Int32
0x1fe8  stelem.ref
0x1fe9  dup
0x1fea  ldc.i4.3
0x1feb  ldloc.s  7
0x1fed  box      [mscorlib]System.Boolean
0x1ff2  stelem.ref
0x1ff3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ff8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1ffd  ldarg.0
0x1ffe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2003  ldstr    aShrinkmailboxs// "ShrinkMailboxStatisticsTable"
0x2008  ldstr    aDeletionservic_49// "DeletionService: Execution of ShrinkMai"...
0x200d  ldloc.s  8
0x200f  ldloc.s  6
0x2011  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x2016  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x201b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x2020  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x2025  ldc.i4.1
0x2026  ldloc.s  5
0x2028  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x202d  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x2032  leave.s  loc_2040
0x2034  ldloc.s  5
0x2036  brfalse.s loc_203F
0x2038  ldloc.s  5
0x203a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x203f  endfinally
0x2040  leave.s  loc_2074
0x2042  stloc.s  9
0x2044  ldarg.0
0x2045  ldc.i4   0x80004003
0x204a  conv.u8
0x204b  ldstr    aDeletionservic_50// "DeletionService: Error cleaning up Mail"...
0x2050  ldloc.s  9
0x2052  callvirt instance string [mscorlib]System.Object::ToString()
0x2057  ldloc.s  4
0x2059  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x205e  rethrow
0x2060  ldloc.3
0x2061  brfalse.s loc_2069
0x2063  ldloc.3
0x2064  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2069  endfinally
0x206a  ldloc.2
0x206b  brfalse.s loc_2073
0x206d  ldloc.2
0x206e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2073  endfinally
0x2074  ret
```
