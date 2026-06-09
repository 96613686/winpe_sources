# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncDeletedResourceBookings

- ea: `0x67f0`
- end: `0x68f8`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncDeletedResourceBookings`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b40`

## callees

- `0x67f0`
- `0x74e0`
- `0x8600`
- `0x8ab0`
- `0x13d00`
- `0x152a0`
- `0x15720`
- `0x15740`
- `0x157f0`
- `0x15e20`
- `0x15ea0`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x67f6`: `MethodSyncDeletedResourceBookings`
- `0x68ed`: `MethodSyncDeletedResourceBookings`

## pseudocode

```c

```

## disassembly

```asm
0x67f0  ldarg.0
0x67f1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x67f6  ldstr    aMethodsyncdele// "MethodSyncDeletedResourceBookings"
0x67fb  callvirt instance void Metrics::StartTimer(string name)
0x6800  newobj   instance void SyncDeleteCollection::.ctor()
0x6805  stloc.0
0x6806  ldarg.1
0x6807  callvirt instance class BookableResourceCache SyncConfig::get_BookableResourceCache()
0x680c  callvirt instance int64 BookableResourceCache::get_MinSyncVersionNumber()
0x6811  stloc.1
0x6812  ldarg.0
0x6813  ldloc.0
0x6814  ldloc.1
0x6815  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RetrieveDeletedResourceBookings(class SyncDeleteCollection syncDeleteCollection, int64 minVersionNumber)
0x681a  ldarg.1
0x681b  callvirt instance class IEntityQuery SyncConfig::get_Query()
0x6820  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> IEntityQuery::Next()
0x6825  stloc.2
0x6826  br.s     loc_68A1
0x6828  ldloc.2
0x6829  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x682e  stloc.3
0x682f  br.s     loc_6881
0x6831  ldloc.3
0x6832  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x6837  dup
0x6838  ldstr    aUserid// "userid"
0x683d  callvirt T0x2B000010
0x6842  stloc.s  4
0x6844  dup
0x6845  ldstr    aExchangeentryi// "exchangeentryid"
0x684a  callvirt T0x2B000011
0x684f  stloc.s  5
0x6851  dup
0x6852  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x6857  callvirt T0x2B000010
0x685c  stloc.s  6
0x685e  ldstr    aSyncstatus_0// "syncstatus"
0x6863  callvirt T0x2B000012
0x6868  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x686d  stloc.s  7
0x686f  ldloc.0
0x6870  ldloc.s  4
0x6872  ldloc.s  5
0x6874  ldloc.s  7
0x6876  ldc.i4.2
0x6877  ceq
0x6879  ldloc.s  6
0x687b  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x6880  pop
0x6881  ldloc.3
0x6882  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6887  brtrue.s loc_6831
0x6889  leave.s  loc_6895
0x688b  ldloc.3
0x688c  brfalse.s loc_6894
0x688e  ldloc.3
0x688f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6894  endfinally
0x6895  ldarg.1
0x6896  callvirt instance class IEntityQuery SyncConfig::get_Query()
0x689b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> IEntityQuery::Next()
0x68a0  stloc.2
0x68a1  ldloc.2
0x68a2  brtrue.s loc_6828
0x68a4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x68a9  ldc.i4.0
0x68aa  ldc.i4.0
0x68ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x68b0  stloc.s  8
0x68b2  ldloc.s  8
0x68b4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x68b9  ldarg.1
0x68ba  ldloc.s  8
0x68bc  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x68c1  ldarg.0
0x68c2  ldarg.1
0x68c3  ldloc.0
0x68c4  ldc.i4.1
0x68c5  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteCollectionInExchange(class SyncConfig syncConfig, class SyncDeleteCollection syncDeleteCollection, bool runTimeControlEnabled)
0x68ca  leave.s  loc_68E7
0x68cc  ldloc.s  8
0x68ce  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x68d3  ldarg.1
0x68d4  ldnull
0x68d5  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x68da  endfinally
0x68db  ldloc.s  8
0x68dd  brfalse.s loc_68E6
0x68df  ldloc.s  8
0x68e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68e6  endfinally
0x68e7  ldarg.0
0x68e8  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x68ed  ldstr    aMethodsyncdele// "MethodSyncDeletedResourceBookings"
0x68f2  callvirt instance void Metrics::StopTimer(string name)
0x68f7  ret
```
