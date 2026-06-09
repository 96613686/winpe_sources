# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::CheckAndRepairExchangeSyncIdMappings

- ea: `0x54050`
- end: `0x543d6`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::CheckAndRepairExchangeSyncIdMappings`
- size: `902`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x53810`

## callees

- `0x53540`
- `0x53700`
- `0x53a20`
- `0x54050`
- `0x54b30`
- `0x54b60`
- `0x54b90`
- `0x54bb0`
- `0x54be0`
- `0x54c00`
- `0x5eae0`
- `0x5eb00`
- `0x5eb20`
- `0x5eb40`
- `0x5eb80`
- `0x71300`
- `0x82a70`

## string_xrefs

- `0x540e5`: `Could not find the IdMapping for Item with Exchange id {0}, Crm id {1}, Item ObjectType {2}, So created a new IdMapping with Id {3}.`
- `0x541a2`: `The ExchangeEntryId of the IdMapping with Id {0}, Exchange id {1}, Crm id {2}, Item ObjectType {3} is updated to {4} for the item which is promoted immediately from the client.`
- `0x5421d`: `The CrmId of the IdMapping with Id {0}, Exchange id {1}, Crm id {2}, Item ObjectType {3} is updated to {4} which was stamped on the Exchange Item.`
- `0x54391`: `Considering the IdMapping with Id {0}, Exchange id {1}, Crm id {2}, Item ObjectType {3}`

## pseudocode

```c

```

## disassembly

```asm
0x54050  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x54055  stloc.0
0x54056  ldloc.0
0x54057  ldarg.2
0x54058  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x5405d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54062  stloc.1
0x54063  ldloc.0
0x54064  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54069  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5406e  ldloca.s 1
0x54070  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x54075  brfalse.s loc_54084
0x54077  ldloc.1
0x54078  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5407d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54082  br.s     loc_54085
0x54084  ldc.i4.0
0x54085  stloc.2
0x54086  ldnull
0x54087  stloc.3
0x54088  ldarg.1
0x54089  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper>::get_Count()
0x5408e  ldc.i4.0
0x5408f  ceq
0x54091  ldloc.2
0x54092  and
0x54093  brfalse  loc_54132
0x54098  ldloc.0
0x54099  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x5409e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x540a3  ldc.i4.3
0x540a4  bne.un   loc_54132
0x540a9  ldloc.0
0x540aa  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x540af  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x540b4  brfalse.s loc_54132
0x540b6  ldarg.0
0x540b7  ldloc.0
0x540b8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x540bd  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x540c2  ldloc.0
0x540c3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x540c8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x540cd  ldloc.0
0x540ce  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x540d3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x540d8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::AddExchangeSyncIdMapping(string crmId, string exchangeEntryId, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x540dd  stloc.3
0x540de  ldarg.0
0x540df  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::traceHandler
0x540e4  ldc.i4.4
0x540e5  ldstr    aCouldNotFindTh// "Could not find the IdMapping for Item w"...
0x540ea  ldc.i4.4
0x540eb  newarr   [mscorlib]System.Object
0x540f0  dup
0x540f1  ldc.i4.0
0x540f2  ldloc.0
0x540f3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x540f8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x540fd  stelem.ref
0x540fe  dup
0x540ff  ldc.i4.1
0x54100  ldloc.0
0x54101  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54106  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5410b  stelem.ref
0x5410c  dup
0x5410d  ldc.i4.2
0x5410e  ldloc.0
0x5410f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54114  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x54119  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5411e  stelem.ref
0x5411f  dup
0x54120  ldc.i4.3
0x54121  ldloc.3
0x54122  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x54127  box      [mscorlib]System.Guid
0x5412c  stelem.ref
0x5412d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x54132  ldarg.1
0x54133  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper>::get_Count()
0x54138  ldc.i4.1
0x54139  bne.un   loc_5426E
0x5413e  ldarg.1
0x5413f  call     T0x2B00006C
0x54144  stloc.3
0x54145  ldloc.3
0x54146  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x5414b  ldloc.0
0x5414c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54151  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x54156  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5415b  brfalse  loc_541F3
0x54160  ldloc.0
0x54161  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54166  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemSSSPromoteTracker()
0x5416b  ldc.i4.1
0x5416c  bne.un   loc_541F3
0x54171  ldloc.0
0x54172  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54177  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x5417c  ldc.i4   0x1F40
0x54181  beq.s    loc_541F3
0x54183  ldloc.3
0x54184  ldloc.0
0x54185  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x5418a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5418f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_ExchangeEntryId(string value)
0x54194  ldarg.0
0x54195  ldloc.3
0x54196  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x5419b  ldarg.0
0x5419c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::traceHandler
0x541a1  ldc.i4.4
0x541a2  ldstr    aTheExchangeent// "The ExchangeEntryId of the IdMapping wi"...
0x541a7  ldc.i4.5
0x541a8  newarr   [mscorlib]System.Object
0x541ad  dup
0x541ae  ldc.i4.0
0x541af  ldloc.3
0x541b0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x541b5  box      [mscorlib]System.Guid
0x541ba  stelem.ref
0x541bb  dup
0x541bc  ldc.i4.1
0x541bd  ldloc.3
0x541be  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x541c3  stelem.ref
0x541c4  dup
0x541c5  ldc.i4.2
0x541c6  ldloc.3
0x541c7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x541cc  box      [mscorlib]System.Guid
0x541d1  stelem.ref
0x541d2  dup
0x541d3  ldc.i4.3
0x541d4  ldloc.3
0x541d5  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x541da  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x541df  stelem.ref
0x541e0  dup
0x541e1  ldc.i4.4
0x541e2  ldloc.0
0x541e3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x541e8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x541ed  stelem.ref
0x541ee  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x541f3  ldloc.2
0x541f4  brfalse.s loc_5426E
0x541f6  ldloc.3
0x541f7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x541fc  stloc.s  4
0x541fe  ldloca.s 4
0x54200  ldloc.1
0x54201  call     instance int32 [mscorlib]System.Guid::CompareTo(valuetype [mscorlib]System.Guid)
0x54206  brfalse.s loc_5426E
0x54208  ldloc.3
0x54209  ldloc.1
0x5420a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_CrmId(valuetype [mscorlib]System.Guid value)
0x5420f  ldarg.0
0x54210  ldloc.3
0x54211  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x54216  ldarg.0
0x54217  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::traceHandler
0x5421c  ldc.i4.4
0x5421d  ldstr    aTheCrmidOfTheI// "The CrmId of the IdMapping with Id {0},"...
0x54222  ldc.i4.5
0x54223  newarr   [mscorlib]System.Object
0x54228  dup
0x54229  ldc.i4.0
0x5422a  ldloc.3
0x5422b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x54230  box      [mscorlib]System.Guid
0x54235  stelem.ref
0x54236  dup
0x54237  ldc.i4.1
0x54238  ldloc.3
0x54239  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x5423e  stelem.ref
0x5423f  dup
0x54240  ldc.i4.2
0x54241  ldloc.3
0x54242  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x54247  box      [mscorlib]System.Guid
0x5424c  stelem.ref
0x5424d  dup
0x5424e  ldc.i4.3
0x5424f  ldloc.3
0x54250  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x54255  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5425a  stelem.ref
0x5425b  dup
0x5425c  ldc.i4.4
0x5425d  ldloc.0
0x5425e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54263  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x54268  stelem.ref
0x54269  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5426e  ldarg.1
0x5426f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper>::get_Count()
0x54274  ldc.i4.1
0x54275  cgt
0x54277  ldloc.2
0x54278  and
0x54279  brfalse  loc_54301
0x5427e  ldarg.1
0x5427f  ldloc.0
0x54280  ldftn    instance bool <>c__DisplayClass18_0::<CheckAndRepairExchangeSyncIdMappings>b__0(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper idmapping)
0x54286  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper, bool>::.ctor(object, native int)
0x5428b  call     T0x2B000093
0x54290  stloc.s  5
0x54292  ldloc.s  5
0x54294  call     T0x2B000094
0x54299  ldc.i4.1
0x5429a  bne.un.s loc_542A6
0x5429c  ldloc.s  5
0x5429e  call     T0x2B00006C
0x542a3  stloc.3
0x542a4  br.s     loc_54301
0x542a6  ldloc.s  5
0x542a8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper>::GetEnumerator()
0x542ad  stloc.s  6
0x542af  br.s     loc_542C2
0x542b1  ldloc.s  6
0x542b3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper>::get_Current()
0x542b8  stloc.s  7
0x542ba  ldarg.0
0x542bb  ldloc.s  7
0x542bd  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::DeleteExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x542c2  ldloc.s  6
0x542c4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x542c9  brtrue.s loc_542B1
0x542cb  leave.s  loc_542D9
0x542cd  ldloc.s  6
0x542cf  brfalse.s loc_542D8
0x542d1  ldloc.s  6
0x542d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x542d8  endfinally
0x542d9  ldarg.0
0x542da  ldloc.0
0x542db  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x542e0  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x542e5  ldloc.0
0x542e6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x542eb  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x542f0  ldloc.0
0x542f1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x542f6  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x542fb  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::AddExchangeSyncIdMapping(string crmId, string exchangeEntryId, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x54300  stloc.3
0x54301  ldloc.3
0x54302  brfalse  loc_54387
0x54307  ldloc.3
0x54308  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x5430d  ldloc.0
0x5430e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54313  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x54318  beq.s    loc_54387
0x5431a  ldloc.0
0x5431b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54320  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x54325  ldc.i4.2
0x54326  beq.s    loc_54387
0x54328  ldarg.0
0x54329  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::traceHandler
0x5432e  ldc.i4.4
0x5432f  ldstr    aTheIdmappingWi// "The IdMapping with Id {0}, Exchange id "...
0x54334  ldc.i4.5
0x54335  newarr   [mscorlib]System.Object
0x5433a  dup
0x5433b  ldc.i4.0
0x5433c  ldloc.3
0x5433d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x54342  box      [mscorlib]System.Guid
0x54347  stelem.ref
0x54348  dup
0x54349  ldc.i4.1
0x5434a  ldloc.3
0x5434b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x54350  stelem.ref
0x54351  dup
0x54352  ldc.i4.2
0x54353  ldloc.3
0x54354  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x54359  box      [mscorlib]System.Guid
0x5435e  stelem.ref
0x5435f  dup
0x54360  ldc.i4.3
0x54361  ldloc.3
0x54362  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x54367  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5436c  stelem.ref
0x5436d  dup
0x5436e  ldc.i4.4
0x5436f  ldloc.0
0x54370  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo <>c__DisplayClass18_0::syncItemChangeInfo
0x54375  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x5437a  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
  ... truncated ...
```
