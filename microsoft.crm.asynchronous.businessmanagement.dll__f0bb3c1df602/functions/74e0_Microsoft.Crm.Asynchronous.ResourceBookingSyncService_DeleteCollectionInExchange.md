# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteCollectionInExchange

- ea: `0x74e0`
- end: `0x75f8`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteCollectionInExchange`
- size: `280`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x67f0`
- `0x6900`
- `0x6b70`

## callees

- `0x74e0`
- `0x7600`
- `0x7ae0`
- `0x8780`
- `0x13f60`
- `0x15720`
- `0x157a0`
- `0x157e0`
- `0x15e00`
- `0x15e10`
- `0x16260`
- `0x16390`
- `0x163e0`
- `0x16480`
- `0x16550`

## string_xrefs

- `0x74e6`: `MethodDeleteCollectionInExchange`
- `0x75ed`: `MethodDeleteCollectionInExchange`
- `0x74f6`: `MethodDeleteCollectionInExchangeCallCount`

## pseudocode

```c

```

## disassembly

```asm
0x74e0  ldarg.0
0x74e1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x74e6  ldstr    aMethoddeleteco// "MethodDeleteCollectionInExchange"
0x74eb  callvirt instance void Metrics::StartTimer(string name)
0x74f0  ldarg.0
0x74f1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x74f6  ldstr    aMethoddeleteco_0// "MethodDeleteCollectionInExchangeCallCou"...
0x74fb  ldc.i4.1
0x74fc  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x7501  pop
0x7502  ldarg.0
0x7503  ldarg.1
0x7504  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7509  ldarg.2
0x750a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> SyncDeleteCollection::get_DeleteMappingIds()
0x750f  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> deleteIdMappings)
0x7514  ldarg.3
0x7515  brfalse.s loc_7521
0x7517  call     bool RunTimeControl::get_IsExpired()
0x751c  brtrue   loc_75CC
0x7521  ldarg.2
0x7522  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data> SyncDeleteCollection::get_DeleteAppointmentsByUserId()
0x7527  stloc.0
0x7528  ldc.i4.0
0x7529  stloc.1
0x752a  ldloc.0
0x752b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data>::get_Keys()
0x7530  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class Data>::GetEnumerator()
0x7535  stloc.2
0x7536  br.s     loc_75B0
0x7538  ldloca.s 2
0x753a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Data>::get_Current()
0x753f  stloc.3
0x7540  ldnull
0x7541  stloc.s  4
0x7543  ldloc.0
0x7544  ldloc.3
0x7545  ldloca.s 4
0x7547  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data>::TryGetValue(var<u1>, !!T0)
0x754c  pop
0x754d  ldarg.0
0x754e  ldarg.1
0x754f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7554  ldarg.0
0x7555  ldarg.1
0x7556  callvirt instance class BookableResourceCache SyncConfig::get_BookableResourceCache()
0x755b  ldloc.3
0x755c  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetExchangeService(class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.Guid userId)
0x7561  ldloc.3
0x7562  ldloc.s  4
0x7564  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchange(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService exchangeService, valuetype [mscorlib]System.Guid userId, class Data deletionData)
0x7569  ldloc.1
0x756a  ldc.i4.1
0x756b  add
0x756c  stloc.1
0x756d  ldarg.0
0x756e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7573  ldstr    aUsers// "Users"
0x7578  ldloc.3
0x7579  box      [mscorlib]System.Guid
0x757e  callvirt instance void Metrics::AddToSet(string name, object value)
0x7583  ldarg.3
0x7584  brfalse.s loc_75B0
0x7586  call     bool RunTimeControl::get_IsExpired()
0x758b  brfalse.s loc_75B0
0x758d  ldarg.0
0x758e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7593  ldstr    aStopped0AfterP// "Stopped {0} after processing {1} users."
0x7598  ldarg.1
0x7599  callvirt instance string SyncConfig::get_Name()
0x759e  ldloc.1
0x759f  box      [mscorlib]System.Int32
0x75a4  call     string [mscorlib]System.String::Format(string, object, object)
0x75a9  callvirt instance void Metrics::RunTimeExpired(string message)
0x75ae  leave.s  loc_75E7
0x75b0  ldloca.s 2
0x75b2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Data>::MoveNext()
0x75b7  brtrue   loc_7538
0x75bc  leave.s  loc_75E7
0x75be  ldloca.s 2
0x75c0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class Data>
0x75c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75cb  endfinally
0x75cc  ldarg.0
0x75cd  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x75d2  ldstr    aStopped0AfterB// "Stopped {0} after batch deleting Id map"...
0x75d7  ldarg.1
0x75d8  callvirt instance string SyncConfig::get_Name()
0x75dd  call     string [mscorlib]System.String::Format(string, object)
0x75e2  callvirt instance void Metrics::RunTimeExpired(string message)
0x75e7  ldarg.0
0x75e8  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x75ed  ldstr    aMethoddeleteco// "MethodDeleteCollectionInExchange"
0x75f2  callvirt instance void Metrics::StopTimer(string name)
0x75f7  ret
```
