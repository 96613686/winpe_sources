# Microsoft.Crm.Caching.MessageProcessorCacheLoader::LoadCacheData

- ea: `0x47b70`
- end: `0x48164`
- name: `Microsoft.Crm.Caching.MessageProcessorCacheLoader::LoadCacheData`
- size: `1524`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1fe90`
- `0x1fea0`
- `0x47b70`
- `0x48170`
- `0x54ce0`
- `0x170580`

## string_xrefs

- `0x47d38`: `configuration`
- `0x47d9e`: `plugintypeid`
- `0x47d40`: `createdby`
- `0x47c81`: `MessageProcessorCacheLoader.LoadCacheData(): No SdkFilter found for SdkMessage: [{0}], PrimaryOTC: [{1}], SecondaryOTC: [{2}]`
- `0x47d28`: `asyncautodelete`
- `0x47d30`: `canusereadonlyconnection`
- `0x47d71`: `impersonatinguserid`
- `0x47dd8`: `SdkMessageProcessingStepSecureConfig`
- `0x47ddd`: `sdkmessageprocessingstepsecureconfigid`
- `0x47de2`: `sdkmessageprocessingstepsecureconfigid`
- `0x47df8`: `secureconfig`
- `0x47dfd`: `secureconfig`
- `0x480e9`: `MessageProcessorCacheLoader:LoadCacheData(): Adding empty entry to MessageProcessor for SdkMessageId: [{0}], PrimaryEntity OTC: [{1}], Secondary OTC: [{2}]. SdkMessageFilter: [{3}]`

## pseudocode

```c

```

## disassembly

```asm
0x47b70  ldc.i4.0
0x47b71  stloc.0
0x47b72  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x47b77  brfalse.s loc_47B7B
0x47b79  ldc.i4.1
0x47b7a  stloc.0
0x47b7b  ldnull
0x47b7c  stloc.2
0x47b7d  ldc.i4.0
0x47b7e  stloc.s  4
0x47b80  ldc.i4.0
0x47b81  stloc.s  5
0x47b83  ldarg.2
0x47b84  ldc.i4.0
0x47b85  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x47b8a  stloc.s  8
0x47b8c  newobj   instance void Microsoft.Crm.ObjectModel.SdkMessageProcessingStepService::.ctor()
0x47b91  stloc.s  6
0x47b93  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageCache::get_Instance()
0x47b98  ldarg.1
0x47b99  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_MessageName()
0x47b9e  ldloca.s 1
0x47ba0  ldarg.2
0x47ba1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageCache::TryLookupEntry(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageData&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47ba6  brtrue.s loc_47BC6
0x47ba8  ldloc.s  6
0x47baa  ldarg.1
0x47bab  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_MessageName()
0x47bb0  ldarg.2
0x47bb1  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<class Microsoft.Crm.ObjectModel.UpgradingOff>::GetSdkMessageId(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x47bb6  stloc.3
0x47bb7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageCache::get_Instance()
0x47bbc  ldloc.3
0x47bbd  ldarg.2
0x47bbe  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageData>::LookupEntry(void, var<u1>)
0x47bc3  stloc.1
0x47bc4  br.s     loc_47BCD
0x47bc6  ldloc.1
0x47bc7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageData::get_SdkmessageId()
0x47bcc  stloc.3
0x47bcd  ldarg.1
0x47bce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_PrimaryEntity()
0x47bd3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47bd8  brtrue.s loc_47C05
0x47bda  ldarg.1
0x47bdb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_PrimaryEntity()
0x47be0  ldstr    aNone// "none"
0x47be5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x47bea  brfalse.s loc_47C05
0x47bec  ldarg.2
0x47bed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47bf2  ldarg.1
0x47bf3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_PrimaryEntity()
0x47bf8  ldc.i4.1
0x47bf9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x47bfe  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x47c03  stloc.s  4
0x47c05  ldarg.1
0x47c06  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_SecondaryEntity()
0x47c0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47c10  brtrue.s loc_47C3D
0x47c12  ldarg.1
0x47c13  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_SecondaryEntity()
0x47c18  ldstr    aNone// "none"
0x47c1d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x47c22  brfalse.s loc_47C3D
0x47c24  ldarg.2
0x47c25  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47c2a  ldarg.1
0x47c2b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_SecondaryEntity()
0x47c30  ldc.i4.1
0x47c31  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x47c36  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x47c3b  stloc.s  5
0x47c3d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache::get_Instance()
0x47c42  ldloc.3
0x47c43  ldloc.s  4
0x47c45  ldloc.s  5
0x47c47  ldloca.s 2
0x47c49  ldarg.2
0x47c4a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache::TryLookupEntry(valuetype [mscorlib]System.Guid, int32, int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageFilterData&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47c4f  brtrue.s loc_47CBE
0x47c51  ldloc.s  6
0x47c53  ldloc.3
0x47c54  ldloc.s  4
0x47c56  ldloc.s  5
0x47c58  ldarg.2
0x47c59  ldloca.s 2
0x47c5b  callvirt instance bool class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<class Microsoft.Crm.ObjectModel.UpgradingOff>::TryGetSdkMessageFilter(valuetype [mscorlib]System.Guid, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageFilterData&)
0x47c60  pop
0x47c61  ldloc.2
0x47c62  brfalse.s loc_47C78
0x47c64  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache::get_Instance()
0x47c69  ldloc.2
0x47c6a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageFilterData::get_SdkmessageFilterId()
0x47c6f  ldarg.2
0x47c70  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageFilterData>::LookupEntry(void, var<u1>)
0x47c75  pop
0x47c76  leave.s  loc_47CCC
0x47c78  ldnull
0x47c79  ldarg.2
0x47c7a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x47c7f  ldc.i4.s 0x1A
0x47c81  ldstr    aMessageprocess_3// "MessageProcessorCacheLoader.LoadCacheDa"...
0x47c86  ldc.i4.3
0x47c87  newarr   [mscorlib]System.Object
0x47c8c  dup
0x47c8d  ldc.i4.0
0x47c8e  ldloc.1
0x47c8f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageData::get_Name()
0x47c94  stelem.ref
0x47c95  dup
0x47c96  ldc.i4.1
0x47c97  ldloc.s  4
0x47c99  box      [mscorlib]System.Int32
0x47c9e  stelem.ref
0x47c9f  dup
0x47ca0  ldc.i4.2
0x47ca1  ldloc.s  5
0x47ca3  box      [mscorlib]System.Int32
0x47ca8  stelem.ref
0x47ca9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x47cae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache::get_Instance()
0x47cb3  ldloc.3
0x47cb4  ldloc.s  4
0x47cb6  ldloc.s  5
0x47cb8  ldarg.2
0x47cb9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache::AddEmptyEntry(valuetype [mscorlib]System.Guid, int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47cbe  leave.s  loc_47CCC
0x47cc0  ldloc.s  8
0x47cc2  brfalse.s loc_47CCB
0x47cc4  ldloc.s  8
0x47cc6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47ccb  endfinally
0x47ccc  ldnull
0x47ccd  stloc.s  7
0x47ccf  ldsfld   class [mscorlib]System.Lazy`1<bool> class Microsoft.Crm.Caching.ObjectModelCacheLoader`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey, class Microsoft.Crm.Extensibility.MessageProcessor>::SetupMode
0x47cd4  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x47cd9  brtrue.s loc_47CF3
0x47cdb  call     class Microsoft.Crm.Caching.MessageProcessorCache Microsoft.Crm.Caching.MessageProcessorCache::get_Instance()
0x47ce0  callvirt instance string class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey, class Microsoft.Crm.Extensibility.MessageProcessor>::get_CacheIdentifier()
0x47ce5  ldarg.1
0x47ce6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::get_CacheKey()
0x47ceb  ldarg.2
0x47cec  call     T0x2B0000C5
0x47cf1  stloc.s  7
0x47cf3  ldloc.s  7
0x47cf5  brtrue   loc_48154
0x47cfa  ldloc.2
0x47cfb  brfalse  loc_480E0
0x47d00  ldloc.2
0x47d01  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISdkMessageFilterData::IsEmpty()
0x47d06  brtrue   loc_480E0
0x47d0b  ldstr    aSdkmessageproc_0// "SdkMessageProcessingStep"
0x47d10  ldarg.2
0x47d11  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x47d16  stloc.s  9
0x47d18  ldloc.s  9
0x47d1a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x47d1f  ldc.i4.s 0x14
0x47d21  newarr   [mscorlib]System.String
0x47d26  dup
0x47d27  ldc.i4.0
0x47d28  ldstr    aAsyncautodelet// "asyncautodelete"
0x47d2d  stelem.ref
0x47d2e  dup
0x47d2f  ldc.i4.1
0x47d30  ldstr    aCanusereadonly// "canusereadonlyconnection"
0x47d35  stelem.ref
0x47d36  dup
0x47d37  ldc.i4.2
0x47d38  ldstr    aConfiguration// "configuration"
0x47d3d  stelem.ref
0x47d3e  dup
0x47d3f  ldc.i4.3
0x47d40  ldstr    aCreatedby// "createdby"
0x47d45  stelem.ref
0x47d46  dup
0x47d47  ldc.i4.4
0x47d48  ldstr    aDescription// "description"
0x47d4d  stelem.ref
0x47d4e  dup
0x47d4f  ldc.i4.5
0x47d50  ldstr    aEventhandler// "eventhandler"
0x47d55  stelem.ref
0x47d56  dup
0x47d57  ldc.i4.6
0x47d58  ldstr    aEventhandlerty// "eventhandlertypecode"
0x47d5d  stelem.ref
0x47d5e  dup
0x47d5f  ldc.i4.7
0x47d60  ldstr    aEventexpander// "eventexpander"
0x47d65  stelem.ref
0x47d66  dup
0x47d67  ldc.i4.8
0x47d68  ldstr    aFilteringattri// "filteringattributes"
0x47d6d  stelem.ref
0x47d6e  dup
0x47d6f  ldc.i4.s 9
0x47d71  ldstr    aImpersonatingu// "impersonatinguserid"
0x47d76  stelem.ref
0x47d77  dup
0x47d78  ldc.i4.s 0xA
0x47d7a  ldstr    aInvocationsour_0// "invocationsource"
0x47d7f  stelem.ref
0x47d80  dup
0x47d81  ldc.i4.s 0xB
0x47d83  ldstr    aIshidden// "ishidden"
0x47d88  stelem.ref
0x47d89  dup
0x47d8a  ldc.i4.s 0xC
0x47d8c  ldstr    aMode// "mode"
0x47d91  stelem.ref
0x47d92  dup
0x47d93  ldc.i4.s 0xD
0x47d95  ldstr    aName// "name"
0x47d9a  stelem.ref
0x47d9b  dup
0x47d9c  ldc.i4.s 0xE
0x47d9e  ldstr    aPlugintypeid// "plugintypeid"
0x47da3  stelem.ref
0x47da4  dup
0x47da5  ldc.i4.s 0xF
0x47da7  ldstr    aSdkmessagefilt// "sdkmessagefilterid"
0x47dac  stelem.ref
0x47dad  dup
0x47dae  ldc.i4.s 0x10
0x47db0  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x47db5  stelem.ref
0x47db6  dup
0x47db7  ldc.i4.s 0x11
0x47db9  ldstr    aSolutionid// "solutionid"
0x47dbe  stelem.ref
0x47dbf  dup
0x47dc0  ldc.i4.s 0x12
0x47dc2  ldstr    aStage_0// "stage"
0x47dc7  stelem.ref
0x47dc8  dup
0x47dc9  ldc.i4.s 0x13
0x47dcb  ldstr    aSupporteddeplo// "supporteddeployment"
0x47dd0  stelem.ref
0x47dd1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x47dd6  ldloc.s  9
0x47dd8  ldstr    aSdkmessageproc_2// "SdkMessageProcessingStepSecureConfig"
0x47ddd  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepsecureconfigid"
0x47de2  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepsecureconfigid"
0x47de7  ldc.i4.0
0x47de8  ldc.i4.1
0x47de9  ldstr    aScfg// "scfg"
0x47dee  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x47df3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47df8  ldstr    aSecureconfig// "secureconfig"
0x47dfd  ldstr    aSecureconfig// "secureconfig"
0x47e02  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e07  ldloc.s  9
0x47e09  ldstr    aSdkmessageproc_4// "SdkMessageProcessingStepImage"
0x47e0e  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x47e13  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x47e18  ldc.i4.0
0x47e19  ldc.i4.1
0x47e1a  ldstr    aImage// "image"
0x47e1f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x47e24  dup
0x47e25  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47e2a  ldstr    aImagetype// "imagetype"
0x47e2f  ldstr    aImagetype// "imagetype"
0x47e34  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e39  dup
0x47e3a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47e3f  ldstr    aAttributes// "attributes"
0x47e44  ldstr    aAttributes// "attributes"
0x47e49  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e4e  dup
0x47e4f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47e54  ldstr    aRelatedattribu// "relatedattributename"
0x47e59  ldstr    aRelatedattribu// "relatedattributename"
0x47e5e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e63  dup
0x47e64  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47e69  ldstr    aEntityalias// "entityalias"
0x47e6e  ldstr    aEntityalias// "entityalias"
0x47e73  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e78  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x47e7d  ldstr    aMessagepropert// "messagepropertyname"
0x47e82  ldstr    aMessagepropert// "messagepropertyname"
0x47e87  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x47e8c  ldloc.s  9
0x47e8e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x47e93  ldc.i4.1
0x47e94  ldstr    aRank// "rank"
0x47e99  ldc.i4.0
0x47e9a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x47e9f  ldloc.s  9
0x47ea1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x47ea6  ldc.i4.0
0x47ea7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x47eac  stloc.s  0xA
0x47eae  ldloc.s  0xA
0x47eb0  ldstr    aStatecode// "statecode"
0x47eb5  ldc.i4.0
  ... truncated ...
```
