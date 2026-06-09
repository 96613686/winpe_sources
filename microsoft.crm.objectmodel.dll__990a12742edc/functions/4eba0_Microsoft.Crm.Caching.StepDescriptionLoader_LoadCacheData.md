# Microsoft.Crm.Caching.StepDescriptionLoader::LoadCacheData

- ea: `0x4eba0`
- end: `0x4ee6b`
- name: `Microsoft.Crm.Caching.StepDescriptionLoader::LoadCacheData`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x22e10`
- `0x22e60`
- `0x4c7a0`
- `0x4eba0`
- `0x170580`

## string_xrefs

- `0x4ec28`: `configuration`
- `0x4ec85`: `plugintypeid`
- `0x4ecbb`: `createdby`
- `0x4ec18`: `asyncautodelete`
- `0x4ec20`: `canusereadonlyconnection`
- `0x4ec58`: `impersonatinguserid`
- `0x4ece1`: `SdkMessageProcessingStepSecureConfig`
- `0x4ece6`: `sdkmessageprocessingstepsecureconfigid`
- `0x4eceb`: `sdkmessageprocessingstepsecureconfigid`
- `0x4ed01`: `secureconfig`
- `0x4ed06`: `secureconfig`

## pseudocode

```c

```

## disassembly

```asm
0x4eba0  ldarg.1
0x4eba1  ldstr    aKey// "key"
0x4eba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x4ebab  ldnull
0x4ebac  stloc.0
0x4ebad  ldsfld   class [mscorlib]System.Lazy`1<bool> class Microsoft.Crm.Caching.ObjectModelCacheLoader`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Extensibility.StepDescription>::SetupMode
0x4ebb2  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x4ebb7  brtrue.s loc_4EBD7
0x4ebb9  call     class Microsoft.Crm.Caching.StepDescriptionCache Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x4ebbe  callvirt instance string class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Extensibility.StepDescription>::get_CacheIdentifier()
0x4ebc3  ldarga.s 1
0x4ebc5  constrained. [mscorlib]System.Guid
0x4ebcb  callvirt instance string [mscorlib]System.Object::ToString()
0x4ebd0  ldarg.2
0x4ebd1  call     T0x2B0000D1
0x4ebd6  stloc.0
0x4ebd7  ldloc.0
0x4ebd8  brtrue   loc_4EE52
0x4ebdd  ldarg.2
0x4ebde  ldc.i4.0
0x4ebdf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x4ebe4  stloc.2
0x4ebe5  newobj   instance void Microsoft.Crm.ObjectModel.SdkMessageProcessingStepService::.ctor()
0x4ebea  stloc.3
0x4ebeb  ldarg.2
0x4ebec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ebf1  ldc.i4   0x1200
0x4ebf6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x4ebfb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x4ec00  ldarg.2
0x4ec01  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4ec06  stloc.s  4
0x4ec08  ldloc.s  4
0x4ec0a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4ec0f  ldc.i4.s 0x14
0x4ec11  newarr   [mscorlib]System.String
0x4ec16  dup
0x4ec17  ldc.i4.0
0x4ec18  ldstr    aAsyncautodelet// "asyncautodelete"
0x4ec1d  stelem.ref
0x4ec1e  dup
0x4ec1f  ldc.i4.1
0x4ec20  ldstr    aCanusereadonly// "canusereadonlyconnection"
0x4ec25  stelem.ref
0x4ec26  dup
0x4ec27  ldc.i4.2
0x4ec28  ldstr    aConfiguration// "configuration"
0x4ec2d  stelem.ref
0x4ec2e  dup
0x4ec2f  ldc.i4.3
0x4ec30  ldstr    aDescription// "description"
0x4ec35  stelem.ref
0x4ec36  dup
0x4ec37  ldc.i4.4
0x4ec38  ldstr    aEventhandler// "eventhandler"
0x4ec3d  stelem.ref
0x4ec3e  dup
0x4ec3f  ldc.i4.5
0x4ec40  ldstr    aEventhandlerty// "eventhandlertypecode"
0x4ec45  stelem.ref
0x4ec46  dup
0x4ec47  ldc.i4.6
0x4ec48  ldstr    aEventexpander// "eventexpander"
0x4ec4d  stelem.ref
0x4ec4e  dup
0x4ec4f  ldc.i4.7
0x4ec50  ldstr    aFilteringattri// "filteringattributes"
0x4ec55  stelem.ref
0x4ec56  dup
0x4ec57  ldc.i4.8
0x4ec58  ldstr    aImpersonatingu// "impersonatinguserid"
0x4ec5d  stelem.ref
0x4ec5e  dup
0x4ec5f  ldc.i4.s 9
0x4ec61  ldstr    aInvocationsour_0// "invocationsource"
0x4ec66  stelem.ref
0x4ec67  dup
0x4ec68  ldc.i4.s 0xA
0x4ec6a  ldstr    aIshidden// "ishidden"
0x4ec6f  stelem.ref
0x4ec70  dup
0x4ec71  ldc.i4.s 0xB
0x4ec73  ldstr    aMode// "mode"
0x4ec78  stelem.ref
0x4ec79  dup
0x4ec7a  ldc.i4.s 0xC
0x4ec7c  ldstr    aName// "name"
0x4ec81  stelem.ref
0x4ec82  dup
0x4ec83  ldc.i4.s 0xD
0x4ec85  ldstr    aPlugintypeid// "plugintypeid"
0x4ec8a  stelem.ref
0x4ec8b  dup
0x4ec8c  ldc.i4.s 0xE
0x4ec8e  ldstr    aSdkmessagefilt// "sdkmessagefilterid"
0x4ec93  stelem.ref
0x4ec94  dup
0x4ec95  ldc.i4.s 0xF
0x4ec97  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x4ec9c  stelem.ref
0x4ec9d  dup
0x4ec9e  ldc.i4.s 0x10
0x4eca0  ldstr    aSolutionid// "solutionid"
0x4eca5  stelem.ref
0x4eca6  dup
0x4eca7  ldc.i4.s 0x11
0x4eca9  ldstr    aStage_0// "stage"
0x4ecae  stelem.ref
0x4ecaf  dup
0x4ecb0  ldc.i4.s 0x12
0x4ecb2  ldstr    aSupporteddeplo// "supporteddeployment"
0x4ecb7  stelem.ref
0x4ecb8  dup
0x4ecb9  ldc.i4.s 0x13
0x4ecbb  ldstr    aCreatedby// "createdby"
0x4ecc0  stelem.ref
0x4ecc1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4ecc6  ldloc.s  4
0x4ecc8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4eccd  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x4ecd2  ldc.i4.0
0x4ecd3  ldarg.1
0x4ecd4  box      [mscorlib]System.Guid
0x4ecd9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4ecde  pop
0x4ecdf  ldloc.s  4
0x4ece1  ldstr    aSdkmessageproc_2// "SdkMessageProcessingStepSecureConfig"
0x4ece6  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepsecureconfigid"
0x4eceb  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepsecureconfigid"
0x4ecf0  ldc.i4.0
0x4ecf1  ldc.i4.1
0x4ecf2  ldstr    aScfg// "scfg"
0x4ecf7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x4ecfc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed01  ldstr    aSecureconfig// "secureconfig"
0x4ed06  ldstr    aSecureconfig// "secureconfig"
0x4ed0b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed10  ldloc.s  4
0x4ed12  ldstr    aSdkmessageproc_4// "SdkMessageProcessingStepImage"
0x4ed17  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x4ed1c  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x4ed21  ldc.i4.0
0x4ed22  ldc.i4.1
0x4ed23  ldstr    aImage// "image"
0x4ed28  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x4ed2d  dup
0x4ed2e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed33  ldstr    aImagetype// "imagetype"
0x4ed38  ldstr    aImagetype// "imagetype"
0x4ed3d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed42  dup
0x4ed43  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed48  ldstr    aAttributes// "attributes"
0x4ed4d  ldstr    aAttributes// "attributes"
0x4ed52  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed57  dup
0x4ed58  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed5d  ldstr    aRelatedattribu// "relatedattributename"
0x4ed62  ldstr    aRelatedattribu// "relatedattributename"
0x4ed67  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed6c  dup
0x4ed6d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed72  ldstr    aEntityalias// "entityalias"
0x4ed77  ldstr    aEntityalias// "entityalias"
0x4ed7c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed81  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4ed86  ldstr    aMessagepropert// "messagepropertyname"
0x4ed8b  ldstr    aMessagepropert// "messagepropertyname"
0x4ed90  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumnWithAlias(string, string)
0x4ed95  ldloc.3
0x4ed96  ldloc.s  4
0x4ed98  ldarg.2
0x4ed99  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ed9e  stloc.s  5
0x4eda0  ldloc.s  5
0x4eda2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4eda7  brtrue.s loc_4EDB1
0x4eda9  ldnull
0x4edaa  stloc.s  7
0x4edac  leave    loc_4EE68
0x4edb1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData>::.ctor()
0x4edb6  pop
0x4edb7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData::.ctor()
0x4edbc  stloc.0
0x4edbd  ldloc.0
0x4edbe  ldloc.s  5
0x4edc0  ldc.i4.0
0x4edc1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x4edc6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x4edcb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription>::.ctor()
0x4edd0  stloc.s  6
0x4edd2  ldloc.s  5
0x4edd4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4edd9  stloc.s  8
0x4eddb  br.s     loc_4EDFA
0x4eddd  ldloc.s  8
0x4eddf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4ede4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4ede9  stloc.s  9
0x4edeb  ldloc.s  6
0x4eded  ldloc.0
0x4edee  ldloc.s  9
0x4edf0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData::GetImages(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x4edf5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4edfa  ldloc.s  8
0x4edfc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ee01  brtrue.s loc_4EDDD
0x4ee03  leave.s  loc_4EE1A
0x4ee05  ldloc.s  8
0x4ee07  isinst   [mscorlib]System.IDisposable
0x4ee0c  stloc.s  0xA
0x4ee0e  ldloc.s  0xA
0x4ee10  brfalse.s loc_4EE19
0x4ee12  ldloc.s  0xA
0x4ee14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ee19  endfinally
0x4ee1a  ldloc.0
0x4ee1b  ldloc.s  6
0x4ee1d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription>::ToArray()
0x4ee22  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData::set_Images(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepImageDescription[])
0x4ee27  leave.s  loc_4EE33
0x4ee29  ldloc.2
0x4ee2a  brfalse.s loc_4EE32
0x4ee2c  ldloc.2
0x4ee2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ee32  endfinally
0x4ee33  call     class Microsoft.Crm.Caching.StepDescriptionCache Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x4ee38  callvirt instance string class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Extensibility.StepDescription>::get_CacheIdentifier()
0x4ee3d  ldarga.s 1
0x4ee3f  constrained. [mscorlib]System.Guid
0x4ee45  callvirt instance string [mscorlib]System.Object::ToString()
0x4ee4a  ldloc.0
0x4ee4b  ldarg.2
0x4ee4c  call     T0x2B0000D2
0x4ee51  pop
0x4ee52  newobj   instance void [Microsoft.Xrm.EventExpander.Bridges]Microsoft.Xrm.EventExpander.Bridges.EventRegistrationFactory::.ctor()
0x4ee57  stloc.1
0x4ee58  ldnull
0x4ee59  ldloc.0
0x4ee5a  ldloc.1
0x4ee5b  newobj   instance void Microsoft.Crm.Extensibility.StepDescription::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey messageProcessorKey, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.StepDescriptionCacheData data, class [Microsoft.Xrm.EventExpander.Bridges]Microsoft.Xrm.EventExpander.Bridges.IEventRegistrationFactory factory)
0x4ee60  dup
0x4ee61  ldarg.2
0x4ee62  callvirt instance void Microsoft.Crm.Extensibility.StepDescription::Initialize(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ee67  ret
0x4ee68  ldloc.s  7
0x4ee6a  ret
```
