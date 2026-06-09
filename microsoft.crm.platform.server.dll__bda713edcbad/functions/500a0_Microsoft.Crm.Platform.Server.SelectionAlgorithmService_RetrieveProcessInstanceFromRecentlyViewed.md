# Microsoft.Crm.Platform.Server.SelectionAlgorithmService::RetrieveProcessInstanceFromRecentlyViewed

- ea: `0x500a0`
- end: `0x50247`
- name: `Microsoft.Crm.Platform.Server.SelectionAlgorithmService::RetrieveProcessInstanceFromRecentlyViewed`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x4ffa0`

## callees

- `0x4ccd0`
- `0x4db50`
- `0x4dbb0`
- `0x4dc10`
- `0x4dc20`
- `0x4dc40`
- `0x4dd20`
- `0x4dd50`
- `0x4de10`
- `0x4df40`
- `0x4e440`
- `0x4e720`
- `0x4e740`
- `0x4edf0`
- `0x4eee0`
- `0x500a0`
- `0x50bb0`
- `0x89be0`

## string_xrefs

- `0x50210`: `processid`
- `0x501c8`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x500a0  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x500a5  stloc.0
0x500a6  ldloc.0
0x500a7  ldarg.1
0x500a8  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass18_0::targetEntityId
0x500ad  ldarg.s  5
0x500af  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::GetActualEndUserId(class Microsoft.Crm.Platform.Server.IExecutionContext context)
0x500b4  stloc.1
0x500b5  ldloc.1
0x500b6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x500bb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x500c0  brfalse.s loc_500C4
0x500c2  ldnull
0x500c3  ret
0x500c4  ldarg.2
0x500c5  ldloc.1
0x500c6  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::CreateKey(int32, valuetype [mscorlib]System.Guid)
0x500cb  stloc.2
0x500cc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x500d1  ldloc.2
0x500d2  ldarg.s  5
0x500d4  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x500d9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings>::LookupEntry(void, var<u1>)
0x500de  stloc.3
0x500df  ldloc.3
0x500e0  brfalse.s loc_500EF
0x500e2  ldloc.3
0x500e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_RecentlyViewedXml()
0x500e8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x500ed  brfalse.s loc_500F1
0x500ef  ldnull
0x500f0  ret
0x500f1  ldnull
0x500f2  stloc.s  4
0x500f4  ldarg.0
0x500f5  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x500fa  ldarg.s  5
0x500fc  callvirt instance class Microsoft.Crm.Platform.Server.ILocalizationSettings Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateLocalizationSettings(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x50101  stloc.s  5
0x50103  ldarg.0
0x50104  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50109  ldarg.s  5
0x5010b  callvirt instance class Microsoft.Crm.Platform.Server.IDynamicMetadataCache Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateMetadataCache(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x50110  stloc.s  6
0x50112  ldarg.s  5
0x50114  ldloc.s  5
0x50116  ldloc.s  6
0x50118  ldarg.0
0x50119  ldfld    class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordComparer Microsoft.Crm.Platform.Server.SelectionAlgorithmService::recentlyViewedRecordComparer
0x5011e  ldarg.0
0x5011f  ldfld    class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordSerializer Microsoft.Crm.Platform.Server.SelectionAlgorithmService::recentlyViewedRecordSerializer
0x50124  newobj   instance void Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::.ctor(class Microsoft.Crm.Platform.Server.IExecutionContext context, class Microsoft.Crm.Platform.Server.ILocalizationSettings localizationSettings, class Microsoft.Crm.Platform.Server.IDynamicMetadataCache metadataCache, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordComparer comparer, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordSerializer serializer)
0x50129  ldloc.3
0x5012a  callvirt instance class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_RecentlyViewedXmlDoc()
0x5012f  stloc.s  7
0x50131  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x50136  stloc.s  8
0x50138  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x5013d  stloc.s  9
0x5013f  ldarg.2
0x50140  ldloc.s  7
0x50142  ldloc.s  8
0x50144  ldloc.s  9
0x50146  callvirt instance void Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::ParseMergeRecentlyViewedRecords(int32 etc, class [System.Xml]System.Xml.XmlNode entityDataNode, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> viewList, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> entityList)
0x5014b  ldloc.s  9
0x5014d  ldloc.0
0x5014e  ldftn    instance bool <>c__DisplayClass18_0::<RetrieveProcessInstanceFromRecentlyViewed>b__0(class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord record)
0x50154  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Platform.Server.IRecentlyViewedRecord, bool>::.ctor(object, native int)
0x50159  call     T0x2B000062
0x5015e  stloc.s  0xA
0x50160  ldloc.s  0xA
0x50162  brfalse  loc_50244
0x50167  ldloca.s 0xB
0x50169  ldloc.s  0xA
0x5016b  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessInstanceId()
0x50170  call     instance void [mscorlib]System.Guid::.ctor(string)
0x50175  ldloca.s 0xC
0x50177  ldloc.s  0xA
0x50179  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessId()
0x5017e  call     instance void [mscorlib]System.Guid::.ctor(string)
0x50183  ldarg.3
0x50184  brfalse.s loc_501E9
0x50186  ldarg.0
0x50187  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x5018c  ldloc.s  0xB
0x5018e  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x50193  ldarg.s  5
0x50195  callvirt instance class Microsoft.Crm.Platform.Server.IBusinessEntityMoniker Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateBusinessEntityMoniker(valuetype [mscorlib]System.Guid recordId, string entityPlatformName, class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x5019a  stloc.s  0xD
0x5019c  ldarg.0
0x5019d  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x501a2  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x501a7  ldarg.s  5
0x501a9  callvirt instance class Microsoft.Crm.Platform.Server.IEntityExpression Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateEntityExpression(string entityPlatformName, class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x501ae  stloc.s  0xE
0x501b0  ldloc.s  0xE
0x501b2  callvirt instance class Microsoft.Crm.Platform.Server.IColumnSetExpression Microsoft.Crm.Platform.Server.IEntityExpression::get_ColumnSet()
0x501b7  ldstr    aProcessstageid// "processstageid"
0x501bc  callvirt instance void Microsoft.Crm.Platform.Server.IColumnSetExpression::AddColumn(string columnName)
0x501c1  ldloc.s  0xE
0x501c3  callvirt instance class Microsoft.Crm.Platform.Server.IColumnSetExpression Microsoft.Crm.Platform.Server.IEntityExpression::get_ColumnSet()
0x501c8  ldstr    aTraversedpath// "traversedpath"
0x501cd  callvirt instance void Microsoft.Crm.Platform.Server.IColumnSetExpression::AddColumn(string columnName)
0x501d2  ldarg.s  4
0x501d4  ldloc.s  0xD
0x501d6  ldloc.s  0xE
0x501d8  ldarg.s  5
0x501da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Platform.Server.IBusinessProcessFlowInstanceService::Retrieve(class Microsoft.Crm.Platform.Server.IBusinessEntityMoniker moniker, class Microsoft.Crm.Platform.Server.IEntityExpression entityExpression, class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x501df  stloc.s  4
0x501e1  leave.s  loc_501F7
0x501e3  pop
0x501e4  ldnull
0x501e5  stloc.s  4
0x501e7  leave.s  loc_501F7
0x501e9  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x501ee  ldarg.s  5
0x501f0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x501f5  stloc.s  4
0x501f7  ldloc.s  4
0x501f9  brfalse.s loc_50244
0x501fb  ldloc.s  4
0x501fd  ldstr    aBusinessproces_0// "businessprocessflowinstanceid"
0x50202  ldloc.s  0xB
0x50204  box      [mscorlib]System.Guid
0x50209  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x5020e  ldloc.s  4
0x50210  ldstr    aProcessid// "processid"
0x50215  ldloc.s  0xC
0x50217  box      [mscorlib]System.Guid
0x5021c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x50221  ldarg.0
0x50222  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50227  ldarg.s  5
0x50229  callvirt instance class Microsoft.Crm.Platform.Server.IProcessUnificationFeature Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateProcessUnificationFeature(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x5022e  callvirt instance bool Microsoft.Crm.Platform.Server.IProcessUnificationFeature::get_FeatureEnabled()
0x50233  brfalse.s loc_50244
0x50235  ldarg.0
0x50236  ldloc.s  4
0x50238  ldarg.s  5
0x5023a  call     instance bool Microsoft.Crm.Platform.Server.SelectionAlgorithmService::IsBPFInstanceValidForCurrentUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity processInstance, class Microsoft.Crm.Platform.Server.IExecutionContext context)
0x5023f  brtrue.s loc_50244
0x50241  ldnull
0x50242  stloc.s  4
0x50244  ldloc.s  4
0x50246  ret
```
