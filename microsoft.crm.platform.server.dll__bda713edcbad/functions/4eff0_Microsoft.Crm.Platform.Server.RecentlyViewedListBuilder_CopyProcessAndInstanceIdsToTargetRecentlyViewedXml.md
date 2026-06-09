# Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::CopyProcessAndInstanceIdsToTargetRecentlyViewedXml

- ea: `0x4eff0`
- end: `0x4f22e`
- name: `Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::CopyProcessAndInstanceIdsToTargetRecentlyViewedXml`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4df30`
- `0x4df40`
- `0x4df50`
- `0x4e6e0`
- `0x4e720`
- `0x4e730`
- `0x4e740`
- `0x4e750`
- `0x4eff0`
- `0x4f230`
- `0x4f260`
- `0x4f340`
- `0x4f4a0`
- `0x66ff0`
- `0x89b30`

## string_xrefs

- `0x4f012`: `AlreadyMergedRecentlyViewedXml`
- `0x4f02e`: `AlreadyMergedRecentlyViewedXml`
- `0x4f051`: `AlreadyMergedRecentlyViewedXml`

## pseudocode

```c

```

## disassembly

```asm
0x4eff0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x4eff5  stloc.0
0x4eff6  ldarg.1
0x4eff7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4effc  brfalse.s loc_4F000
0x4effe  ldnull
0x4efff  ret
0x4f000  ldc.i4.0
0x4f001  stloc.1
0x4f002  ldarg.0
0x4f003  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f008  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4f00d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x4f012  ldstr    aAlreadymergedr// "AlreadyMergedRecentlyViewedXml"
0x4f017  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x4f01c  brfalse.s loc_4F03E
0x4f01e  ldarg.0
0x4f01f  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f024  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4f029  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x4f02e  ldstr    aAlreadymergedr// "AlreadyMergedRecentlyViewedXml"
0x4f033  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x4f038  unbox.any [mscorlib]System.Boolean
0x4f03d  stloc.1
0x4f03e  ldloc.1
0x4f03f  brfalse.s loc_4F063
0x4f041  ldarg.0
0x4f042  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f047  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4f04c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x4f051  ldstr    aAlreadymergedr// "AlreadyMergedRecentlyViewedXml"
0x4f056  ldc.i4.0
0x4f057  box      [mscorlib]System.Boolean
0x4f05c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4f061  ldnull
0x4f062  ret
0x4f063  ldarg.0
0x4f064  ldarg.1
0x4f065  call     instance int32 Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::GetEntityTypeCodeFromRecentlyViewedXml(string recentlyViewedXml)
0x4f06a  stloc.2
0x4f06b  ldloc.2
0x4f06c  ldc.i4.0
0x4f06d  bgt.s    loc_4F071
0x4f06f  ldnull
0x4f070  ret
0x4f071  ldarg.0
0x4f072  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f077  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.IExecutionContext::get_OriginalCaller()
0x4f07c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4f081  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4f086  brtrue.s loc_4F095
0x4f088  ldarg.0
0x4f089  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f08e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.IExecutionContext::get_Caller()
0x4f093  br.s     loc_4F0A0
0x4f095  ldarg.0
0x4f096  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f09b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.IExecutionContext::get_OriginalCaller()
0x4f0a0  stloc.3
0x4f0a1  ldloc.2
0x4f0a2  ldloc.3
0x4f0a3  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::CreateKey(int32, valuetype [mscorlib]System.Guid)
0x4f0a8  stloc.s  4
0x4f0aa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x4f0af  ldloc.s  4
0x4f0b1  ldarg.0
0x4f0b2  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::context
0x4f0b7  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings>::LookupEntry(void, var<u1>)
0x4f0bc  stloc.s  5
0x4f0be  ldloc.s  5
0x4f0c0  brfalse.s loc_4F0D0
0x4f0c2  ldloc.s  5
0x4f0c4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_RecentlyViewedXml()
0x4f0c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f0ce  brfalse.s loc_4F0D2
0x4f0d0  ldnull
0x4f0d1  ret
0x4f0d2  ldloc.s  5
0x4f0d4  callvirt instance class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_RecentlyViewedXmlDoc()
0x4f0d9  stloc.s  6
0x4f0db  ldloc.0
0x4f0dc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x4f0e1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f0e6  ldarg.0
0x4f0e7  ldloc.2
0x4f0e8  ldloc.s  6
0x4f0ea  ldloc.0
0x4f0eb  ldftn    instance void <>c__DisplayClass9_0::<CopyProcessAndInstanceIdsToTargetRecentlyViewedXml>b__0(class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord recentlyViewedRecord)
0x4f0f1  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor(object, native int)
0x4f0f6  call     instance void Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ParseRecentlyViewedRecordsXml(int32 entityTypeCode, class [System.Xml]System.Xml.XmlDocument recentlyViewedXmlDoc, class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> handleRecentlyViewedRecord)
0x4f0fb  ldloc.0
0x4f0fc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f101  brfalse.s loc_4F110
0x4f103  ldloc.0
0x4f104  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f109  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Count()
0x4f10e  brtrue.s loc_4F112
0x4f110  ldnull
0x4f111  ret
0x4f112  ldarg.1
0x4f113  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4f118  stloc.s  7
0x4f11a  ldloc.0
0x4f11b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x4f120  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::targetRecentlyViewedRecordList
0x4f125  ldarg.0
0x4f126  ldloc.2
0x4f127  ldloc.s  7
0x4f129  ldloc.0
0x4f12a  ldftn    instance void <>c__DisplayClass9_0::<CopyProcessAndInstanceIdsToTargetRecentlyViewedXml>b__1(class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord recentlyViewedRecord)
0x4f130  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor(object, native int)
0x4f135  call     instance void Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ParseRecentlyViewedRecordsXml(int32 entityTypeCode, class [System.Xml]System.Xml.XmlDocument recentlyViewedXmlDoc, class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> handleRecentlyViewedRecord)
0x4f13a  ldloc.0
0x4f13b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::targetRecentlyViewedRecordList
0x4f140  brfalse.s loc_4F14F
0x4f142  ldloc.0
0x4f143  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::targetRecentlyViewedRecordList
0x4f148  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Count()
0x4f14d  brtrue.s loc_4F151
0x4f14f  ldnull
0x4f150  ret
0x4f151  ldloc.0
0x4f152  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::targetRecentlyViewedRecordList
0x4f157  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::GetEnumerator()
0x4f15c  stloc.s  8
0x4f15e  br       loc_4F204
0x4f163  ldloca.s 8
0x4f165  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Current()
0x4f16a  stloc.s  9
0x4f16c  ldloc.0
0x4f16d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f172  ldloc.s  9
0x4f174  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ObjectId()
0x4f179  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::ContainsKey(var<u1>)
0x4f17e  brfalse  loc_4F204
0x4f183  ldarg.0
0x4f184  ldloc.s  9
0x4f186  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessInstanceId()
0x4f18b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ConvertToGuid(string guidString)
0x4f190  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4f195  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4f19a  brtrue.s loc_4F1B5
0x4f19c  ldarg.0
0x4f19d  ldloc.s  9
0x4f19f  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessId()
0x4f1a4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ConvertToGuid(string guidString)
0x4f1a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4f1ae  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4f1b3  brfalse.s loc_4F1F1
0x4f1b5  ldloc.s  9
0x4f1b7  ldloc.0
0x4f1b8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f1bd  ldloc.s  9
0x4f1bf  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ObjectId()
0x4f1c4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Item(void)
0x4f1c9  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessInstanceId()
0x4f1ce  callvirt instance void Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::set_ProcessInstanceId(string value)
0x4f1d3  ldloc.s  9
0x4f1d5  ldloc.0
0x4f1d6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f1db  ldloc.s  9
0x4f1dd  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ObjectId()
0x4f1e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Item(void)
0x4f1e7  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessId()
0x4f1ec  callvirt instance void Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::set_ProcessId(string value)
0x4f1f1  ldloc.0
0x4f1f2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::sourceRecentlyViewedRecordDict
0x4f1f7  ldloc.s  9
0x4f1f9  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ObjectId()
0x4f1fe  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::Remove(var<u1>)
0x4f203  pop
0x4f204  ldloca.s 8
0x4f206  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::MoveNext()
0x4f20b  brtrue   loc_4F163
0x4f210  leave.s  loc_4F220
0x4f212  ldloca.s 8
0x4f214  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>
0x4f21a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f21f  endfinally
0x4f220  ldarg.0
0x4f221  ldloc.2
0x4f222  ldloc.0
0x4f223  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> <>c__DisplayClass9_0::targetRecentlyViewedRecordList
0x4f228  call     instance string Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ToXml(int32 etc, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> recordList)
0x4f22d  ret
```
