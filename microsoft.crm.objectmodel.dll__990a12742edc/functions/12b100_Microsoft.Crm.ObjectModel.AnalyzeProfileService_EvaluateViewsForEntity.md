# Microsoft.Crm.ObjectModel.AnalyzeProfileService::EvaluateViewsForEntity

- ea: `0x12b100`
- end: `0x12b2f2`
- name: `Microsoft.Crm.ObjectModel.AnalyzeProfileService::EvaluateViewsForEntity`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x12af30`

## callees

- `0x19b50`
- `0x12b100`
- `0x12b300`
- `0x12b790`
- `0x12b7d0`
- `0x16df80`
- `0x16fe60`

## string_xrefs

- `0x12b135`: `fetchxml`
- `0x12b1cf`: `fetchxml`
- `0x12b1fc`: `fetchxml`
- `0x12b180`: `AnalyzeProfileService::EvaluateViewsForEntity , No metadata found for entity : {0}`
- `0x12b278`: `AnalyzeProfileService::EvaluateViewsForEntity , Execption occured while generating the sql for view : {0}`
- `0x12b2a3`: `MobileOfflineProfile.AnalyzeView.Comments.Column.Value.IndividualActivityViewsNotSupported`
- `0x12b2b7`: `MobileOfflineProfile.AnalyzeView.Comments.Column.Value.EmptyFetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x12b100  newobj   instance void Microsoft.Crm.ObjectModel.EntityViewCollection::.ctor()
0x12b105  stloc.0
0x12b106  newobj   instance void Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x12b10b  ldc.i4.1
0x12b10c  newarr   [mscorlib]System.Int32
0x12b111  dup
0x12b112  ldc.i4.0
0x12b113  ldarg.1
0x12b114  stelem.i4
0x12b115  ldc.i4.4
0x12b116  newarr   [mscorlib]System.String
0x12b11b  dup
0x12b11c  ldc.i4.0
0x12b11d  ldstr    aName// "name"
0x12b122  stelem.ref
0x12b123  dup
0x12b124  ldc.i4.1
0x12b125  ldstr    aQuerytype// "querytype"
0x12b12a  stelem.ref
0x12b12b  dup
0x12b12c  ldc.i4.2
0x12b12d  ldstr    aReturnedtypeco// "returnedtypecode"
0x12b132  stelem.ref
0x12b133  dup
0x12b134  ldc.i4.3
0x12b135  ldstr    aFetchxml// "fetchxml"
0x12b13a  stelem.ref
0x12b13b  ldc.i4.1
0x12b13c  newarr   Microsoft.Crm.ObjectModel.SavedQueryType
0x12b141  ldarg.3
0x12b142  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SavedQueryService::RetrieveSavedQueryForEntities(int32[] entityTypeCodes, string[] columns, valuetype Microsoft.Crm.ObjectModel.SavedQueryType[] queryTypes, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12b147  stloc.1
0x12b148  ldloc.1
0x12b149  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x12b14e  ldc.i4.0
0x12b14f  ble      loc_12B2F0
0x12b154  ldarg.3
0x12b155  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12b15a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x12b15f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12b164  ldarg.1
0x12b165  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x12b16a  stloc.2
0x12b16b  ldloc.2
0x12b16c  brtrue.s loc_12B19B
0x12b16e  ldstr    aEntityMetadata// "Entity Metadata not found"
0x12b173  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x12b178  ldarg.3
0x12b179  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12b17e  ldc.i4.s 0x11
0x12b180  ldstr    aAnalyzeprofile_0// "AnalyzeProfileService::EvaluateViewsFor"...
0x12b185  ldarg.1
0x12b186  box      [mscorlib]System.Int32
0x12b18b  call     string [mscorlib]System.String::Format(string, object)
0x12b190  ldc.i4.0
0x12b191  newarr   [mscorlib]System.Object
0x12b196  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12b19b  ldloc.1
0x12b19c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x12b1a1  stloc.3
0x12b1a2  br       loc_12B2CF
0x12b1a7  ldloc.3
0x12b1a8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x12b1ad  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x12b1b2  stloc.s  4
0x12b1b4  ldloc.s  4
0x12b1b6  ldstr    aName// "name"
0x12b1bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12b1c0  castclass [mscorlib]System.String
0x12b1c5  ldarg.1
0x12b1c6  newobj   instance void Microsoft.Crm.ObjectModel.EntityView::.ctor(string viewName, int32 entityObjectTypeCode)
0x12b1cb  stloc.s  5
0x12b1cd  ldloc.s  4
0x12b1cf  ldstr    aFetchxml// "fetchxml"
0x12b1d4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12b1d9  castclass [mscorlib]System.String
0x12b1de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12b1e3  brtrue   loc_12B296
0x12b1e8  ldloc.2
0x12b1e9  brfalse  loc_12B296
0x12b1ee  ldloc.2
0x12b1ef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x12b1f4  brtrue   loc_12B296
0x12b1f9  ldarg.0
0x12b1fa  ldloc.s  4
0x12b1fc  ldstr    aFetchxml// "fetchxml"
0x12b201  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12b206  castclass [mscorlib]System.String
0x12b20b  ldarg.2
0x12b20c  ldarg.3
0x12b20d  call     instance void Microsoft.Crm.ObjectModel.AnalyzeProfileService::EvaluateSavedQueryFetchXmlForOffline(string fetchXml, class [mscorlib]System.Collections.Generic.List`1<string> profileItems, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12b212  ldloc.s  5
0x12b214  ldc.i4.1
0x12b215  stfld    bool Microsoft.Crm.ObjectModel.EntityView::IsOfflineAvailable
0x12b21a  leave    loc_12B2C7
0x12b21f  stloc.s  6
0x12b221  ldloc.s  6
0x12b223  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmMobileOfflineOperationNotSupported
0x12b228  brtrue.s loc_12B23C
0x12b22a  ldloc.s  6
0x12b22c  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmMobileOfflineEntityNotSupportedInProfile
0x12b231  brtrue.s loc_12B23C
0x12b233  ldloc.s  6
0x12b235  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmMobileOfflineNotSupportedAttributeType
0x12b23a  brfalse.s loc_12B26E
0x12b23c  ldarg.3
0x12b23d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12b242  ldc.i4.s 0x11
0x12b244  ldstr    aRecievedExcept// "Recieved Exception while generating off"...
0x12b249  ldc.i4.1
0x12b24a  newarr   [mscorlib]System.Object
0x12b24f  dup
0x12b250  ldc.i4.0
0x12b251  ldloc.s  6
0x12b253  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12b258  stelem.ref
0x12b259  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12b25e  ldloc.s  5
0x12b260  ldloc.s  6
0x12b262  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12b267  stfld    string Microsoft.Crm.ObjectModel.EntityView::OfflineNonAvailabilityReason
0x12b26c  br.s     loc_12B294
0x12b26e  ldloc.s  6
0x12b270  ldarg.3
0x12b271  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12b276  ldc.i4.s 0x11
0x12b278  ldstr    aAnalyzeprofile_1// "AnalyzeProfileService::EvaluateViewsFor"...
0x12b27d  ldloc.s  6
0x12b27f  callvirt instance string [mscorlib]System.Object::ToString()
0x12b284  call     string [mscorlib]System.String::Format(string, object)
0x12b289  ldc.i4.0
0x12b28a  newarr   [mscorlib]System.Object
0x12b28f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12b294  leave.s  loc_12B2C7
0x12b296  ldloc.2
0x12b297  brfalse.s loc_12B2B5
0x12b299  ldloc.2
0x12b29a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x12b29f  brfalse.s loc_12B2B5
0x12b2a1  ldloc.s  5
0x12b2a3  ldstr    aMobileofflinep_6// "MobileOfflineProfile.AnalyzeView.Commen"...
0x12b2a8  ldarg.3
0x12b2a9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12b2ae  stfld    string Microsoft.Crm.ObjectModel.EntityView::OfflineNonAvailabilityReason
0x12b2b3  br.s     loc_12B2C7
0x12b2b5  ldloc.s  5
0x12b2b7  ldstr    aMobileofflinep_7// "MobileOfflineProfile.AnalyzeView.Commen"...
0x12b2bc  ldarg.3
0x12b2bd  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12b2c2  stfld    string Microsoft.Crm.ObjectModel.EntityView::OfflineNonAvailabilityReason
0x12b2c7  ldloc.0
0x12b2c8  ldloc.s  5
0x12b2ca  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.ObjectModel.EntityView>::Add(var<u1>)
0x12b2cf  ldloc.3
0x12b2d0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12b2d5  brtrue   loc_12B1A7
0x12b2da  leave.s  loc_12B2F0
0x12b2dc  ldloc.3
0x12b2dd  isinst   [mscorlib]System.IDisposable
0x12b2e2  stloc.s  7
0x12b2e4  ldloc.s  7
0x12b2e6  brfalse.s loc_12B2EF
0x12b2e8  ldloc.s  7
0x12b2ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12b2ef  endfinally
0x12b2f0  ldloc.0
0x12b2f1  ret
```
