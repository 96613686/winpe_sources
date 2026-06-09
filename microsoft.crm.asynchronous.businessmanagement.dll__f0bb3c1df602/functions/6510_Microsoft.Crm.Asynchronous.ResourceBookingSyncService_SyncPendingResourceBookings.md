# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncPendingResourceBookings

- ea: `0x6510`
- end: `0x67e7`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncPendingResourceBookings`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x8b30`

## callees

- `0x62c0`
- `0x6510`
- `0x8840`
- `0x8ab0`
- `0x13d70`
- `0x13da0`
- `0x13f60`
- `0x157e0`
- `0x157f0`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x6584`: `DELETE CLEANUP_IDMAPPING FROM BookableResourceBookingExchangeSyncIdMappingBase CLEANUP_IDMAPPING`
- `0x65b4`: `AND (CLEANUP_IDMAPPING.IsDeletedInExchange = @deletedInExchange`
- `0x65ea`: `@deletedInExchange`
- `0x671d`: `@deletedInExchange`
- `0x667f`: `SyncPendingResourceBookings_CleanupDeletedBookings`
- `0x6784`: `SyncPendingResourceBookings_CleanupDeletedBookings`
- `0x66be`: `DELETE FROM BookableResourceBookingExchangeSyncIdMappingBase`
- `0x66d8`: `AND (BookableResourceBookingExchangeSyncIdMappingBase.IsDeletedInExchange = @deletedInExchange`

## pseudocode

```c

```

## disassembly

```asm
0x6510  ldarg.0
0x6511  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6516  ldstr    aSyncpendingres// "SyncPendingResourceBookings"
0x651b  callvirt instance void Metrics::StartTimer(string name)
0x6520  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x6525  ldc.i4.0
0x6526  ldc.i4.0
0x6527  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x652c  stloc.0
0x652d  ldloc.0
0x652e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6533  ldarg.1
0x6534  ldloc.0
0x6535  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x653a  call     bool RunTimeControl::get_IsExpired()
0x653f  brtrue   loc_666F
0x6544  ldarg.0
0x6545  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x654a  ldstr    aSyncpendingres_0// "SyncPendingResourceBookings_CleanupPast"...
0x654f  callvirt instance void Metrics::StartTimer(string name)
0x6554  ldarg.1
0x6555  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x655a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x655f  stloc.1
0x6560  ldarg.1
0x6561  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6566  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x656b  stloc.2
0x656c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6571  stloc.3
0x6572  ldloc.2
0x6573  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6578  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x657d  dup
0x657e  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x6583  ldloc.3
0x6584  ldstr    aDeleteCleanupI// "DELETE CLEANUP_IDMAPPING FROM BookableR"...
0x6589  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x658e  pop
0x658f  ldloc.3
0x6590  ldstr    aJoinBookablere// "JOIN BookableResourceBookingBase"
0x6595  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x659a  pop
0x659b  ldloc.3
0x659c  ldstr    aOnBookablereso// "ON BookableResourceBookingBase.Bookable"...
0x65a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x65a6  pop
0x65a7  ldloc.3
0x65a8  ldstr    aWhereCleanupId// "WHERE CLEANUP_IDMAPPING.SyncStatus = @s"...
0x65ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x65b2  pop
0x65b3  ldloc.3
0x65b4  ldstr    aAndCleanupIdma// "AND (CLEANUP_IDMAPPING.IsDeletedInExcha"...
0x65b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x65be  pop
0x65bf  ldloc.3
0x65c0  ldstr    aOrCleanupIdmap// "OR CLEANUP_IDMAPPING.Retries >= @maxRet"...
0x65c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x65ca  pop
0x65cb  ldloc.3
0x65cc  ldstr    aAndBookableres// "AND BookableResourceBookingBase.StartTi"...
0x65d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x65d6  pop
0x65d7  dup
0x65d8  ldstr    aSyncstatus// "@syncStatus"
0x65dd  ldc.i4.2
0x65de  box      SyncStatus
0x65e3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65e8  pop
0x65e9  dup
0x65ea  ldstr    aDeletedinexcha// "@deletedInExchange"
0x65ef  ldc.i4.0
0x65f0  box      [mscorlib]System.Int32
0x65f5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65fa  pop
0x65fb  dup
0x65fc  ldstr    aMaxretries// "@maxRetries"
0x6601  ldarg.0
0x6602  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6607  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x660c  box      [mscorlib]System.Int32
0x6611  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6616  pop
0x6617  ldstr    aLowerbounddate// "@lowerBoundDateTime"
0x661c  ldarg.0
0x661d  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6622  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_LowerBoundDateTime()
0x6627  box      [mscorlib]System.DateTime
0x662c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6631  pop
0x6632  ldloc.2
0x6633  ldloc.3
0x6634  callvirt instance string [mscorlib]System.Object::ToString()
0x6639  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x663e  ldarg.0
0x663f  ldloc.1
0x6640  ldloc.2
0x6641  ldc.i4.s 9
0x6643  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x6648  pop
0x6649  leave.s  loc_665F
0x664b  ldloc.2
0x664c  brfalse.s loc_6654
0x664e  ldloc.2
0x664f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6654  endfinally
0x6655  ldloc.1
0x6656  brfalse.s loc_665E
0x6658  ldloc.1
0x6659  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x665e  endfinally
0x665f  ldarg.0
0x6660  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6665  ldstr    aSyncpendingres_0// "SyncPendingResourceBookings_CleanupPast"...
0x666a  callvirt instance void Metrics::StopTimer(string name)
0x666f  call     bool RunTimeControl::get_IsExpired()
0x6674  brtrue   loc_678E
0x6679  ldarg.0
0x667a  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x667f  ldstr    aSyncpendingres_1// "SyncPendingResourceBookings_CleanupDele"...
0x6684  callvirt instance void Metrics::StartTimer(string name)
0x6689  ldarg.1
0x668a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x668f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x6694  stloc.s  4
0x6696  ldarg.1
0x6697  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x669c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x66a1  stloc.s  5
0x66a3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x66a8  stloc.s  6
0x66aa  ldloc.s  5
0x66ac  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x66b1  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x66b6  dup
0x66b7  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x66bc  ldloc.s  6
0x66be  ldstr    aDeleteFromBook// "DELETE FROM BookableResourceBookingExch"...
0x66c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x66c8  pop
0x66c9  ldloc.s  6
0x66cb  ldstr    aWhereBookabler// "WHERE BookableResourceBookingExchangeSy"...
0x66d0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x66d5  pop
0x66d6  ldloc.s  6
0x66d8  ldstr    aAndBookableres_0// "AND (BookableResourceBookingExchangeSyn"...
0x66dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x66e2  pop
0x66e3  ldloc.s  6
0x66e5  ldstr    aOrBookablereso// "OR BookableResourceBookingExchangeSyncI"...
0x66ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x66ef  pop
0x66f0  ldloc.s  6
0x66f2  ldstr    aAndNotExistsSe// "AND NOT EXISTS (SELECT NULL FROM Bookab"...
0x66f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x66fc  pop
0x66fd  ldloc.s  6
0x66ff  ldstr    aWhereBookabler_0// "WHERE BookableResourceBookingBase.Booka"...
0x6704  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x6709  pop
0x670a  dup
0x670b  ldstr    aSyncstatus// "@syncStatus"
0x6710  ldc.i4.2
0x6711  box      SyncStatus
0x6716  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x671b  pop
0x671c  dup
0x671d  ldstr    aDeletedinexcha// "@deletedInExchange"
0x6722  ldc.i4.0
0x6723  box      [mscorlib]System.Int32
0x6728  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x672d  pop
0x672e  ldstr    aMaxretries// "@maxRetries"
0x6733  ldarg.0
0x6734  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6739  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x673e  box      [mscorlib]System.Int32
0x6743  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6748  pop
0x6749  ldloc.s  5
0x674b  ldloc.s  6
0x674d  callvirt instance string [mscorlib]System.Object::ToString()
0x6752  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6757  ldarg.0
0x6758  ldloc.s  4
0x675a  ldloc.s  5
0x675c  ldc.i4.s 9
0x675e  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x6763  pop
0x6764  leave.s  loc_677E
0x6766  ldloc.s  5
0x6768  brfalse.s loc_6771
0x676a  ldloc.s  5
0x676c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6771  endfinally
0x6772  ldloc.s  4
0x6774  brfalse.s loc_677D
0x6776  ldloc.s  4
0x6778  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x677d  endfinally
0x677e  ldarg.0
0x677f  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6784  ldstr    aSyncpendingres_1// "SyncPendingResourceBookings_CleanupDele"...
0x6789  callvirt instance void Metrics::StopTimer(string name)
0x678e  leave.s  loc_67A8
0x6790  ldloc.0
0x6791  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6796  ldarg.1
0x6797  ldnull
0x6798  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x679d  endfinally
0x679e  ldloc.0
0x679f  brfalse.s loc_67A7
0x67a1  ldloc.0
0x67a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67a7  endfinally
0x67a8  call     bool RunTimeControl::get_IsExpired()
0x67ad  brtrue.s loc_67D6
0x67af  ldarg.0
0x67b0  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x67b5  ldstr    aSyncpendingres_2// "SyncPendingResourceBookings_Sync"
0x67ba  callvirt instance void Metrics::StartTimer(string name)
0x67bf  ldarg.0
0x67c0  ldarg.1
0x67c1  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncResourceBookings(class SyncConfig syncConfig)
0x67c6  ldarg.0
0x67c7  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x67cc  ldstr    aSyncpendingres_2// "SyncPendingResourceBookings_Sync"
0x67d1  callvirt instance void Metrics::StopTimer(string name)
0x67d6  ldarg.0
0x67d7  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x67dc  ldstr    aSyncpendingres// "SyncPendingResourceBookings"
0x67e1  callvirt instance void Metrics::StopTimer(string name)
0x67e6  ret
```
