# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateInExchange

- ea: `0x6ba0`
- end: `0x6e1e`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateInExchange`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x6ba0`
- `0x6e20`
- `0x6f50`
- `0x13db0`
- `0x158d0`
- `0x158e0`
- `0x15b50`
- `0x15b70`
- `0x15b90`
- `0x16260`
- `0x16390`
- `0x163e0`
- `0x16540`

## string_xrefs

- `0x6ba8`: `MethodCreateInExchange`
- `0x6e12`: `MethodCreateInExchange`
- `0x6be5`: `NumberOfUsersForCreateSync`
- `0x6bf7`: `NumberOfAppointmentsForCreateSync`
- `0x6c13`: `MethodCreateInExchange_PrepareBatch`
- `0x6c46`: `MethodCreateInExchange_PrepareBatch`
- `0x6c5c`: `MethodCreateInExchange_PrepareBatch`
- `0x6c99`: `MethodCreateInExchange_PrepareBatch`
- `0x6d7e`: `MethodCreateInExchange_PrepareBatch`
- `0x6da4`: `MethodCreateInExchange_PrepareBatch`
- `0x6ca9`: `MethodCreateInExchange_CreateAppointments`
- `0x6cd8`: `MethodCreateInExchange_CreateAppointments`
- `0x6d46`: `CreateInExchange error in batch processing: {0}`
- `0x6dbb`: `NumberOfBatchesForCreateSync`
- `0x6dd2`: `CreateInExchange error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldc.i4.0
0x6ba1  stloc.0
0x6ba2  ldarg.0
0x6ba3  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6ba8  ldstr    aMethodcreatein// "MethodCreateInExchange"
0x6bad  callvirt instance void Metrics::StartTimer(string name)
0x6bb2  ldarg.2
0x6bb3  brfalse  loc_6DC8
0x6bb8  ldarg.2
0x6bb9  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6bbe  brfalse  loc_6DC8
0x6bc3  ldarg.2
0x6bc4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6bc9  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Count()
0x6bce  ldc.i4.0
0x6bcf  ble      loc_6DC8
0x6bd4  ldarg.2
0x6bd5  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x6bda  brfalse  loc_6DC8
0x6bdf  ldarg.0
0x6be0  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6be5  ldstr    aNumberofusersf// "NumberOfUsersForCreateSync"
0x6bea  ldc.i4.1
0x6beb  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6bf0  pop
0x6bf1  ldarg.0
0x6bf2  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6bf7  ldstr    aNumberofappoin// "NumberOfAppointmentsForCreateSync"
0x6bfc  ldarg.2
0x6bfd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6c02  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Count()
0x6c07  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6c0c  pop
0x6c0d  ldarg.0
0x6c0e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6c13  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6c18  callvirt instance void Metrics::StartTimer(string name)
0x6c1d  ldarg.2
0x6c1e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6c23  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Count()
0x6c28  stloc.1
0x6c29  ldc.i4.0
0x6c2a  stloc.2
0x6c2b  ldarg.0
0x6c2c  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6c31  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x6c36  ldloc.1
0x6c37  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x6c3c  stloc.3
0x6c3d  ldc.i4.0
0x6c3e  stloc.s  4
0x6c40  ldarg.0
0x6c41  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6c46  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6c4b  callvirt instance void Metrics::StopTimer(string name)
0x6c50  br       loc_6DAE
0x6c55  nop
0x6c56  ldarg.0
0x6c57  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6c5c  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6c61  callvirt instance void Metrics::StartTimer(string name)
0x6c66  ldloc.s  4
0x6c68  ldc.i4.1
0x6c69  add
0x6c6a  stloc.s  4
0x6c6c  ldloc.3
0x6c6d  stloc.2
0x6c6e  ldloc.s  4
0x6c70  ldc.i4.1
0x6c71  sub
0x6c72  ldarg.0
0x6c73  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6c78  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x6c7d  mul
0x6c7e  stloc.0
0x6c7f  ldarg.2
0x6c80  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6c85  ldloc.0
0x6c86  call     T0x2B000015
0x6c8b  ldloc.3
0x6c8c  call     T0x2B000016
0x6c91  stloc.s  5
0x6c93  ldarg.0
0x6c94  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6c99  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6c9e  callvirt instance void Metrics::StopTimer(string name)
0x6ca3  ldarg.0
0x6ca4  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6ca9  ldstr    aMethodcreatein_1// "MethodCreateInExchange_CreateAppointmen"...
0x6cae  callvirt instance void Metrics::StartTimer(string name)
0x6cb3  ldarg.2
0x6cb4  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x6cb9  ldloc.s  5
0x6cbb  ldc.i4.0
0x6cbc  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::op_Implicit(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x6cc1  ldc.i4.0
0x6cc2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>::.ctor(var<u1>)
0x6cc7  ldc.i4.0
0x6cc8  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsMode>::.ctor(var<u1>)
0x6ccd  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::CreateItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsMode>)
0x6cd2  ldarg.0
0x6cd3  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6cd8  ldstr    aMethodcreatein_1// "MethodCreateInExchange_CreateAppointmen"...
0x6cdd  callvirt instance void Metrics::StopTimer(string name)
0x6ce2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse>::GetEnumerator()
0x6ce7  stloc.s  6
0x6ce9  br.s     loc_6D25
0x6ceb  ldloc.s  6
0x6ced  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse>::get_Current()
0x6cf2  stloc.s  7
0x6cf4  ldarg.0
0x6cf5  ldarg.1
0x6cf6  ldarg.2
0x6cf7  ldloc.s  7
0x6cf9  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_Result()
0x6cfe  ldc.i4.0
0x6cff  ldloc.s  7
0x6d01  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorCode()
0x6d06  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>::.ctor(var<u1>)
0x6d0b  ldloc.s  7
0x6d0d  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorMessage()
0x6d12  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> errorCode, string errorMessage)
0x6d17  ldloc.0
0x6d18  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleCreateInExchangeResponse(class SyncConfig syncConfig, class SyncDataCollection collection, class SyncResult syncResult, int32 index)
0x6d1d  ldloc.0
0x6d1e  ldc.i4.1
0x6d1f  add
0x6d20  stloc.0
0x6d21  ldloc.2
0x6d22  ldc.i4.1
0x6d23  sub
0x6d24  stloc.2
0x6d25  ldloc.s  6
0x6d27  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6d2c  brtrue.s loc_6CEB
0x6d2e  leave.s  loc_6D3C
0x6d30  ldloc.s  6
0x6d32  brfalse.s loc_6D3B
0x6d34  ldloc.s  6
0x6d36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d3b  endfinally
0x6d3c  leave.s  loc_6D78
0x6d3e  stloc.s  8
0x6d40  ldarg.0
0x6d41  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6d46  ldstr    aCreateinexchan// "CreateInExchange error in batch process"...
0x6d4b  ldloc.s  8
0x6d4d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d52  call     string [mscorlib]System.String::Format(string, object)
0x6d57  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x6d5c  ldarg.0
0x6d5d  ldarg.1
0x6d5e  ldarg.2
0x6d5f  ldc.i4.2
0x6d60  ldc.i4.1
0x6d61  ldloc.s  8
0x6d63  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d68  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x6d6d  ldloc.0
0x6d6e  ldloc.0
0x6d6f  ldloc.2
0x6d70  add
0x6d71  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkCreateInExchangeRequestsAsFailed(class SyncConfig syncConfig, class SyncDataCollection collection, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x6d76  leave.s  loc_6D78
0x6d78  ldarg.0
0x6d79  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6d7e  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6d83  callvirt instance void Metrics::StartTimer(string name)
0x6d88  ldloc.1
0x6d89  ldloc.3
0x6d8a  sub
0x6d8b  stloc.1
0x6d8c  ldarg.0
0x6d8d  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6d92  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x6d97  ldloc.1
0x6d98  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x6d9d  stloc.3
0x6d9e  ldarg.0
0x6d9f  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6da4  ldstr    aMethodcreatein_0// "MethodCreateInExchange_PrepareBatch"
0x6da9  callvirt instance void Metrics::StopTimer(string name)
0x6dae  ldloc.3
0x6daf  ldc.i4.0
0x6db0  bgt      loc_6C55
0x6db5  ldarg.0
0x6db6  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6dbb  ldstr    aNumberofbatche// "NumberOfBatchesForCreateSync"
0x6dc0  ldloc.s  4
0x6dc2  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6dc7  pop
0x6dc8  leave.s  loc_6E1D
0x6dca  stloc.s  9
0x6dcc  ldarg.0
0x6dcd  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6dd2  ldstr    aCreateinexchan_0// "CreateInExchange error: {0}"
0x6dd7  ldloc.s  9
0x6dd9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6dde  call     string [mscorlib]System.String::Format(string, object)
0x6de3  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x6de8  ldarg.0
0x6de9  ldarg.1
0x6dea  ldarg.2
0x6deb  ldc.i4.2
0x6dec  ldc.i4.2
0x6ded  ldloc.s  9
0x6def  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6df4  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x6df9  ldloc.0
0x6dfa  ldarg.2
0x6dfb  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_CreateSyncData()
0x6e00  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Count()
0x6e05  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkCreateInExchangeRequestsAsFailed(class SyncConfig syncConfig, class SyncDataCollection collection, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x6e0a  leave.s  loc_6E1D
0x6e0c  ldarg.0
0x6e0d  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6e12  ldstr    aMethodcreatein// "MethodCreateInExchange"
0x6e17  callvirt instance void Metrics::StopTimer(string name)
0x6e1c  endfinally
0x6e1d  ret
```
