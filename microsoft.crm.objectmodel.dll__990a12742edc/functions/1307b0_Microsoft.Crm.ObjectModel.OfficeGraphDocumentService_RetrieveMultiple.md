# Microsoft.Crm.ObjectModel.OfficeGraphDocumentService::RetrieveMultiple

- ea: `0x1307b0`
- end: `0x1309ea`
- name: `Microsoft.Crm.ObjectModel.OfficeGraphDocumentService::RetrieveMultiple`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ec10`
- `0x12ec30`
- `0x1307b0`
- `0x1309f0`
- `0x131310`
- `0x131380`
- `0x1313c0`

## string_xrefs

- `0x13080b`: `OfficeGraphDocumentService.RetrieveMultiple`
- `0x13086d`: `OfficeGraphDocumentService.RetrieveMultiple`
- `0x1308aa`: `OfficeGraphDocumentService.RetrieveMultiple`
- `0x13095d`: `OfficeGraphDocumentService.RetrieveMultiple`
- `0x1309d3`: `OfficeGraphDocumentService.RetrieveMultiple`
- `0x130810`: `Trending Documents is not supported by your company’s Microsoft Office service.`
- `0x13081f`: `Trending Documents is not supported by your company’s Microsoft Office service.`

## pseudocode

```c

```

## disassembly

```asm
0x1307b0  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x1307b5  stloc.0
0x1307b6  ldloc.0
0x1307b7  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x1307bc  ldarg.2
0x1307bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1307c2  ldarg.2
0x1307c3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1307c8  ldarg.0
0x1307c9  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1307ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x1307d3  ldc.i4.1
0x1307d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x1307d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x1307de  ldarg.2
0x1307df  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1307e4  call     bool Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::IsOfficeGraphIntegrationRegistryEnabled()
0x1307e9  brtrue   loc_1308CE
0x1307ee  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1307f3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1307f8  ldc.i4.2
0x1307f9  beq.s    loc_13082F
0x1307fb  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130800  ldstr    aTrendingdocume// "TrendingDocumentsOnpremiseDeploymentErr"...
0x130805  ldarg.2
0x130806  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x13080b  ldstr    aOfficegraphdoc_5// "OfficeGraphDocumentService.RetrieveMult"...
0x130810  ldstr    aTrendingDocume// "Trending Documents is not supported by "...
0x130815  ldc.i4   0x80044232
0x13081a  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogError(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails, int32 ErrorCode)
0x13081f  ldstr    aTrendingDocume// "Trending Documents is not supported by "...
0x130824  ldc.i4   0x80044232
0x130829  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x13082e  throw
0x13082f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x130834  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x130839  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeGraphIntegration()
0x13083e  ldarg.2
0x13083f  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x130844  brfalse.s loc_13085D
0x130846  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x13084b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x130850  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeGraphIntegration()
0x130855  ldarg.2
0x130856  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13085b  brtrue.s loc_130891
0x13085d  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130862  ldstr    aTrendingdocume_0// "TrendingDocumentsIntegrationDisabledErr"...
0x130867  ldarg.2
0x130868  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x13086d  ldstr    aOfficegraphdoc_5// "OfficeGraphDocumentService.RetrieveMult"...
0x130872  ldstr    aTrendingDocume_0// "Trending Documents is disabled for your"...
0x130877  ldc.i4   0x80044233
0x13087c  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogError(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails, int32 ErrorCode)
0x130881  ldstr    aTrendingDocume_0// "Trending Documents is disabled for your"...
0x130886  ldc.i4   0x80044233
0x13088b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x130890  throw
0x130891  ldc.i4.0
0x130892  ldarg.2
0x130893  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.OfficeGraphUtil::IsOfficeGraphIntegrationEnabled(bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x130898  brtrue.s loc_1308CE
0x13089a  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x13089f  ldstr    aTrendingdocume_1// "TrendingDocumentsIntegrationTurnedOffEr"...
0x1308a4  ldarg.2
0x1308a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1308aa  ldstr    aOfficegraphdoc_5// "OfficeGraphDocumentService.RetrieveMult"...
0x1308af  ldstr    aTrendingDocume_1// "Trending Documents is turned off. Pleas"...
0x1308b4  ldc.i4   0x80044255
0x1308b9  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogError(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails, int32 ErrorCode)
0x1308be  ldstr    aTrendingDocume_1// "Trending Documents is turned off. Pleas"...
0x1308c3  ldc.i4   0x80044255
0x1308c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1308cd  throw
0x1308ce  call     bool Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::IsOfficeGraphDataFromDBEnabledRegistry()
0x1308d3  brfalse.s loc_1308DE
0x1308d5  ldarg.0
0x1308d6  ldarg.1
0x1308d7  ldarg.2
0x1308d8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1308dd  ret
0x1308de  ldc.i4.0
0x1308df  stloc.1
0x1308e0  ldarg.1
0x1308e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1308e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1308eb  ldarg.2
0x1308ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1308f1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1308f6  stloc.2
0x1308f7  ldarg.1
0x1308f8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1308fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x130902  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::GetEnumerator()
0x130907  stloc.3
0x130908  br       loc_130994
0x13090d  ldloca.s 3
0x13090f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::get_Current()
0x130914  stloc.s  4
0x130916  ldloc.s  4
0x130918  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x13091d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x130922  ldstr    aQuerytype// "querytype"
0x130927  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x13092c  brtrue.s loc_130994
0x13092e  ldloc.s  4
0x130930  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0x130935  ldc.i4.0
0x130936  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x13093b  callvirt instance string [mscorlib]System.Object::ToString()
0x130940  ldc.i4.1
0x130941  ldloca.s 1
0x130943  call     T0x2B000227
0x130948  brfalse.s loc_13094D
0x13094a  ldloc.1
0x13094b  brtrue.s loc_1309A0
0x13094d  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130952  ldstr    aTrendingdocume_2// "TrendingDocumentsQueryTypeNotValid"
0x130957  ldarg.2
0x130958  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x13095d  ldstr    aOfficegraphdoc_5// "OfficeGraphDocumentService.RetrieveMult"...
0x130962  ldstr    aOfficegraphque// "officeGraphQueryType = "
0x130967  ldloc.s  4
0x130969  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0x13096e  ldc.i4.0
0x13096f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x130974  callvirt instance string [mscorlib]System.Object::ToString()
0x130979  ldstr    aQueryTypePasse// "Query type passed is not a valid Office"...
0x13097e  call     string [mscorlib]System.String::Concat(string, string, string)
0x130983  ldc.i4.0
0x130984  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogError(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails, int32 ErrorCode)
0x130989  ldstr    aQueryTypePasse// "Query type passed is not a valid Office"...
0x13098e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x130993  throw
0x130994  ldloca.s 3
0x130996  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::MoveNext()
0x13099b  brtrue   loc_13090D
0x1309a0  leave.s  loc_1309B0
0x1309a2  ldloca.s 3
0x1309a4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>
0x1309aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1309af  endfinally
0x1309b0  ldloc.1
0x1309b1  ldc.i4.1
0x1309b2  bne.un.s loc_1309BD
0x1309b4  ldarg.0
0x1309b5  ldarg.1
0x1309b6  ldarg.2
0x1309b7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.OfficeGraphDocumentService::RetrieveTrendingDocuments(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1309bc  stloc.2
0x1309bd  ldloc.0
0x1309be  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x1309c3  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x1309c8  ldstr    aRetrievemultip_4// "RetrieveMultipleTimetaken"
0x1309cd  ldarg.2
0x1309ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1309d3  ldstr    aOfficegraphdoc_5// "OfficeGraphDocumentService.RetrieveMult"...
0x1309d8  ldloc.0
0x1309d9  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x1309de  ldstr    aOverallTimeTak// "Overall time taken by Office Graph Docu"...
0x1309e3  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogOfficeGraphTimeTaken(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int64 TimeTaken, string EventDetails)
0x1309e8  ldloc.2
0x1309e9  ret
```
