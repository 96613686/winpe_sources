# Microsoft.Crm.DeletionService::<ShrinkTraceLogTable>b__31_0

- ea: `0x2080`
- end: `0x2249`
- name: `Microsoft.Crm.DeletionService::<ShrinkTraceLogTable>b__31_0`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e0`
- `0x640`
- `0x2080`
- `0xaf40`
- `0xaf50`
- `0x86c40`
- `0x96cd0`

## string_xrefs

- `0x2088`: `DeletionService: Inside DeletionService.ShrinkTraceLogTable`
- `0x20a8`: `DeletionService: Inside DeletionService.ShrinkTraceLogTable`
- `0x2100`: `DELETE from TraceAssociationBase where RegardingObjectTypeCode = @mailboxTypeCode \n	and TraceLogId in (select TraceLogId from TraceLogBase where CreatedOn < DATEADD(DAY,@numberofdays,GETUTCDATE()) and CanBeDeleted = 1); \nDELETE from TraceLogBase where CreatedOn < DATEADD(DAY,@numberofdays,GETUTCDATE()) and CanBeDeleted = 1`
- `0x219d`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from TraceAssociationBase and TraceLogBase. Completed all Deletes : {2}`
- `0x21db`: `DeletionService: Execution of ShrinkTraceLogTable is completed.`
- `0x221e`: `DeletionService: Error cleaning up TraceLogBase Table`

## pseudocode

```c

```

## disassembly

```asm
0x2080  ldarg.0
0x2081  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2086  ldc.i4.s 0x14
0x2088  ldstr    aDeletionservic_51// "DeletionService: Inside DeletionService"...
0x208d  ldc.i4.0
0x208e  newarr   [mscorlib]System.Object
0x2093  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2098  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x209d  ldarg.0
0x209e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x20a3  ldstr    aShrinktracelog// "ShrinkTraceLogTable"
0x20a8  ldstr    aDeletionservic_51// "DeletionService: Inside DeletionService"...
0x20ad  ldc.i4.0
0x20ae  ldc.i4.0
0x20af  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x20b4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x20b9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x20be  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x20c3  ldc.i4.0
0x20c4  ldsfld   string [mscorlib]System.String::Empty
0x20c9  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x20ce  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x20d3  ldarg.0
0x20d4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x20d9  ldarg.0
0x20da  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x20df  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x20e4  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x20e9  ldstr    aTracelogpersis// "TraceLogPersistenceTimeInDays"
0x20ee  ldc.i4.s 0x1E
0x20f0  box      [mscorlib]System.Int32
0x20f5  callvirt instance object Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string orgSetting, object defaultValue)
0x20fa  unbox.any [mscorlib]System.Int32
0x20ff  stloc.0
0x2100  ldstr    aDeleteFromTrac// "DELETE from TraceAssociationBase where "...
0x2105  stloc.1
0x2106  ldarg.0
0x2107  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x210c  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x2111  ldc.i4.0
0x2112  ldc.i4.0
0x2113  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x2118  stloc.2
0x2119  ldloc.2
0x211a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x211f  ldsfld   string [mscorlib]System.String::Empty
0x2124  stloc.3
0x2125  ldloc.2
0x2126  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x212b  stloc.s  4
0x212d  ldloc.2
0x212e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2133  stloc.s  5
0x2135  ldc.i4.m1
0x2136  stloc.s  6
0x2138  ldc.i4.0
0x2139  stloc.s  7
0x213b  ldloc.s  5
0x213d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2142  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2147  dup
0x2148  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x214d  dup
0x214e  ldstr    aNumberofdays// "@numberofdays"
0x2153  ldloc.0
0x2154  neg
0x2155  box      [mscorlib]System.Int32
0x215a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x215f  pop
0x2160  ldstr    aMailboxtypecod// "@mailboxTypeCode"
0x2165  ldstr    a9606// "9606"
0x216a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x216f  pop
0x2170  ldloc.s  5
0x2172  ldloc.1
0x2173  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2178  ldloc.s  5
0x217a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x217f  stloc.3
0x2180  ldloc.s  4
0x2182  ldloc.s  5
0x2184  ldarg.0
0x2185  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x218a  ldloca.s 6
0x218c  ldloca.s 7
0x218e  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x2193  stloc.s  8
0x2195  ldarg.0
0x2196  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x219b  ldc.i4.s 0x14
0x219d  ldstr    aDeletionservic_52// "DeletionService: Deletion Service delet"...
0x21a2  ldc.i4.3
0x21a3  newarr   [mscorlib]System.Object
0x21a8  dup
0x21a9  ldc.i4.0
0x21aa  ldloc.s  8
0x21ac  box      [mscorlib]System.Int32
0x21b1  stelem.ref
0x21b2  dup
0x21b3  ldc.i4.1
0x21b4  ldloc.s  6
0x21b6  box      [mscorlib]System.Int32
0x21bb  stelem.ref
0x21bc  dup
0x21bd  ldc.i4.2
0x21be  ldloc.s  7
0x21c0  box      [mscorlib]System.Boolean
0x21c5  stelem.ref
0x21c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21cb  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x21d0  ldarg.0
0x21d1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x21d6  ldstr    aShrinktracelog// "ShrinkTraceLogTable"
0x21db  ldstr    aDeletionservic_53// "DeletionService: Execution of ShrinkTra"...
0x21e0  ldloc.s  8
0x21e2  ldloc.s  6
0x21e4  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x21e9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x21ee  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x21f3  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x21f8  ldc.i4.1
0x21f9  ldloc.s  5
0x21fb  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2200  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x2205  leave.s  loc_2213
0x2207  ldloc.s  5
0x2209  brfalse.s loc_2212
0x220b  ldloc.s  5
0x220d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2212  endfinally
0x2213  leave.s  loc_2248
0x2215  stloc.s  9
0x2217  ldarg.0
0x2218  ldc.i4   0x80004003
0x221d  conv.u8
0x221e  ldstr    aDeletionservic_54// "DeletionService: Error cleaning up Trac"...
0x2223  ldloc.s  9
0x2225  callvirt instance string [mscorlib]System.Object::ToString()
0x222a  ldloc.3
0x222b  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x2230  rethrow
0x2232  ldloc.s  4
0x2234  brfalse.s loc_223D
0x2236  ldloc.s  4
0x2238  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x223d  endfinally
0x223e  ldloc.2
0x223f  brfalse.s loc_2247
0x2241  ldloc.2
0x2242  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2247  endfinally
0x2248  ret
```
