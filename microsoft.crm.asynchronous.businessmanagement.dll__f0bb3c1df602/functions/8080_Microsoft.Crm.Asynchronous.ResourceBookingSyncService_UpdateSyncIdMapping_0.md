# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping_0

- ea: `0x8080`
- end: `0x82a6`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping_0`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8050`

## callees

- `0x8080`
- `0x8840`
- `0x15820`
- `0x15860`
- `0x15880`
- `0x158a0`
- `0x15980`
- `0x159a0`
- `0x159c0`
- `0x15a00`
- `0x15a20`
- `0x160d0`
- `0x16260`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x80bb`: `UPDATE BookableResourceBookingExchangeSyncIdMappingBase SET`
- `0x80df`: `IsDeletedInExchange = 0,`
- `0x8086`: `MethodUpdateSyncIdMapping`
- `0x829b`: `MethodUpdateSyncIdMapping`
- `0x8096`: `MethodUpdateSyncIdMappingCallCount`

## pseudocode

```c

```

## disassembly

```asm
0x8080  ldarg.0
0x8081  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8086  ldstr    aMethodupdatesy// "MethodUpdateSyncIdMapping"
0x808b  callvirt instance void Metrics::StartTimer(string name)
0x8090  ldarg.0
0x8091  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8096  ldstr    aMethodupdatesy_0// "MethodUpdateSyncIdMappingCallCount"
0x809b  ldc.i4.1
0x809c  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x80a1  pop
0x80a2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x80a7  stloc.1
0x80a8  ldarg.2
0x80a9  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x80ae  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x80b3  stloc.2
0x80b4  ldloc.2
0x80b5  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x80ba  ldloc.1
0x80bb  ldstr    aUpdateBookable// "UPDATE BookableResourceBookingExchangeS"...
0x80c0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x80c5  pop
0x80c6  ldloc.1
0x80c7  ldstr    aSyncstatusSync_0// "SyncStatus = @syncStatus,"
0x80cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x80d1  pop
0x80d2  ldloc.1
0x80d3  ldstr    aModifiedonModi_0// "ModifiedOn = @modifiedOn,"
0x80d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x80dd  pop
0x80de  ldloc.1
0x80df  ldstr    aIsdeletedinexc_1// "IsDeletedInExchange = 0,"
0x80e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x80e9  pop
0x80ea  ldloc.2
0x80eb  ldstr    aModifiedon_1// "@modifiedOn"
0x80f0  call     valuetype [mscorlib]System.DateTime Utils::RoundDateTimeUtcNow()
0x80f5  box      [mscorlib]System.DateTime
0x80fa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x80ff  pop
0x8100  ldarg.3
0x8101  callvirt instance class SyncResult SyncData::get_SyncResult()
0x8106  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x810b  stloc.3
0x810c  ldc.i4.0
0x810d  stloc.s  4
0x810f  ldloca.s 3
0x8111  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x8116  ldloc.s  4
0x8118  beq.s    loc_811D
0x811a  ldc.i4.0
0x811b  br.s     loc_8124
0x811d  ldloca.s 3
0x811f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x8124  brfalse  loc_81CA
0x8129  ldloc.1
0x812a  ldstr    aRetriesCaseWhe// "Retries = CASE WHEN SyncStatus = 1 THEN"...
0x812f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8134  pop
0x8135  ldloc.1
0x8136  ldstr    aLastsyncerrorc// "LastSyncErrorCode = @lastSyncErrorCode,"
0x813b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8140  pop
0x8141  ldloc.1
0x8142  ldstr    aLastsyncerrorL// "LastSyncError = @lastSyncError,"
0x8147  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x814c  pop
0x814d  ldloc.1
0x814e  ldstr    aLastsyncerroro_1// "LastSyncErrorOccurredOn = @lastSyncErro"...
0x8153  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8158  pop
0x8159  ldloc.2
0x815a  ldstr    aLastsyncerrorc_0// "@lastSyncErrorCode"
0x815f  ldarg.3
0x8160  callvirt instance class SyncResult SyncData::get_SyncResult()
0x8165  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> SyncResult::get_ErrorCode()
0x816a  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>
0x816f  dup
0x8170  brtrue.s loc_8178
0x8172  pop
0x8173  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8178  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x817d  pop
0x817e  ldloc.2
0x817f  ldstr    aLastsyncerror// "@lastSyncError"
0x8184  ldarg.3
0x8185  callvirt instance class SyncResult SyncData::get_SyncResult()
0x818a  callvirt instance string SyncResult::get_ErrorMessage()
0x818f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8194  pop
0x8195  ldloc.2
0x8196  ldstr    aLastsyncerroro_0// "@lastSyncErrorOccurredOn"
0x819b  ldarg.3
0x819c  callvirt instance class SyncResult SyncData::get_SyncResult()
0x81a1  callvirt instance valuetype [mscorlib]System.DateTime SyncResult::get_Date()
0x81a6  box      [mscorlib]System.DateTime
0x81ab  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x81b0  pop
0x81b1  ldloc.2
0x81b2  ldstr    aSyncstatus// "@syncStatus"
0x81b7  ldc.i4.1
0x81b8  box      SyncStatus
0x81bd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x81c2  pop
0x81c3  ldc.i4.5
0x81c4  stloc.0
0x81c5  br       loc_825C
0x81ca  ldloc.1
0x81cb  ldstr    aRetries0// "Retries = 0,"
0x81d0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x81d5  pop
0x81d6  ldloc.1
0x81d7  ldstr    aSyncversionnum// "SyncVersionNumber = @synchronizedVersio"...
0x81dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x81e1  pop
0x81e2  ldarg.3
0x81e3  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x81e8  brtrue.s loc_8208
0x81ea  ldloc.1
0x81eb  ldstr    aExchangeentryi_2// ", ExchangeEntryId = @exchangeId"
0x81f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x81f5  pop
0x81f6  ldloc.2
0x81f7  ldstr    aExchangeid// "@exchangeId"
0x81fc  ldarg.3
0x81fd  callvirt instance string SyncData::get_ExchangeId()
0x8202  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8207  pop
0x8208  ldloc.2
0x8209  ldstr    aSynchronizedve_0// "@synchronizedVersionNumber"
0x820e  ldarg.3
0x820f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity SyncData::get_ResourceBooking()
0x8214  ldstr    aVersionnumber// "versionnumber"
0x8219  callvirt T0x2B000019
0x821e  box      [mscorlib]System.Int64
0x8223  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8228  pop
0x8229  ldarg.3
0x822a  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x822f  ldc.i4.4
0x8230  bne.un.s loc_8248
0x8232  ldloc.2
0x8233  ldstr    aSyncstatus// "@syncStatus"
0x8238  ldc.i4.2
0x8239  box      SyncStatus
0x823e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8243  pop
0x8244  ldc.i4.4
0x8245  stloc.0
0x8246  br.s     loc_825C
0x8248  ldloc.2
0x8249  ldstr    aSyncstatus// "@syncStatus"
0x824e  ldc.i4.0
0x824f  box      SyncStatus
0x8254  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8259  pop
0x825a  ldc.i4.4
0x825b  stloc.0
0x825c  ldloc.1
0x825d  ldstr    aWhereBookabler_3// "WHERE BookableResourceBookingExchangeSy"...
0x8262  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8267  pop
0x8268  ldloc.2
0x8269  ldstr    aBookableresour_2// "@bookableResourceBookingSyncIdMappingId"
0x826e  ldarg.3
0x826f  callvirt instance valuetype [mscorlib]System.Guid SyncData::get_Id()
0x8274  box      [mscorlib]System.Guid
0x8279  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x827e  pop
0x827f  ldarg.2
0x8280  ldloc.1
0x8281  callvirt instance string [mscorlib]System.Object::ToString()
0x8286  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x828b  ldarg.0
0x828c  ldarg.1
0x828d  ldarg.2
0x828e  ldloc.0
0x828f  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x8294  pop
0x8295  ldarg.0
0x8296  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x829b  ldstr    aMethodupdatesy// "MethodUpdateSyncIdMapping"
0x82a0  callvirt instance void Metrics::StopTimer(string name)
0x82a5  ret
```
