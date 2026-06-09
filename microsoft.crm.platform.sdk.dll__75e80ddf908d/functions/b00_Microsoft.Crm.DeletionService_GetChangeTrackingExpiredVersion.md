# Microsoft.Crm.DeletionService::GetChangeTrackingExpiredVersion

- ea: `0xb00`
- end: `0xccb`
- name: `Microsoft.Crm.DeletionService::GetChangeTrackingExpiredVersion`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1600`

## callees

- `0xa50`
- `0xb00`
- `0xcd0`
- `0xdc0`
- `0xaf40`
- `0xaf50`
- `0x86980`
- `0x96cd0`

## string_xrefs

- `0xc24`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0xb39`: `DeletionService: Change Tracking Enabled for at least one Entity with DeletedChangeTrackingExpiryInDays {0}`
- `0xb62`: `DeletionService: Change Tracking Enabled for at least one Entity with DeletedChangeTrackingExpiryInDays {0}`
- `0xba0`: `BEGIN\nDECLARE @TempTable TABLE (TimeStamp BIGINT, Date DateTime)\nDECLARE @now DateTime = getutcdate();\n\nDELETE FROM [TimeStampDateMapping] \nOUTPUT Deleted.TimeStamp, Deleted.Date INTO @TempTable\nWHERE datediff(dd, Date, @now) >= @deletedChangeTrackingExpiryInDays;\n\nSELECT TOP 1 * FROM @TempTable order by Date desc\nEND`
- `0xbc6`: `@deletedChangeTrackingExpiryInDays`
- `0xbe7`: `DeletionService: Deleting all the rows from change tracking db time stamp which are older than {0} days`
- `0xc63`: `DeletionService: Deleted all the rows from change tracking db time stamp which are older than {0} days and fetching last recently deleted one by date having changeTrackingExpiredVersion as {1}`

## pseudocode

```c

```

## disassembly

```asm
0xb00  ldarg.2
0xb01  stloc.0
0xb02  ldarg.0
0xb03  call     instance bool Microsoft.Crm.DeletionService::IsChangeTrackingEnabledForAnyEntity()
0xb08  brfalse  loc_CC2
0xb0d  ldc.i4.m1
0xb0e  conv.i8
0xb0f  stloc.0
0xb10  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0xb15  ldarg.0
0xb16  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xb1b  ldarg.0
0xb1c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xb21  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xb26  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xb2b  callvirt instance int32 Microsoft.Crm.Caching.IOrganizationSettings::get_DeletedChangeTrackingExpiryInDays()
0xb30  stloc.1
0xb31  ldarg.0
0xb32  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xb37  ldc.i4.s 0x14
0xb39  ldstr    aDeletionservic_5// "DeletionService: Change Tracking Enable"...
0xb3e  ldc.i4.1
0xb3f  newarr   [mscorlib]System.Object
0xb44  dup
0xb45  ldc.i4.0
0xb46  ldloc.1
0xb47  box      [mscorlib]System.Int32
0xb4c  stelem.ref
0xb4d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb52  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xb57  ldarg.0
0xb58  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xb5d  ldstr    aGetchangetrack// "GetChangeTrackingExpiredVersion"
0xb62  ldstr    aDeletionservic_5// "DeletionService: Change Tracking Enable"...
0xb67  ldloc.1
0xb68  box      [mscorlib]System.Int32
0xb6d  call     string [mscorlib]System.String::Format(string, object)
0xb72  ldc.i4.0
0xb73  ldc.i4.m1
0xb74  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xb79  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xb7e  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xb83  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xb88  ldc.i4.0
0xb89  ldsfld   string [mscorlib]System.String::Empty
0xb8e  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xb93  ldarg.1
0xb94  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xb99  stloc.2
0xb9a  ldloc.2
0xb9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba0  ldstr    aBeginDeclareTe// "BEGIN\r\nDECLARE @TempTable TABLE (Time"...
0xba5  ldc.i4.0
0xba6  newarr   [mscorlib]System.Object
0xbab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbb0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xbb5  ldloc.2
0xbb6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xbbb  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xbc0  dup
0xbc1  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0xbc6  ldstr    aDeletedchanget// "@deletedChangeTrackingExpiryInDays"
0xbcb  ldloc.1
0xbcc  box      [mscorlib]System.Int32
0xbd1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xbd6  pop
0xbd7  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xbdc  ldarg.0
0xbdd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xbe2  ldstr    aGetchangetrack// "GetChangeTrackingExpiredVersion"
0xbe7  ldstr    aDeletionservic_6// "DeletionService: Deleting all the rows "...
0xbec  ldloc.1
0xbed  box      [mscorlib]System.Int32
0xbf2  call     string [mscorlib]System.String::Format(string, object)
0xbf7  ldc.i4.0
0xbf8  ldc.i4.m1
0xbf9  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xbfe  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xc03  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xc08  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xc0d  ldc.i4.0
0xc0e  ldloc.2
0xc0f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xc14  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xc19  ldloc.2
0xc1a  ldc.i4   0x2C1
0xc1f  ldstr    aGetchangetrack// "GetChangeTrackingExpiredVersion"
0xc24  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0xc29  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xc2e  stloc.3
0xc2f  ldloc.3
0xc30  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xc35  brfalse.s loc_C50
0xc37  ldloc.3
0xc38  ldstr    aTimestamp// "TimeStamp"
0xc3d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xc42  unbox.any [mscorlib]System.Int64
0xc47  stloc.0
0xc48  ldloc.0
0xc49  ldarg.2
0xc4a  ble.s    loc_C53
0xc4c  ldarg.2
0xc4d  stloc.0
0xc4e  br.s     loc_C53
0xc50  ldc.i4.m1
0xc51  conv.i8
0xc52  stloc.0
0xc53  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xc58  ldarg.0
0xc59  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xc5e  ldstr    aGetchangetrack// "GetChangeTrackingExpiredVersion"
0xc63  ldstr    aDeletionservic_7// "DeletionService: Deleted all the rows f"...
0xc68  ldloc.1
0xc69  box      [mscorlib]System.Int32
0xc6e  ldloc.0
0xc6f  box      [mscorlib]System.Int64
0xc74  call     string [mscorlib]System.String::Format(string, object, object)
0xc79  ldc.i4.0
0xc7a  ldc.i4.m1
0xc7b  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xc80  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xc85  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xc8a  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xc8f  ldc.i4.1
0xc90  ldloc.2
0xc91  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xc96  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xc9b  leave.s  loc_CB1
0xc9d  ldloc.3
0xc9e  brfalse.s loc_CA6
0xca0  ldloc.3
0xca1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca6  endfinally
0xca7  ldloc.2
0xca8  brfalse.s loc_CB0
0xcaa  ldloc.2
0xcab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb0  endfinally
0xcb1  ldloc.1
0xcb2  ldc.i4.0
0xcb3  ble.s    loc_CBE
0xcb5  ldarg.0
0xcb6  ldarg.1
0xcb7  call     instance void Microsoft.Crm.DeletionService::TrackChangeTrackingTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0xcbc  br.s     loc_CC9
0xcbe  ldarg.2
0xcbf  stloc.0
0xcc0  br.s     loc_CC9
0xcc2  ldarg.0
0xcc3  ldarg.1
0xcc4  call     instance void Microsoft.Crm.DeletionService::CleanUpChangeTrackingTimeStamps(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0xcc9  ldloc.0
0xcca  ret
```
