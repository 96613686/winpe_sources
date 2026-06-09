# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchange

- ea: `0x7600`
- end: `0x7860`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchange`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x74e0`

## callees

- `0x7600`
- `0x7860`
- `0x7ac0`
- `0x13db0`
- `0x158d0`
- `0x158e0`
- `0x16260`
- `0x16390`
- `0x163e0`
- `0x16540`
- `0x179a0`
- `0x179e0`

## string_xrefs

- `0x7608`: `MethodDeleteInExchange`
- `0x7854`: `MethodDeleteInExchange`
- `0x7632`: `NumberOfUsersForDeleteSync`
- `0x7644`: `NumberOfAppointmentsForDeleteSync`
- `0x765c`: `MethodDeleteInExchange_PrepareBatch`
- `0x7693`: `MethodDeleteInExchange_PrepareBatch`
- `0x76a9`: `MethodDeleteInExchange_PrepareBatch`
- `0x76e3`: `MethodDeleteInExchange_PrepareBatch`
- `0x77c0`: `MethodDeleteInExchange_PrepareBatch`
- `0x77e8`: `MethodDeleteInExchange_PrepareBatch`
- `0x76f3`: `MethodDeleteInExchange_DeleteAppointments`
- `0x7718`: `MethodDeleteInExchange_DeleteAppointments`
- `0x7787`: `DeleteInExchange error in batch processing: {0}`
- `0x7800`: `NumberOfBatchesForDeleteSync`
- `0x7817`: `DeleteInExchange error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7600  ldc.i4.0
0x7601  stloc.0
0x7602  ldarg.0
0x7603  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7608  ldstr    aMethoddeletein// "MethodDeleteInExchange"
0x760d  callvirt instance void Metrics::StartTimer(string name)
0x7612  ldarg.s  4
0x7614  brfalse  loc_780D
0x7619  ldarg.s  4
0x761b  callvirt instance int32 Data::get_Count()
0x7620  ldc.i4.0
0x7621  ble      loc_780D
0x7626  ldarg.2
0x7627  brfalse  loc_780D
0x762c  ldarg.0
0x762d  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7632  ldstr    aNumberofusersf_1// "NumberOfUsersForDeleteSync"
0x7637  ldc.i4.1
0x7638  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x763d  pop
0x763e  ldarg.0
0x763f  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7644  ldstr    aNumberofappoin_7// "NumberOfAppointmentsForDeleteSync"
0x7649  ldarg.s  4
0x764b  callvirt instance int32 Data::get_Count()
0x7650  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x7655  pop
0x7656  ldarg.0
0x7657  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x765c  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x7661  callvirt instance void Metrics::StartTimer(string name)
0x7666  ldarg.s  4
0x7668  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId> Data::get_ItemIds()
0x766d  stloc.1
0x766e  ldloc.1
0x766f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>::get_Count()
0x7674  stloc.2
0x7675  ldc.i4.0
0x7676  stloc.3
0x7677  ldarg.0
0x7678  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x767d  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x7682  ldloc.2
0x7683  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x7688  stloc.s  4
0x768a  ldc.i4.0
0x768b  stloc.s  5
0x768d  ldarg.0
0x768e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7693  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x7698  callvirt instance void Metrics::StopTimer(string name)
0x769d  br       loc_77F2
0x76a2  nop
0x76a3  ldarg.0
0x76a4  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x76a9  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x76ae  callvirt instance void Metrics::StartTimer(string name)
0x76b3  ldloc.s  5
0x76b5  ldc.i4.1
0x76b6  add
0x76b7  stloc.s  5
0x76b9  ldloc.s  4
0x76bb  stloc.3
0x76bc  ldloc.s  5
0x76be  ldc.i4.1
0x76bf  sub
0x76c0  ldarg.0
0x76c1  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x76c6  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x76cb  mul
0x76cc  stloc.0
0x76cd  ldloc.1
0x76ce  ldloc.0
0x76cf  call     T0x2B000017
0x76d4  ldloc.s  4
0x76d6  call     T0x2B000018
0x76db  stloc.s  6
0x76dd  ldarg.0
0x76de  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x76e3  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x76e8  callvirt instance void Metrics::StopTimer(string name)
0x76ed  ldarg.0
0x76ee  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x76f3  ldstr    aMethoddeletein_1// "MethodDeleteInExchange_DeleteAppointmen"...
0x76f8  callvirt instance void Metrics::StartTimer(string name)
0x76fd  ldarg.2
0x76fe  ldloc.s  6
0x7700  ldc.i4.2
0x7701  ldc.i4.2
0x7702  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendCancellationsMode>::.ctor(var<u1>)
0x7707  ldc.i4.0
0x7708  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AffectedTaskOccurrence>::.ctor(var<u1>)
0x770d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::DeleteItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DeleteMode, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendCancellationsMode>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AffectedTaskOccurrence>)
0x7712  ldarg.0
0x7713  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7718  ldstr    aMethoddeletein_1// "MethodDeleteInExchange_DeleteAppointmen"...
0x771d  callvirt instance void Metrics::StopTimer(string name)
0x7722  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse>::GetEnumerator()
0x7727  stloc.s  7
0x7729  br.s     loc_7766
0x772b  ldloc.s  7
0x772d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse>::get_Current()
0x7732  stloc.s  8
0x7734  ldarg.0
0x7735  ldarg.1
0x7736  ldarg.s  4
0x7738  ldloc.s  8
0x773a  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_Result()
0x773f  ldc.i4.0
0x7740  ldloc.s  8
0x7742  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorCode()
0x7747  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError>::.ctor(var<u1>)
0x774c  ldloc.s  8
0x774e  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse::get_ErrorMessage()
0x7753  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError> errorCode, string errorMessage)
0x7758  ldloc.0
0x7759  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleDeleteInExchangeResponse(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class Data deletionData, class SyncResult syncResult, int32 index)
0x775e  ldloc.0
0x775f  ldc.i4.1
0x7760  add
0x7761  stloc.0
0x7762  ldloc.3
0x7763  ldc.i4.1
0x7764  sub
0x7765  stloc.3
0x7766  ldloc.s  7
0x7768  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x776d  brtrue.s loc_772B
0x776f  leave.s  loc_777D
0x7771  ldloc.s  7
0x7773  brfalse.s loc_777C
0x7775  ldloc.s  7
0x7777  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x777c  endfinally
0x777d  leave.s  loc_77BA
0x777f  stloc.s  9
0x7781  ldarg.0
0x7782  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7787  ldstr    aDeleteinexchan// "DeleteInExchange error in batch process"...
0x778c  ldloc.s  9
0x778e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7793  call     string [mscorlib]System.String::Format(string, object)
0x7798  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x779d  ldarg.0
0x779e  ldarg.1
0x779f  ldarg.s  4
0x77a1  ldc.i4.2
0x77a2  ldc.i4.1
0x77a3  ldloc.s  9
0x77a5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x77aa  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x77af  ldloc.0
0x77b0  ldloc.0
0x77b1  ldloc.3
0x77b2  add
0x77b3  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkDeleteInExchangeRequestsAsFailed(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class Data deletionData, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x77b8  leave.s  loc_77BA
0x77ba  ldarg.0
0x77bb  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x77c0  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x77c5  callvirt instance void Metrics::StartTimer(string name)
0x77ca  ldloc.2
0x77cb  ldloc.s  4
0x77cd  sub
0x77ce  stloc.2
0x77cf  ldarg.0
0x77d0  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x77d5  callvirt instance int32 ConfigurationSettings::get_MaxExchangeBatchSize()
0x77da  ldloc.2
0x77db  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x77e0  stloc.s  4
0x77e2  ldarg.0
0x77e3  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x77e8  ldstr    aMethoddeletein_0// "MethodDeleteInExchange_PrepareBatch"
0x77ed  callvirt instance void Metrics::StopTimer(string name)
0x77f2  ldloc.s  4
0x77f4  ldc.i4.0
0x77f5  bgt      loc_76A2
0x77fa  ldarg.0
0x77fb  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7800  ldstr    aNumberofbatche_1// "NumberOfBatchesForDeleteSync"
0x7805  ldloc.s  5
0x7807  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x780c  pop
0x780d  leave.s  loc_785F
0x780f  stloc.s  0xA
0x7811  ldarg.0
0x7812  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7817  ldstr    aDeleteinexchan_0// "DeleteInExchange error: {0}"
0x781c  ldloc.s  0xA
0x781e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7823  call     string [mscorlib]System.String::Format(string, object)
0x7828  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x782d  ldarg.0
0x782e  ldarg.1
0x782f  ldarg.s  4
0x7831  ldc.i4.2
0x7832  ldc.i4.2
0x7833  ldloc.s  0xA
0x7835  callvirt instance string [mscorlib]System.Exception::get_Message()
0x783a  newobj   instance void SyncResult::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResult result, valuetype Level errorLevel, string errorMessage)
0x783f  ldloc.0
0x7840  ldarg.s  4
0x7842  callvirt instance int32 Data::get_Count()
0x7847  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkDeleteInExchangeRequestsAsFailed(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class Data deletionData, class SyncResult syncResult, int32 startIndex, int32 endIndex)
0x784c  leave.s  loc_785F
0x784e  ldarg.0
0x784f  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7854  ldstr    aMethoddeletein// "MethodDeleteInExchange"
0x7859  callvirt instance void Metrics::StopTimer(string name)
0x785e  endfinally
0x785f  ret
```
