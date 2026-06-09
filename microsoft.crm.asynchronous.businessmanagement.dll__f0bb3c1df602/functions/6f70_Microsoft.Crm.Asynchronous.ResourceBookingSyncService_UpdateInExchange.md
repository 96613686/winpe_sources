# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateInExchange

- ea: `0x6f70`
- end: `0x7338`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateInExchange`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x6f70`
- `0x7340`
- `0x73d0`
- `0x74a0`
- `0x74c0`
- `0x13db0`
- `0x158d0`
- `0x158e0`
- `0x15b50`
- `0x15b80`
- `0x15ba0`
- `0x16260`
- `0x16390`
- `0x163e0`
- `0x16540`

## string_xrefs

- `0x6f78`: `MethodUpdateInExchange`
- `0x732c`: `MethodUpdateInExchange`
- `0x6fb5`: `NumberOfUsersForUpdateSync`
- `0x6fc7`: `NumberOfAppointmentsForUpdateSync`
- `0x6fe3`: `MethodUpdateInExchange_PrepareBatch`
- `0x7016`: `MethodUpdateInExchange_PrepareBatch`
- `0x702b`: `MethodUpdateInExchange_PrepareBatch`
- `0x7068`: `MethodUpdateInExchange_PrepareBatch`
- `0x7293`: `MethodUpdateInExchange_PrepareBatch`
- `0x72b9`: `MethodUpdateInExchange_PrepareBatch`
- `0x70bc`: `MethodUpdateInExchange_GetAppointments`
- `0x70db`: `MethodUpdateInExchange_GetAppointments`
- `0x70eb`: `MethodUpdateInExchange_HandleGetAppointmentsResponse`
- `0x715b`: `MethodUpdateInExchange_HandleGetAppointmentsResponse`
- `0x716f`: `UpdateInExchange error in batch bind: {0}`
- `0x71b7`: `MethodUpdateInExchange_UpdateAppointments`
- `0x71e7`: `MethodUpdateInExchange_UpdateAppointments`
- `0x7255`: `UpdateInExchange error in batch update: {0}`
- `0x72d0`: `NumberOfBatchesForUpdateSync`
- `0x72e7`: `UpdateInExchange error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6f70  ldc.i4.0
0x6f71  stloc.0
0x6f72  ldarg.0
0x6f73  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6f78  ldstr    aMethodupdatein// "MethodUpdateInExchange"
0x6f7d  callvirt instance void Metrics::StartTimer(string name)
0x6f82  ldarg.2
0x6f83  brfalse  loc_72DD
0x6f88  ldarg.2
0x6f89  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> SyncDataCollection::get_UpdateAppointments()
0x6f8e  brfalse  loc_72DD
0x6f93  ldarg.2
0x6f94  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> SyncDataCollection::get_UpdateAppointments()
0x6f99  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>::get_Count()
0x6f9e  ldc.i4.0
0x6f9f  ble      loc_72DD
0x6fa4  ldarg.2
0x6fa5  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x6faa  brfalse  loc_72DD
0x6faf  ldarg.0
0x6fb0  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6fb5  ldstr    aNumberofusersf_0// "NumberOfUsersForUpdateSync"
0x6fba  ldc.i4.1
0x6fbb  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6fc0  pop
0x6fc1  ldarg.0
0x6fc2  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6fc7  ldstr    aNumberofappoin_2// "NumberOfAppointmentsForUpdateSync"
0x6fcc  ldarg.2
0x6fcd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> SyncDataCollection::get_UpdateAppointments()
0x6fd2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>::get_Count()
0x6fd7  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6fdc  pop
0x6fdd  ldarg.0
0x6fde  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6fe3  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x6fe8  callvirt instance void Metrics::StartTimer(string name)
0x6fed  ldarg.2
0x6fee  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> SyncDataCollection::get_UpdateAppointments()
0x6ff3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>::get_Count()
0x6ff8  stloc.1
0x6ff9  ldc.i4.0
0x6ffa  stloc.2
0x6ffb  ldarg.0
0x6ffc  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x7001  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x7006  ldloc.1
0x7007  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x700c  stloc.3
0x700d  ldc.i4.0
0x700e  stloc.s  4
0x7010  ldarg.0
0x7011  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7016  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x701b  callvirt instance void Metrics::StopTimer(string name)
0x7020  br       loc_72C3
0x7025  ldarg.0
0x7026  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x702b  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x7030  callvirt instance void Metrics::StartTimer(string name)
0x7035  ldloc.s  4
0x7037  ldc.i4.1
0x7038  add
0x7039  stloc.s  4
0x703b  ldloc.3
0x703c  stloc.2
0x703d  ldloc.s  4
0x703f  ldc.i4.1
0x7040  sub
0x7041  ldarg.0
0x7042  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x7047  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x704c  mul
0x704d  stloc.0
0x704e  ldarg.2
0x704f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> SyncDataCollection::get_UpdateAppointments()
0x7054  ldloc.0
0x7055  call     T0x2B000017
0x705a  ldloc.3
0x705b  call     T0x2B000018
0x7060  stloc.s  5
0x7062  ldarg.0
0x7063  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7068  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x706d  callvirt instance void Metrics::StopTimer(string name)
0x7072  ldc.i4.0
0x7073  ldc.i4.5
0x7074  newarr   [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase
0x7079  dup
0x707a  ldc.i4.0
0x707b  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemSchema::Subject
0x7080  stelem.ref
0x7081  dup
0x7082  ldc.i4.1
0x7083  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AppointmentSchema::Start
0x7088  stelem.ref
0x7089  dup
0x708a  ldc.i4.2
0x708b  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AppointmentSchema::End
0x7090  stelem.ref
0x7091  dup
0x7092  ldc.i4.3
0x7093  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AppointmentSchema::StartTimeZone
0x7098  stelem.ref
0x7099  dup
0x709a  ldc.i4.4
0x709b  ldsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AppointmentSchema::EndTimeZone
0x70a0  stelem.ref
0x70a1  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.BasePropertySet, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertyDefinitionBase[])
0x70a6  stloc.s  6
0x70a8  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::.ctor()
0x70ad  stloc.s  7
0x70af  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::.ctor()
0x70b4  stloc.s  8
0x70b6  ldarg.0
0x70b7  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x70bc  ldstr    aMethodupdatein_1// "MethodUpdateInExchange_GetAppointments"
0x70c1  callvirt instance void Metrics::StartTimer(string name)
0x70c6  ldarg.2
0x70c7  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x70cc  ldloc.s  5
0x70ce  ldloc.s  6
0x70d0  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::BindToItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x70d5  ldarg.0
0x70d6  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x70db  ldstr    aMethodupdatein_1// "MethodUpdateInExchange_GetAppointments"
0x70e0  callvirt instance void Metrics::StopTimer(string name)
0x70e5  ldarg.0
0x70e6  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x70eb  ldstr    aMethodupdatein_2// "MethodUpdateInExchange_HandleGetAppoint"...
0x70f0  callvirt instance void Metrics::StartTimer(string name)
0x70f5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse>::GetEnumerator()
0x70fa  stloc.s  0xA
0x70fc  br.s     loc_713E
0x70fe  ldloc.s  0xA
0x7100  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse>::get_Current()
0x7105  stloc.s  0xB
0x7107  ldarg.0
0x7108  ldarg.1
0x7109  ldarg.2
0x710a  ldloc.s  0xB
0x710c  ldloc.s  7
0x710e  ldloc.s  8
0x7110  ldloc.s  0xB
0x7112  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_Result()
0x7117  ldc.i4.0
0x7118  ldloc.s  0xB
0x711a  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorCode()
0x711f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>::.ctor(var<u1>)
0x7124  ldloc.s  0xB
0x7126  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorMessage()
0x712b  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> errorCode, string errorMessage)
0x7130  ldloc.0
0x7131  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeBindResponse(class SyncConfig syncConfig, class SyncDataCollection collection, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse itemResponse, class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> updateSyncData, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> updateAppointments, class SyncResult syncResult, int32 index)
0x7136  ldloc.0
0x7137  ldc.i4.1
0x7138  add
0x7139  stloc.0
0x713a  ldloc.2
0x713b  ldc.i4.1
0x713c  sub
0x713d  stloc.2
0x713e  ldloc.s  0xA
0x7140  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7145  brtrue.s loc_70FE
0x7147  leave.s  loc_7155
0x7149  ldloc.s  0xA
0x714b  brfalse.s loc_7154
0x714d  ldloc.s  0xA
0x714f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7154  endfinally
0x7155  ldarg.0
0x7156  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x715b  ldstr    aMethodupdatein_2// "MethodUpdateInExchange_HandleGetAppoint"...
0x7160  callvirt instance void Metrics::StopTimer(string name)
0x7165  leave.s  loc_71A1
0x7167  stloc.s  0xC
0x7169  ldarg.0
0x716a  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x716f  ldstr    aUpdateinexchan// "UpdateInExchange error in batch bind: {"...
0x7174  ldloc.s  0xC
0x7176  callvirt instance string [mscorlib]System.Exception::get_Message()
0x717b  call     string [mscorlib]System.String::Format(string, object)
0x7180  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x7185  ldarg.0
0x7186  ldarg.1
0x7187  ldarg.2
0x7188  ldc.i4.2
0x7189  ldc.i4.1
0x718a  ldloc.s  0xC
0x718c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7191  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x7196  ldloc.0
0x7197  ldloc.0
0x7198  ldloc.2
0x7199  add
0x719a  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeBindRequestsAsFailed(class SyncConfig syncConfig, class SyncDataCollection collection, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x719f  leave.s  loc_71A1
0x71a1  ldc.i4.0
0x71a2  stloc.s  9
0x71a4  ldloc.s  8
0x71a6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Count()
0x71ab  ldc.i4.0
0x71ac  ble      loc_724B
0x71b1  ldarg.0
0x71b2  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x71b7  ldstr    aMethodupdatein_3// "MethodUpdateInExchange_UpdateAppointmen"...
0x71bc  callvirt instance void Metrics::StartTimer(string name)
0x71c1  ldarg.2
0x71c2  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x71c7  ldloc.s  8
0x71c9  ldc.i4.0
0x71ca  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::op_Implicit(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName)
0x71cf  ldc.i4.1
0x71d0  ldc.i4.0
0x71d1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>::.ctor(var<u1>)
0x71d6  ldc.i4.0
0x71d7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsOrCancellationsMode>::.ctor(var<u1>)
0x71dc  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::UpdateItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ConflictResolutionMode, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsOrCancellationsMode>)
0x71e1  ldarg.0
0x71e2  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x71e7  ldstr    aMethodupdatein_3// "MethodUpdateInExchange_UpdateAppointmen"...
0x71ec  callvirt instance void Metrics::StopTimer(string name)
0x71f1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::GetEnumerator()
0x71f6  stloc.s  0xD
0x71f8  br.s     loc_7234
0x71fa  ldloc.s  0xD
0x71fc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse>::get_Current()
0x7201  stloc.s  0xE
0x7203  ldarg.0
0x7204  ldarg.1
0x7205  ldloc.s  7
0x7207  ldloc.s  0xE
0x7209  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_Result()
0x720e  ldc.i4.1
0x720f  ldloc.s  0xE
0x7211  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorCode()
0x7216  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>::.ctor(var<u1>)
0x721b  ldloc.s  0xE
0x721d  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorMessage()
0x7222  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> errorCode, string errorMessage)
0x7227  ldloc.s  9
0x7229  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeResponse(class SyncConfig syncConfig, class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> updateSyncData, class SyncResult syncResult, int32 index)
0x722e  ldloc.s  9
0x7230  ldc.i4.1
0x7231  add
0x7232  stloc.s  9
0x7234  ldloc.s  0xD
0x7236  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x723b  brtrue.s loc_71FA
0x723d  leave.s  loc_724B
0x723f  ldloc.s  0xD
0x7241  brfalse.s loc_724A
0x7243  ldloc.s  0xD
0x7245  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724a  endfinally
0x724b  leave.s  loc_728D
0x724d  stloc.s  0xF
0x724f  ldarg.0
0x7250  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7255  ldstr    aUpdateinexchan_0// "UpdateInExchange error in batch update:"...
0x725a  ldloc.s  0xF
0x725c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7261  call     string [mscorlib]System.String::Format(string, object)
0x7266  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x726b  ldarg.0
0x726c  ldarg.1
0x726d  ldloc.s  7
0x726f  ldc.i4.2
0x7270  ldc.i4.1
0x7271  ldloc.s  0xF
0x7273  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7278  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x727d  ldloc.s  9
0x727f  ldloc.s  7
0x7281  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Count()
0x7286  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeRequestsAsFailed(class SyncConfig syncConfig, class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> updateSyncData, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x728b  leave.s  loc_728D
0x728d  ldarg.0
0x728e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7293  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x7298  callvirt instance void Metrics::StartTimer(string name)
0x729d  ldloc.1
0x729e  ldloc.3
0x729f  sub
0x72a0  stloc.1
0x72a1  ldarg.0
0x72a2  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x72a7  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x72ac  ldloc.1
0x72ad  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x72b2  stloc.3
0x72b3  ldarg.0
0x72b4  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x72b9  ldstr    aMethodupdatein_0// "MethodUpdateInExchange_PrepareBatch"
0x72be  callvirt instance void Metrics::StopTimer(string name)
0x72c3  ldloc.3
0x72c4  ldc.i4.0
0x72c5  bgt      loc_7025
0x72ca  ldarg.0
  ... truncated ...
```
