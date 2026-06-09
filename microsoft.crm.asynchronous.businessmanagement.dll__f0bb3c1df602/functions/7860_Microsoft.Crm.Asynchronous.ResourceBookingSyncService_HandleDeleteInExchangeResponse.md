# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleDeleteInExchangeResponse

- ea: `0x7860`
- end: `0x7abf`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleDeleteInExchangeResponse`
- size: `607`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x7600`
- `0x7ac0`

## callees

- `0x7860`
- `0x8840`
- `0x15820`
- `0x15860`
- `0x15880`
- `0x158a0`
- `0x160d0`
- `0x16270`
- `0x16390`
- `0x163e0`
- `0x179a0`
- `0x179c0`

## string_xrefs

- `0x7a36`: `DELETE FROM BookableResourceBookingExchangeSyncIdMappingBase`
- `0x7866`: `MethodDeleteInExchange_HandleDeleteAppointmentsResponse`
- `0x7ab4`: `MethodDeleteInExchange_HandleDeleteAppointmentsResponse`
- `0x78be`: `UPDATE BookableResourceBookingExchangeSyncIdMappingBase SET`
- `0x79cd`: `UPDATE BookableResourceBookingExchangeSyncIdMappingBase SET`
- `0x78d6`: `IsDeletedInExchange = 1,`
- `0x79aa`: `NumberOfAppointmentsForDeleteSyncError`
- `0x79f1`: `IsDeletedInExchange = 0,`
- `0x7a49`: `NumberOfAppointmentsForDeleteSyncSuccess`

## pseudocode

```c

```

## disassembly

```asm
0x7860  ldarg.0
0x7861  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7866  ldstr    aMethoddeletein_2// "MethodDeleteInExchange_HandleDeleteAppo"...
0x786b  callvirt instance void Metrics::StartTimer(string name)
0x7870  ldarg.1
0x7871  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x7876  stloc.0
0x7877  ldarg.1
0x7878  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x787d  stloc.1
0x787e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7883  stloc.3
0x7884  ldloc.1
0x7885  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x788a  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x788f  stloc.s  4
0x7891  ldloc.s  4
0x7893  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x7898  ldarg.3
0x7899  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x789e  stloc.s  5
0x78a0  ldc.i4.0
0x78a1  stloc.s  6
0x78a3  ldloca.s 5
0x78a5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x78aa  ldloc.s  6
0x78ac  beq.s    loc_78B1
0x78ae  ldc.i4.0
0x78af  br.s     loc_78B8
0x78b1  ldloca.s 5
0x78b3  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x78b8  brfalse  loc_79BD
0x78bd  ldloc.3
0x78be  ldstr    aUpdateBookable// "UPDATE BookableResourceBookingExchangeS"...
0x78c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78c8  pop
0x78c9  ldloc.3
0x78ca  ldstr    aRetriesRetries// "Retries = Retries + 1,"
0x78cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78d4  pop
0x78d5  ldloc.3
0x78d6  ldstr    aIsdeletedinexc_0// "IsDeletedInExchange = 1,"
0x78db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78e0  pop
0x78e1  ldloc.3
0x78e2  ldstr    aLastsyncerrorc// "LastSyncErrorCode = @lastSyncErrorCode,"
0x78e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78ec  pop
0x78ed  ldloc.3
0x78ee  ldstr    aLastsyncerrorL// "LastSyncError = @lastSyncError,"
0x78f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78f8  pop
0x78f9  ldloc.3
0x78fa  ldstr    aLastsyncerroro// "LastSyncErrorOccurredOn = @lastSyncErro"...
0x78ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7904  pop
0x7905  ldloc.3
0x7906  ldstr    aModifiedonModi// "ModifiedOn = @modifiedOn"
0x790b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7910  pop
0x7911  ldloc.s  4
0x7913  ldstr    aLastsyncerrorc_0// "@lastSyncErrorCode"
0x7918  ldarg.3
0x7919  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> SyncResult::get_ErrorCode()
0x791e  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>
0x7923  dup
0x7924  brtrue.s loc_792C
0x7926  pop
0x7927  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x792c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7931  pop
0x7932  ldloc.s  4
0x7934  ldstr    aLastsyncerror// "@lastSyncError"
0x7939  ldarg.3
0x793a  callvirt instance string SyncResult::get_ErrorMessage()
0x793f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7944  pop
0x7945  ldloc.s  4
0x7947  ldstr    aLastsyncerroro_0// "@lastSyncErrorOccurredOn"
0x794c  ldarg.3
0x794d  callvirt instance valuetype [mscorlib]System.DateTime SyncResult::get_Date()
0x7952  box      [mscorlib]System.DateTime
0x7957  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x795c  pop
0x795d  ldloc.s  4
0x795f  ldstr    aModifiedon_1// "@modifiedOn"
0x7964  call     valuetype [mscorlib]System.DateTime Utils::RoundDateTimeUtcNow()
0x7969  box      [mscorlib]System.DateTime
0x796e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7973  pop
0x7974  ldarg.2
0x7975  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<bool> Data::get_KeepIdMapping()
0x797a  ldarg.s  4
0x797c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<bool>::get_Item(!!T0)
0x7981  brtrue.s loc_79A2
0x7983  ldloc.3
0x7984  ldstr    aSyncstatusSync// ",SyncStatus = @syncStatus"
0x7989  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x798e  pop
0x798f  ldloc.s  4
0x7991  ldstr    aSyncstatus// "@syncStatus"
0x7996  ldc.i4.1
0x7997  box      SyncStatus
0x799c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x79a1  pop
0x79a2  ldc.i4.5
0x79a3  stloc.2
0x79a4  ldarg.0
0x79a5  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x79aa  ldstr    aNumberofappoin_8// "NumberOfAppointmentsForDeleteSyncError"
0x79af  ldc.i4.1
0x79b0  ldc.i4.s 0x32
0x79b2  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x79b7  pop
0x79b8  br       loc_7A57
0x79bd  ldarg.2
0x79be  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<bool> Data::get_KeepIdMapping()
0x79c3  ldarg.s  4
0x79c5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<bool>::get_Item(!!T0)
0x79ca  brfalse.s loc_7A35
0x79cc  ldloc.3
0x79cd  ldstr    aUpdateBookable// "UPDATE BookableResourceBookingExchangeS"...
0x79d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x79d7  pop
0x79d8  ldloc.3
0x79d9  ldstr    aExchangeentryi_0// "ExchangeEntryId = @clearExchangeId,"
0x79de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x79e3  pop
0x79e4  ldloc.3
0x79e5  ldstr    aRetries0// "Retries = 0,"
0x79ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x79ef  pop
0x79f0  ldloc.3
0x79f1  ldstr    aIsdeletedinexc_1// "IsDeletedInExchange = 0,"
0x79f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x79fb  pop
0x79fc  ldloc.3
0x79fd  ldstr    aModifiedonModi// "ModifiedOn = @modifiedOn"
0x7a02  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7a07  pop
0x7a08  ldloc.s  4
0x7a0a  ldstr    aClearexchangei// "@clearExchangeId"
0x7a0f  ldsfld   string [mscorlib]System.String::Empty
0x7a14  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7a19  pop
0x7a1a  ldloc.s  4
0x7a1c  ldstr    aModifiedon_1// "@modifiedOn"
0x7a21  call     valuetype [mscorlib]System.DateTime Utils::RoundDateTimeUtcNow()
0x7a26  box      [mscorlib]System.DateTime
0x7a2b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7a30  pop
0x7a31  ldc.i4.3
0x7a32  stloc.2
0x7a33  br.s     loc_7A43
0x7a35  ldloc.3
0x7a36  ldstr    aDeleteFromBook// "DELETE FROM BookableResourceBookingExch"...
0x7a3b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7a40  pop
0x7a41  ldc.i4.6
0x7a42  stloc.2
0x7a43  ldarg.0
0x7a44  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7a49  ldstr    aNumberofappoin_9// "NumberOfAppointmentsForDeleteSyncSucces"...
0x7a4e  ldc.i4.1
0x7a4f  ldc.i4.s 0x32
0x7a51  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x7a56  pop
0x7a57  ldloc.3
0x7a58  ldstr    aWhereExchangee// "WHERE ExchangeEntryId = @exchangeId"
0x7a5d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7a62  pop
0x7a63  ldloc.s  4
0x7a65  ldstr    aExchangeid// "@exchangeId"
0x7a6a  ldarg.2
0x7a6b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> Data::get_ItemIds()
0x7a70  ldarg.s  4
0x7a72  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>::get_Item(!!T0)
0x7a77  callvirt instance string [mscorlib]System.Object::ToString()
0x7a7c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7a81  pop
0x7a82  ldloc.1
0x7a83  ldloc.3
0x7a84  callvirt instance string [mscorlib]System.Object::ToString()
0x7a89  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7a8e  ldarg.0
0x7a8f  ldloc.0
0x7a90  ldloc.1
0x7a91  ldloc.2
0x7a92  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x7a97  pop
0x7a98  leave.s  loc_7AAE
0x7a9a  ldloc.1
0x7a9b  brfalse.s loc_7AA3
0x7a9d  ldloc.1
0x7a9e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7aa3  endfinally
0x7aa4  ldloc.0
0x7aa5  brfalse.s loc_7AAD
0x7aa7  ldloc.0
0x7aa8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7aad  endfinally
0x7aae  ldarg.0
0x7aaf  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7ab4  ldstr    aMethoddeletein_2// "MethodDeleteInExchange_HandleDeleteAppo"...
0x7ab9  callvirt instance void Metrics::StopTimer(string name)
0x7abe  ret
```
