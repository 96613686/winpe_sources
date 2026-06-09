# Microsoft.Crm.DeletionService::<CleanUpOfficeDocumentRecords>b__32_0

- ea: `0x2250`
- end: `0x24c8`
- name: `Microsoft.Crm.DeletionService::<CleanUpOfficeDocumentRecords>b__32_0`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x640`
- `0x2250`
- `0xaf40`
- `0xaf50`
- `0x496d0`
- `0x4e2a0`
- `0x86c40`
- `0x96cd0`

## string_xrefs

- `0x23c6`: `@numOfRecordsToBeDeleted`
- `0x2258`: `DeletionService: Inside DeletionService.CleanUpOfficeDocumentRecords`
- `0x2278`: `DeletionService: Inside DeletionService.CleanUpOfficeDocumentRecords`
- `0x22ba`: `DeletionService: Checking whether the officedocument entity exists in metadata`
- `0x2306`: `DeletionService: Officedocument entity exists in metadata`
- `0x2361`: `DELETE TOP(@numOfRecordsToBeDeleted) from OfficeDocumentBase where DocumentType=1 AND CreatedOn < DATEADD(DAY,@numberofdays,GETUTCDATE())`
- `0x2400`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from table OfficeDocumentBase based on DocumentType=1 and CreatedOn older than {2} days. Completed all Deletes : {3}`
- `0x2447`: `Deletion Service deleted {0} rows in {1} seconds from table OfficeDocumentBase based on DocumentType=1 and CreatedOn older than {2} days. Completed all Deletes : {3}`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldarg.0
0x2251  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2256  ldc.i4.s 0x14
0x2258  ldstr    aDeletionservic_55// "DeletionService: Inside DeletionService"...
0x225d  ldc.i4.0
0x225e  newarr   [mscorlib]System.Object
0x2263  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2268  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x226d  ldarg.0
0x226e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2273  ldstr    aCleanupofficed// "CleanUpOfficeDocumentRecords"
0x2278  ldstr    aDeletionservic_55// "DeletionService: Inside DeletionService"...
0x227d  ldc.i4.0
0x227e  ldc.i4.0
0x227f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x2284  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x2289  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x228e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x2293  ldc.i4.0
0x2294  ldsfld   string [mscorlib]System.String::Empty
0x2299  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x229e  ldarg.0
0x229f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x22a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x22a9  stloc.0
0x22aa  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x22af  ldarg.0
0x22b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x22b5  ldstr    aCleanupofficed// "CleanUpOfficeDocumentRecords"
0x22ba  ldstr    aDeletionservic_56// "DeletionService: Checking whether the o"...
0x22bf  ldc.i4.0
0x22c0  ldc.i4.0
0x22c1  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x22c6  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x22cb  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x22d0  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x22d5  ldc.i4.0
0x22d6  ldsfld   string [mscorlib]System.String::Empty
0x22db  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x22e0  ldloc.0
0x22e1  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22e6  ldstr    aOfficedocument// "officedocument"
0x22eb  ldc.i4.1
0x22ec  callvirt instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string entityName, valuetype Microsoft.Crm.Metadata.NameMappingType mapping)
0x22f1  brfalse  loc_24C7
0x22f6  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x22fb  ldarg.0
0x22fc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2301  ldstr    aCleanupofficed// "CleanUpOfficeDocumentRecords"
0x2306  ldstr    aDeletionservic_57// "DeletionService: Officedocument entity "...
0x230b  ldc.i4.0
0x230c  ldc.i4.0
0x230d  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x2312  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x2317  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x231c  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x2321  ldc.i4.0
0x2322  ldsfld   string [mscorlib]System.String::Empty
0x2327  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x232c  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x2331  ldarg.0
0x2332  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2337  ldloc.0
0x2338  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x233d  ldstr    aOfficedocument_0// "officeDocumentPersistenceTimeInDays"
0x2342  ldc.i4.7
0x2343  box      [mscorlib]System.Int32
0x2348  callvirt instance object Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string orgSetting, object defaultValue)
0x234d  unbox.any [mscorlib]System.Int32
0x2352  stloc.1
0x2353  ldloc.1
0x2354  ldc.i4.1
0x2355  bge.s    loc_235A
0x2357  ldc.i4.1
0x2358  br.s     loc_235B
0x235a  ldloc.1
0x235b  stloc.1
0x235c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2361  ldstr    aDeleteTopNumof_5// "DELETE TOP(@numOfRecordsToBeDeleted) fr"...
0x2366  ldc.i4.0
0x2367  newarr   [mscorlib]System.Object
0x236c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2371  stloc.2
0x2372  ldarg.0
0x2373  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2378  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x237d  ldc.i4.0
0x237e  ldc.i4.0
0x237f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x2384  stloc.3
0x2385  ldloc.3
0x2386  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x238b  stloc.s  4
0x238d  ldloc.3
0x238e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2393  ldloc.3
0x2394  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2399  stloc.s  5
0x239b  ldc.i4.m1
0x239c  stloc.s  6
0x239e  ldc.i4.0
0x239f  stloc.s  7
0x23a1  ldloc.s  5
0x23a3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x23a8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x23ad  dup
0x23ae  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x23b3  dup
0x23b4  ldstr    aNumberofdays// "@numberofdays"
0x23b9  ldloc.1
0x23ba  neg
0x23bb  box      [mscorlib]System.Int32
0x23c0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x23c5  pop
0x23c6  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x23cb  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x23d0  box      [mscorlib]System.Int32
0x23d5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x23da  pop
0x23db  ldloc.s  5
0x23dd  ldloc.2
0x23de  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x23e3  ldloc.s  4
0x23e5  ldloc.s  5
0x23e7  ldarg.0
0x23e8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x23ed  ldloca.s 6
0x23ef  ldloca.s 7
0x23f1  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x23f6  stloc.s  8
0x23f8  ldarg.0
0x23f9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x23fe  ldc.i4.s 0x14
0x2400  ldstr    aDeletionservic_58// "DeletionService: Deletion Service delet"...
0x2405  ldc.i4.4
0x2406  newarr   [mscorlib]System.Object
0x240b  dup
0x240c  ldc.i4.0
0x240d  ldloc.s  8
0x240f  box      [mscorlib]System.Int32
0x2414  stelem.ref
0x2415  dup
0x2416  ldc.i4.1
0x2417  ldloc.s  6
0x2419  box      [mscorlib]System.Int32
0x241e  stelem.ref
0x241f  dup
0x2420  ldc.i4.2
0x2421  ldloc.1
0x2422  box      [mscorlib]System.Int32
0x2427  stelem.ref
0x2428  dup
0x2429  ldc.i4.3
0x242a  ldloc.s  7
0x242c  box      [mscorlib]System.Boolean
0x2431  stelem.ref
0x2432  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2437  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x243c  ldarg.0
0x243d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x2442  ldstr    aCleanupofficed// "CleanUpOfficeDocumentRecords"
0x2447  ldstr    aDeletionServic// "Deletion Service deleted {0} rows in {1"...
0x244c  ldc.i4.4
0x244d  newarr   [mscorlib]System.Object
0x2452  dup
0x2453  ldc.i4.0
0x2454  ldloc.s  8
0x2456  box      [mscorlib]System.Int32
0x245b  stelem.ref
0x245c  dup
0x245d  ldc.i4.1
0x245e  ldloc.s  6
0x2460  box      [mscorlib]System.Int32
0x2465  stelem.ref
0x2466  dup
0x2467  ldc.i4.2
0x2468  ldloc.1
0x2469  box      [mscorlib]System.Int32
0x246e  stelem.ref
0x246f  dup
0x2470  ldc.i4.3
0x2471  ldloc.s  7
0x2473  box      [mscorlib]System.Boolean
0x2478  stelem.ref
0x2479  call     string [mscorlib]System.String::Format(string, object[])
0x247e  ldloc.s  8
0x2480  ldloc.s  6
0x2482  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x2487  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x248c  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x2491  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x2496  ldc.i4.1
0x2497  ldloc.s  5
0x2499  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x249e  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x24a3  leave.s  loc_24C7
0x24a5  ldloc.s  5
0x24a7  brfalse.s loc_24B0
0x24a9  ldloc.s  5
0x24ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24b0  endfinally
0x24b1  ldloc.s  4
0x24b3  brfalse.s loc_24BC
0x24b5  ldloc.s  4
0x24b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24bc  endfinally
0x24bd  ldloc.3
0x24be  brfalse.s loc_24C6
0x24c0  ldloc.3
0x24c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24c6  endfinally
0x24c7  ret
```
