# Microsoft.Crm.DeletionService::<CleanUpPOA>b__18_0

- ea: `0x11e0`
- end: `0x1462`
- name: `Microsoft.Crm.DeletionService::<CleanUpPOA>b__18_0`
- size: `642`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e0`
- `0x640`
- `0x11e0`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x129b`: `@numOfRecordsToBeDeleted`
- `0x11e8`: `DeletionService: Inside DeletionService.CleanUpPOA`
- `0x1208`: `DeletionService: Inside DeletionService.CleanUpPOA`
- `0x1267`: `declare @versionNumberExpired timestamp;\nselect @versionNumberExpired = convert(timestamp,coalesce(min(CompletedSyncVersionNumber), @@dbts)) from Subscription;\ndelete top(@numOfRecordsToBeDeleted) from PrincipalObjectAccess where (AccessRightsMask = 0 or AccessRightsMask is null) \n	and (InheritedAccessRightsMask = 0 or InheritedAccessRightsMask is null) and VersionNumber <= @versionNumberExpired\n	option (maxdop {0});`
- `0x12d2`: `DeletionService: CleanupPOA deleted {0} rows in {1} seconds from table PrincipalObjectAccess based on version number expired. Completed all Deletes : {2}`
- `0x1310`: `DeletionService:CleanupPOA deleted data from table PrincipalObjectAccess based on version number expired. Completed all Deletes `
- `0x1346`: `delete top(@numOfRecordsToBeDeleted) poa from PrincipalObjectAccess poa\n	inner join SubscriptionTrackingDeletedObject o on (o.ObjectId = poa.ObjectId and o.ObjectTypeCode=poa.ObjectTypeCode)\n	option (maxdop {0});`
- `0x138f`: `DeletionService: CleanupPOA deleted {0} rows in {1} seconds from table PrincipalObjectAccess based on matching records found in SubscriptionTrackingDeletedObject. Completed all Deletes : {2}`
- `0x13d1`: `DeletionService:CleanupPOA deleted data from table PrincipalObjectAccess based on matching records found in SubscriptionTrackingDeletedObject. Completed all Deletes.`
- `0x140c`: `DeletionService: More records pending to be deleted from PrincipalObjectAccess that matches SubscriptionTrackingDeletedObject`
- `0x1439`: `DeletionService: Error cleaning up Principal Object Access Table`

## pseudocode

```c

```

## disassembly

```asm
0x11e0  ldarg.0
0x11e1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x11e6  ldc.i4.s 0x14
0x11e8  ldstr    aDeletionservic_19// "DeletionService: Inside DeletionService"...
0x11ed  ldc.i4.0
0x11ee  newarr   [mscorlib]System.Object
0x11f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11f8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x11fd  ldarg.0
0x11fe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1203  ldstr    aCleanuppoa// "CleanUpPOA"
0x1208  ldstr    aDeletionservic_19// "DeletionService: Inside DeletionService"...
0x120d  ldc.i4.0
0x120e  ldc.i4.0
0x120f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1214  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1219  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x121e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1223  ldc.i4.0
0x1224  ldsfld   string [mscorlib]System.String::Empty
0x1229  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x122e  ldarg.0
0x122f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1234  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1239  ldc.i4.0
0x123a  ldc.i4.0
0x123b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1240  stloc.0
0x1241  ldloc.0
0x1242  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1247  ldloc.0
0x1248  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x124d  stloc.1
0x124e  ldsfld   string [mscorlib]System.String::Empty
0x1253  stloc.2
0x1254  ldloc.0
0x1255  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x125a  stloc.3
0x125b  ldc.i4.m1
0x125c  stloc.s  4
0x125e  ldc.i4.0
0x125f  stloc.s  5
0x1261  ldloc.3
0x1262  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1267  ldstr    aDeclareVersion_0// "declare @versionNumberExpired timestamp"...
0x126c  ldc.i4.1
0x126d  newarr   [mscorlib]System.Object
0x1272  dup
0x1273  ldc.i4.0
0x1274  ldarg.0
0x1275  ldfld    int32 Microsoft.Crm.DeletionService::_maxDop
0x127a  box      [mscorlib]System.Int32
0x127f  stelem.ref
0x1280  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1285  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x128a  ldloc.3
0x128b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1290  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1295  dup
0x1296  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x129b  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x12a0  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x12a5  box      [mscorlib]System.Int32
0x12aa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12af  pop
0x12b0  ldloc.3
0x12b1  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x12b6  stloc.2
0x12b7  ldloc.1
0x12b8  ldloc.3
0x12b9  ldarg.0
0x12ba  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x12bf  ldloca.s 4
0x12c1  ldloca.s 5
0x12c3  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x12c8  stloc.s  6
0x12ca  ldarg.0
0x12cb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x12d0  ldc.i4.s 0x14
0x12d2  ldstr    aDeletionservic_20// "DeletionService: CleanupPOA deleted {0}"...
0x12d7  ldc.i4.3
0x12d8  newarr   [mscorlib]System.Object
0x12dd  dup
0x12de  ldc.i4.0
0x12df  ldloc.s  6
0x12e1  box      [mscorlib]System.Int32
0x12e6  stelem.ref
0x12e7  dup
0x12e8  ldc.i4.1
0x12e9  ldloc.s  4
0x12eb  box      [mscorlib]System.Int32
0x12f0  stelem.ref
0x12f1  dup
0x12f2  ldc.i4.2
0x12f3  ldloc.s  5
0x12f5  box      [mscorlib]System.Boolean
0x12fa  stelem.ref
0x12fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1300  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1305  ldarg.0
0x1306  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x130b  ldstr    aCleanuppoa// "CleanUpPOA"
0x1310  ldstr    aDeletionservic_21// "DeletionService:CleanupPOA deleted data"...
0x1315  ldloc.s  6
0x1317  ldloc.s  4
0x1319  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x131e  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1323  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1328  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x132d  ldc.i4.1
0x132e  ldloc.3
0x132f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1334  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1339  ldarg.0
0x133a  ldc.i4.0
0x133b  stfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x1340  ldloc.3
0x1341  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1346  ldstr    aDeleteTopNumof_0// "delete top(@numOfRecordsToBeDeleted) po"...
0x134b  ldc.i4.1
0x134c  newarr   [mscorlib]System.Object
0x1351  dup
0x1352  ldc.i4.0
0x1353  ldarg.0
0x1354  ldfld    int32 Microsoft.Crm.DeletionService::_maxDop
0x1359  box      [mscorlib]System.Int32
0x135e  stelem.ref
0x135f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1364  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1369  ldloc.3
0x136a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x136f  stloc.2
0x1370  ldloc.1
0x1371  ldloc.3
0x1372  ldarg.0
0x1373  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1378  ldloca.s 4
0x137a  ldarg.0
0x137b  ldflda   bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x1380  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x1385  stloc.s  6
0x1387  ldarg.0
0x1388  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x138d  ldc.i4.s 0x14
0x138f  ldstr    aDeletionservic_22// "DeletionService: CleanupPOA deleted {0}"...
0x1394  ldc.i4.3
0x1395  newarr   [mscorlib]System.Object
0x139a  dup
0x139b  ldc.i4.0
0x139c  ldloc.s  6
0x139e  box      [mscorlib]System.Int32
0x13a3  stelem.ref
0x13a4  dup
0x13a5  ldc.i4.1
0x13a6  ldloc.s  4
0x13a8  box      [mscorlib]System.Int32
0x13ad  stelem.ref
0x13ae  dup
0x13af  ldc.i4.2
0x13b0  ldarg.0
0x13b1  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x13b6  box      [mscorlib]System.Boolean
0x13bb  stelem.ref
0x13bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13c1  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x13c6  ldarg.0
0x13c7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x13cc  ldstr    aCleanuppoa// "CleanUpPOA"
0x13d1  ldstr    aDeletionservic_23// "DeletionService:CleanupPOA deleted data"...
0x13d6  ldloc.s  6
0x13d8  ldloc.s  4
0x13da  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x13df  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x13e4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x13e9  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x13ee  ldarg.0
0x13ef  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x13f4  ldloc.3
0x13f5  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x13fa  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x13ff  ldarg.0
0x1400  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x1405  brtrue.s loc_1422
0x1407  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x140c  ldstr    aDeletionservic_24// "DeletionService: More records pending t"...
0x1411  ldc.i4.0
0x1412  newarr   [mscorlib]System.Object
0x1417  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x141c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1421  throw
0x1422  leave.s  loc_142E
0x1424  ldloc.3
0x1425  brfalse.s loc_142D
0x1427  ldloc.3
0x1428  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x142d  endfinally
0x142e  leave.s  loc_1461
0x1430  stloc.s  7
0x1432  ldarg.0
0x1433  ldc.i4   0x80004004
0x1438  conv.u8
0x1439  ldstr    aDeletionservic_25// "DeletionService: Error cleaning up Prin"...
0x143e  ldloc.s  7
0x1440  callvirt instance string [mscorlib]System.Object::ToString()
0x1445  ldloc.2
0x1446  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x144b  rethrow
0x144d  ldloc.1
0x144e  brfalse.s loc_1456
0x1450  ldloc.1
0x1451  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1456  endfinally
0x1457  ldloc.0
0x1458  brfalse.s loc_1460
0x145a  ldloc.0
0x145b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1460  endfinally
0x1461  ret
```
