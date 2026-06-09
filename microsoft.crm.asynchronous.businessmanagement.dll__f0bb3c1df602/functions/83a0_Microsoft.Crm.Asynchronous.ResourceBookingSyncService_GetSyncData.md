# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetSyncData

- ea: `0x83a0`
- end: `0x85f6`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetSyncData`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x62c0`

## callees

- `0x83a0`
- `0x8730`
- `0x13d80`
- `0x13da0`
- `0x15780`
- `0x15980`
- `0x15990`
- `0x159a0`
- `0x159b0`
- `0x159c0`
- `0x159d0`
- `0x159e0`
- `0x159f0`
- `0x15ae0`
- `0x15e20`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x847d`: `isdeletedinexchange`

## pseudocode

```c

```

## disassembly

```asm
0x83a0  ldarg.0
0x83a1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x83a6  ldstr    aMethodgetsyncd// "MethodGetSyncData"
0x83ab  callvirt instance void Metrics::StartTimer(string name)
0x83b0  ldnull
0x83b1  stloc.0
0x83b2  ldarg.s  4
0x83b4  brfalse  loc_85E4
0x83b9  ldarg.3
0x83ba  brfalse  loc_85E4
0x83bf  ldarg.s  4
0x83c1  ldstr    aBookableresour_1// "bookableresourcebookingid"
0x83c6  callvirt T0x2B000010
0x83cb  stloc.1
0x83cc  ldarg.s  4
0x83ce  ldstr    aStarttime// "starttime"
0x83d3  callvirt T0x2B00001A
0x83d8  stloc.2
0x83d9  ldarg.s  4
0x83db  ldstr    aBookingstatusS// "bookingstatus.status"
0x83e0  callvirt T0x2B00000F
0x83e5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x83ea  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x83ef  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x83f4  stloc.3
0x83f5  ldarg.s  4
0x83f7  newobj   instance void SyncData::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity resourceBooking)
0x83fc  stloc.0
0x83fd  ldloc.0
0x83fe  ldloc.2
0x83ff  ldarg.0
0x8400  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x8405  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_UpperBoundDateTime()
0x840a  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x840f  brtrue.s loc_8414
0x8411  ldc.i4.0
0x8412  br.s     loc_8415
0x8414  ldc.i4.4
0x8415  callvirt instance void SyncData::set_SyncAction(valuetype SyncAction value)
0x841a  ldloc.0
0x841b  ldloc.3
0x841c  ldc.i4.2
0x841d  beq.s    loc_8422
0x841f  ldc.i4.3
0x8420  br.s     loc_8428
0x8422  ldloc.0
0x8423  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x8428  callvirt instance void SyncData::set_SyncAction(valuetype SyncAction value)
0x842d  ldarg.0
0x842e  ldloc.1
0x842f  ldc.i4.1
0x8430  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetIdMappingsForBookableResourceBooking(valuetype [mscorlib]System.Guid bookableResourceBookingId, bool includeDeletedInExchange)
0x8435  stloc.s  4
0x8437  ldloc.s  4
0x8439  brfalse  loc_85E4
0x843e  ldloc.s  4
0x8440  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x8445  stloc.s  5
0x8447  br       loc_85CA
0x844c  ldloc.s  5
0x844e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x8453  stloc.s  6
0x8455  ldloc.s  6
0x8457  ldstr    aUserid// "userid"
0x845c  callvirt T0x2B000013
0x8461  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x8466  stloc.s  7
0x8468  ldloc.s  6
0x846a  ldstr    aSyncstatus_0// "syncstatus"
0x846f  callvirt T0x2B000012
0x8474  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x8479  stloc.s  8
0x847b  ldloc.s  6
0x847d  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x8482  callvirt T0x2B000014
0x8487  stloc.s  9
0x8489  ldloc.s  7
0x848b  ldarg.2
0x848c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8491  brfalse  loc_859B
0x8496  ldloc.0
0x8497  ldloc.s  6
0x8499  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x849e  callvirt T0x2B000010
0x84a3  callvirt instance void SyncData::set_Id(valuetype [mscorlib]System.Guid value)
0x84a8  ldloc.0
0x84a9  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x84ae  brtrue   loc_8542
0x84b3  ldloc.0
0x84b4  ldloc.s  6
0x84b6  ldstr    aExchangeentryi// "exchangeentryid"
0x84bb  callvirt T0x2B000011
0x84c0  callvirt instance void SyncData::set_ExchangeId(string value)
0x84c5  ldloc.0
0x84c6  ldloc.s  6
0x84c8  ldstr    aSyncversionnum_0// "syncversionnumber"
0x84cd  callvirt T0x2B000019
0x84d2  callvirt instance void SyncData::set_SynchronizedVersionNumber(int64 value)
0x84d7  ldloc.s  9
0x84d9  brtrue.s loc_8526
0x84db  ldloc.s  6
0x84dd  ldstr    aRetries// "retries"
0x84e2  callvirt T0x2B00001B
0x84e7  ldarg.0
0x84e8  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x84ed  callvirt instance int32 ConfigurationSettings::get_MaxRetryCount()
0x84f2  bge.s    loc_851A
0x84f4  ldloc.s  8
0x84f6  ldc.i4.2
0x84f7  beq.s    loc_850D
0x84f9  ldarg.s  4
0x84fb  ldstr    aVersionnumber// "versionnumber"
0x8500  callvirt T0x2B000019
0x8505  ldloc.0
0x8506  callvirt instance int64 SyncData::get_SynchronizedVersionNumber()
0x850b  ble.s    loc_851A
0x850d  ldarg.1
0x850e  callvirt instance bool SyncConfig::get_IgnoreRetries()
0x8513  brfalse.s loc_8526
0x8515  ldloc.s  8
0x8517  ldc.i4.1
0x8518  bne.un.s loc_8526
0x851a  ldloc.0
0x851b  ldc.i4.3
0x851c  callvirt instance void SyncData::set_SyncAction(valuetype SyncAction value)
0x8521  br       loc_85CA
0x8526  ldloc.0
0x8527  ldloc.0
0x8528  callvirt instance string SyncData::get_ExchangeId()
0x852d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8532  brtrue.s loc_8537
0x8534  ldc.i4.1
0x8535  br.s     loc_8538
0x8537  ldc.i4.0
0x8538  callvirt instance void SyncData::set_SyncAction(valuetype SyncAction value)
0x853d  br       loc_85CA
0x8542  ldloc.0
0x8543  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x8548  ldc.i4.3
0x8549  bne.un.s loc_8570
0x854b  ldloc.s  9
0x854d  brtrue.s loc_8570
0x854f  ldloc.s  6
0x8551  ldstr    aExchangeentryi// "exchangeentryid"
0x8556  callvirt T0x2B000011
0x855b  stloc.s  0xA
0x855d  ldarg.s  5
0x855f  ldloc.s  7
0x8561  ldloc.s  0xA
0x8563  ldc.i4.0
0x8564  ldloc.0
0x8565  callvirt instance valuetype [mscorlib]System.Guid SyncData::get_Id()
0x856a  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x856f  pop
0x8570  ldloc.0
0x8571  callvirt instance valuetype SyncAction SyncData::get_SyncAction()
0x8576  ldc.i4.4
0x8577  bne.un.s loc_85CA
0x8579  ldloc.s  6
0x857b  ldstr    aExchangeentryi// "exchangeentryid"
0x8580  callvirt T0x2B000011
0x8585  stloc.s  0xB
0x8587  ldarg.s  5
0x8589  ldloc.s  7
0x858b  ldloc.s  0xB
0x858d  ldc.i4.1
0x858e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8593  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x8598  pop
0x8599  br.s     loc_85CA
0x859b  ldloc.s  9
0x859d  brtrue.s loc_85CA
0x859f  ldloc.s  6
0x85a1  ldstr    aExchangeentryi// "exchangeentryid"
0x85a6  callvirt T0x2B000011
0x85ab  stloc.s  0xC
0x85ad  ldloc.s  6
0x85af  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x85b4  callvirt T0x2B000010
0x85b9  stloc.s  0xD
0x85bb  ldarg.s  5
0x85bd  ldloc.s  7
0x85bf  ldloc.s  0xC
0x85c1  ldc.i4.0
0x85c2  ldloc.s  0xD
0x85c4  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x85c9  pop
0x85ca  ldloc.s  5
0x85cc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x85d1  brtrue   loc_844C
0x85d6  leave.s  loc_85E4
0x85d8  ldloc.s  5
0x85da  brfalse.s loc_85E3
0x85dc  ldloc.s  5
0x85de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85e3  endfinally
0x85e4  ldarg.0
0x85e5  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x85ea  ldstr    aMethodgetsyncd// "MethodGetSyncData"
0x85ef  callvirt instance void Metrics::StopTimer(string name)
0x85f4  ldloc.0
0x85f5  ret
```
