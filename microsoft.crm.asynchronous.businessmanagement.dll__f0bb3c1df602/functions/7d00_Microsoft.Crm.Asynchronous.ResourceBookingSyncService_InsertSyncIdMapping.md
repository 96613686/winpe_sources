# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::InsertSyncIdMapping

- ea: `0x7d00`
- end: `0x8042`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::InsertSyncIdMapping`
- size: `834`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e20`
- `0x7c10`

## callees

- `0x7d00`
- `0x8840`
- `0x15820`
- `0x15860`
- `0x15880`
- `0x158a0`
- `0x15a00`
- `0x15a20`
- `0x15b10`
- `0x15b30`
- `0x160d0`
- `0x16260`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x7d60`: `ExchangeEntryId, UserId, SyncVersionNumber, SyncStatus, Retries, IsDeletedInExchange, LastSyncErrorCode, LastSyncError, LastSyncErrorOccurredOn,`
- `0x7d6d`: `OwnerId, OwnerIdType, OwningBusinessUnit, CreatedOn, ModifiedOn)`
- `0x7d87`: `@synchronizedVersionNumber, @syncStatus, @retryCount, @deleteInExchange, @lastSyncErrorCode, @lastSyncError, @lastSyncErrorOccurredOn,`
- `0x7d94`: `@ownerId, @ownerIdType, @owningBusinessUnit, @createdOn, @modifiedOn)`
- `0x7df8`: `@deleteInExchange`
- `0x7e62`: `@createdOn`

## pseudocode

```c

```

## disassembly

```asm
0x7d00  ldarg.0
0x7d01  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7d06  ldstr    aMethodinsertsy// "MethodInsertSyncIdMapping"
0x7d0b  callvirt instance void Metrics::StartTimer(string name)
0x7d10  ldarg.0
0x7d11  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7d16  ldstr    aMethodinsertsy_0// "MethodInsertSyncIdMappingCallCount"
0x7d1b  ldc.i4.1
0x7d1c  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x7d21  pop
0x7d22  ldarg.1
0x7d23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x7d28  stloc.0
0x7d29  ldarg.1
0x7d2a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7d2f  stloc.1
0x7d30  call     valuetype [mscorlib]System.DateTime Utils::RoundDateTimeUtcNow()
0x7d35  stloc.3
0x7d36  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7d3b  stloc.s  4
0x7d3d  ldloc.1
0x7d3e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7d43  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7d48  stloc.s  5
0x7d4a  ldloc.s  5
0x7d4c  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x7d51  ldloc.s  4
0x7d53  ldstr    aInsertIntoBook// "INSERT INTO BookableResourceBookingExch"...
0x7d58  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d5d  pop
0x7d5e  ldloc.s  4
0x7d60  ldstr    aExchangeentryi_1// "ExchangeEntryId, UserId, SyncVersionNum"...
0x7d65  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d6a  pop
0x7d6b  ldloc.s  4
0x7d6d  ldstr    aOwneridOwnerid// "OwnerId, OwnerIdType, OwningBusinessUni"...
0x7d72  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d77  pop
0x7d78  ldloc.s  4
0x7d7a  ldstr    aValuesNewidBoo// "VALUES (NEWID(), @bookableResourceBooki"...
0x7d7f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d84  pop
0x7d85  ldloc.s  4
0x7d87  ldstr    aSynchronizedve// "@synchronizedVersionNumber, @syncStatus"...
0x7d8c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d91  pop
0x7d92  ldloc.s  4
0x7d94  ldstr    aOwneridOwnerid_0// "@ownerId, @ownerIdType, @owningBusiness"...
0x7d99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7d9e  pop
0x7d9f  ldloc.s  5
0x7da1  ldstr    aBookableresour_0// "@bookableResourceBookingId"
0x7da6  ldarg.3
0x7da7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity SyncData::get_ResourceBooking()
0x7dac  ldstr    aBookableresour_1// "bookableresourcebookingid"
0x7db1  callvirt T0x2B000010
0x7db6  box      [mscorlib]System.Guid
0x7dbb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7dc0  pop
0x7dc1  ldloc.s  5
0x7dc3  ldstr    aSystemuserid// "@systemUserId"
0x7dc8  ldarg.2
0x7dc9  callvirt instance valuetype [mscorlib]System.Guid SyncDataCollection::get_UserId()
0x7dce  stloc.s  6
0x7dd0  ldloca.s 6
0x7dd2  constrained. [mscorlib]System.Guid
0x7dd8  callvirt instance string [mscorlib]System.Object::ToString()
0x7ddd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7de2  pop
0x7de3  ldloc.s  5
0x7de5  ldstr    aRetrycount// "@retryCount"
0x7dea  ldc.i4.0
0x7deb  box      [mscorlib]System.Int32
0x7df0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7df5  pop
0x7df6  ldloc.s  5
0x7df8  ldstr    aDeleteinexchan_1// "@deleteInExchange"
0x7dfd  ldc.i4.0
0x7dfe  box      [mscorlib]System.Int32
0x7e03  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e08  pop
0x7e09  ldloc.s  5
0x7e0b  ldstr    aOwnerid_1// "@ownerId"
0x7e10  ldarg.2
0x7e11  callvirt instance valuetype [mscorlib]System.Guid SyncDataCollection::get_UserId()
0x7e16  stloc.s  6
0x7e18  ldloca.s 6
0x7e1a  constrained. [mscorlib]System.Guid
0x7e20  callvirt instance string [mscorlib]System.Object::ToString()
0x7e25  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e2a  pop
0x7e2b  ldloc.s  5
0x7e2d  ldstr    aOwneridtype_0// "@ownerIdType"
0x7e32  ldc.i4.8
0x7e33  box      [mscorlib]System.Int32
0x7e38  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e3d  pop
0x7e3e  ldloc.s  5
0x7e40  ldstr    aOwningbusiness// "@owningBusinessUnit"
0x7e45  ldarg.2
0x7e46  callvirt instance valuetype [mscorlib]System.Guid SyncDataCollection::get_BusinessUnitId()
0x7e4b  stloc.s  6
0x7e4d  ldloca.s 6
0x7e4f  constrained. [mscorlib]System.Guid
0x7e55  callvirt instance string [mscorlib]System.Object::ToString()
0x7e5a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e5f  pop
0x7e60  ldloc.s  5
0x7e62  ldstr    aCreatedon_0// "@createdOn"
0x7e67  ldloc.3
0x7e68  box      [mscorlib]System.DateTime
0x7e6d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e72  pop
0x7e73  ldloc.s  5
0x7e75  ldstr    aModifiedon_1// "@modifiedOn"
0x7e7a  ldloc.3
0x7e7b  box      [mscorlib]System.DateTime
0x7e80  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7e85  pop
0x7e86  ldarg.3
0x7e87  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7e8c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x7e91  stloc.s  7
0x7e93  ldc.i4.0
0x7e94  stloc.s  8
0x7e96  ldloca.s 7
0x7e98  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x7e9d  ldloc.s  8
0x7e9f  beq.s    loc_7EA4
0x7ea1  ldc.i4.0
0x7ea2  br.s     loc_7EAB
0x7ea4  ldloca.s 7
0x7ea6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x7eab  brfalse  loc_7F4A
0x7eb0  ldloc.s  5
0x7eb2  ldstr    aLastsyncerrorc_0// "@lastSyncErrorCode"
0x7eb7  ldarg.3
0x7eb8  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7ebd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> SyncResult::get_ErrorCode()
0x7ec2  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>
0x7ec7  dup
0x7ec8  brtrue.s loc_7ED0
0x7eca  pop
0x7ecb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7ed0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7ed5  pop
0x7ed6  ldloc.s  5
0x7ed8  ldstr    aLastsyncerror// "@lastSyncError"
0x7edd  ldarg.3
0x7ede  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7ee3  callvirt instance string SyncResult::get_ErrorMessage()
0x7ee8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7eed  pop
0x7eee  ldloc.s  5
0x7ef0  ldstr    aLastsyncerroro_0// "@lastSyncErrorOccurredOn"
0x7ef5  ldarg.3
0x7ef6  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7efb  callvirt instance valuetype [mscorlib]System.DateTime SyncResult::get_Date()
0x7f00  box      [mscorlib]System.DateTime
0x7f05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f0a  pop
0x7f0b  ldloc.s  5
0x7f0d  ldstr    aExchangeid// "@exchangeId"
0x7f12  ldsfld   string [mscorlib]System.String::Empty
0x7f17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f1c  pop
0x7f1d  ldloc.s  5
0x7f1f  ldstr    aSynchronizedve_0// "@synchronizedVersionNumber"
0x7f24  ldc.i4.0
0x7f25  box      [mscorlib]System.Int32
0x7f2a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f2f  pop
0x7f30  ldloc.s  5
0x7f32  ldstr    aSyncstatus// "@syncStatus"
0x7f37  ldc.i4.1
0x7f38  box      SyncStatus
0x7f3d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f42  pop
0x7f43  ldc.i4.2
0x7f44  stloc.2
0x7f45  br       loc_8004
0x7f4a  ldloc.s  5
0x7f4c  ldstr    aLastsyncerrorc_0// "@lastSyncErrorCode"
0x7f51  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7f56  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f5b  pop
0x7f5c  ldloc.s  5
0x7f5e  ldstr    aLastsyncerror// "@lastSyncError"
0x7f63  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7f68  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f6d  pop
0x7f6e  ldloc.s  5
0x7f70  ldstr    aLastsyncerroro_0// "@lastSyncErrorOccurredOn"
0x7f75  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7f7a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7f7f  pop
0x7f80  ldloc.s  5
0x7f82  ldstr    aSynchronizedve_0// "@synchronizedVersionNumber"
0x7f87  ldarg.3
0x7f88  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity SyncData::get_ResourceBooking()
0x7f8d  ldstr    aVersionnumber// "versionnumber"
0x7f92  callvirt T0x2B000019
0x7f97  box      [mscorlib]System.Int64
0x7f9c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7fa1  pop
0x7fa2  ldloc.s  5
0x7fa4  ldstr    aExchangeid// "@exchangeId"
0x7fa9  ldarg.s  4
0x7fab  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7fb0  pop
0x7fb1  ldarg.3
0x7fb2  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7fb7  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x7fbc  stloc.s  7
0x7fbe  ldc.i4.3
0x7fbf  stloc.s  8
0x7fc1  ldloca.s 7
0x7fc3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x7fc8  ldloc.s  8
0x7fca  beq.s    loc_7FCF
0x7fcc  ldc.i4.0
0x7fcd  br.s     loc_7FD6
0x7fcf  ldloca.s 7
0x7fd1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x7fd6  brfalse.s loc_7FEF
0x7fd8  ldloc.s  5
0x7fda  ldstr    aSyncstatus// "@syncStatus"
0x7fdf  ldc.i4.2
0x7fe0  box      SyncStatus
0x7fe5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7fea  pop
0x7feb  ldc.i4.0
0x7fec  stloc.2
0x7fed  br.s     loc_8004
0x7fef  ldloc.s  5
0x7ff1  ldstr    aSyncstatus// "@syncStatus"
0x7ff6  ldc.i4.0
0x7ff7  box      SyncStatus
0x7ffc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8001  pop
0x8002  ldc.i4.1
0x8003  stloc.2
0x8004  ldloc.1
0x8005  ldloc.s  4
0x8007  callvirt instance string [mscorlib]System.Object::ToString()
0x800c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8011  ldarg.0
0x8012  ldloc.0
0x8013  ldloc.1
0x8014  ldloc.2
0x8015  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x801a  pop
0x801b  leave.s  loc_8031
0x801d  ldloc.1
0x801e  brfalse.s loc_8026
0x8020  ldloc.1
0x8021  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8026  endfinally
0x8027  ldloc.0
0x8028  brfalse.s loc_8030
0x802a  ldloc.0
0x802b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8030  endfinally
0x8031  ldarg.0
0x8032  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8037  ldstr    aMethodinsertsy// "MethodInsertSyncIdMapping"
0x803c  callvirt instance void Metrics::StopTimer(string name)
0x8041  ret
```
