# Microsoft.Crm.Metadata.SavedQueryHelper::CreateView

- ea: `0x5c6e0`
- end: `0x5c87f`
- name: `Microsoft.Crm.Metadata.SavedQueryHelper::CreateView`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5c520`
- `0x5c620`
- `0x5c680`

## callees

- `0x2cd30`
- `0x2d530`
- `0x5c6e0`
- `0x5cce0`
- `0x5ce40`
- `0x5d1a0`
- `0x5d960`

## string_xrefs

- `0x5c809`: `fetchxml`
- `0x5c821`: `layoutxml`
- `0x5c798`: `canbedeleted`

## pseudocode

```c

```

## disassembly

```asm
0x5c6e0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x5c6e5  ldarg.s  4
0x5c6e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5c6ec  ldarg.s  4
0x5c6ee  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x5c6f3  stloc.0
0x5c6f4  ldarg.0
0x5c6f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x5c6fa  stloc.1
0x5c6fb  ldarg.s  4
0x5c6fd  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c702  stloc.2
0x5c703  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5c708  stloc.3
0x5c709  ldloc.2
0x5c70a  ldstr    aSavedqueryid// "savedqueryid"
0x5c70f  ldloc.3
0x5c710  box      [mscorlib]System.Guid
0x5c715  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c71a  ldarg.0
0x5c71b  ldarg.1
0x5c71c  ldloc.3
0x5c71d  ldstr    aDisplayname// "DisplayName"
0x5c722  ldarg.s  4
0x5c724  ldarg.s  5
0x5c726  ldarg.s  6
0x5c728  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.SavedQueryHelper::GenerateViewName(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, valuetype SystemViewType view, valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata bpfPrimaryEntityMetadata, [opt] bool isBPFSpecificView)
0x5c72d  ldloc.0
0x5c72e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x5c733  ldarg.s  4
0x5c735  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c73a  stloc.s  4
0x5c73c  ldloc.2
0x5c73d  ldstr    aName// "name"
0x5c742  ldloc.s  4
0x5c744  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c749  ldloc.2
0x5c74a  ldstr    aReturnedtypeco// "returnedtypecode"
0x5c74f  ldloc.1
0x5c750  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x5c755  box      [mscorlib]System.Int32
0x5c75a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c75f  ldloc.2
0x5c760  ldstr    aQuerytype// "querytype"
0x5c765  ldarg.1
0x5c766  call     int32 Microsoft.Crm.Metadata.SavedQueryHelper::GetQueryType(valuetype SystemViewType view)
0x5c76b  box      [mscorlib]System.Int32
0x5c770  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c775  ldloc.2
0x5c776  ldstr    aIsdefault// "isdefault"
0x5c77b  ldarg.2
0x5c77c  box      [mscorlib]System.Boolean
0x5c781  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c786  ldloc.2
0x5c787  ldstr    aIscustomizable// "iscustomizable"
0x5c78c  ldarg.3
0x5c78d  box      [mscorlib]System.Boolean
0x5c792  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c797  ldloc.2
0x5c798  ldstr    aCanbedeleted// "canbedeleted"
0x5c79d  ldc.i4.0
0x5c79e  box      [mscorlib]System.Boolean
0x5c7a3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c7a8  ldarg.s  4
0x5c7aa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c7af  ldloc.2
0x5c7b0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5c7b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x5c7ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x5c7bf  ldstr    aIscustom// "iscustom"
0x5c7c4  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5c7c9  brfalse.s loc_5C7EA
0x5c7cb  ldloc.2
0x5c7cc  ldstr    aIscustom// "iscustom"
0x5c7d1  ldarg.0
0x5c7d2  brfalse.s loc_5C7DC
0x5c7d4  ldarg.0
0x5c7d5  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x5c7da  brtrue.s loc_5C7DF
0x5c7dc  ldc.i4.0
0x5c7dd  br.s     loc_5C7E0
0x5c7df  ldc.i4.1
0x5c7e0  box      [mscorlib]System.Boolean
0x5c7e5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c7ea  ldloc.2
0x5c7eb  ldstr    aIsquickfindque// "isquickfindquery"
0x5c7f0  ldc.i4.3
0x5c7f1  ldarg.1
0x5c7f2  ceq
0x5c7f4  box      [mscorlib]System.Boolean
0x5c7f9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c7fe  ldarg.1
0x5c7ff  ldc.i4.6
0x5c800  beq.s    loc_5C805
0x5c802  ldc.i4.0
0x5c803  br.s     loc_5C806
0x5c805  ldc.i4.1
0x5c806  stloc.s  5
0x5c808  ldloc.2
0x5c809  ldstr    aFetchxml// "fetchxml"
0x5c80e  ldarg.0
0x5c80f  ldarg.1
0x5c810  ldloc.s  5
0x5c812  ldarg.s  5
0x5c814  ldarg.s  6
0x5c816  call     string Microsoft.Crm.Metadata.SavedQueryHelper::GenerateFetchXml(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, valuetype SystemViewType view, bool fetchDistinct, [opt] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata bpfPrimaryEntityMetadata, [opt] bool isBPFSpecificView)
0x5c81b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c820  ldloc.2
0x5c821  ldstr    aLayoutxml_0// "layoutxml"
0x5c826  ldarg.0
0x5c827  ldarg.1
0x5c828  ldarg.s  5
0x5c82a  call     string Microsoft.Crm.Metadata.SavedQueryHelper::GenerateLayoutXml(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, valuetype SystemViewType view, [opt] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata bpfPrimaryEntityMetadata)
0x5c82f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c834  ldarg.s  4
0x5c836  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c83b  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x5c840  brfalse.s loc_5C850
0x5c842  ldarg.s  4
0x5c844  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c849  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x5c84e  br.s     loc_5C855
0x5c850  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x5c855  stloc.s  6
0x5c857  ldloc.2
0x5c858  ldstr    aSolutionid// "solutionid"
0x5c85d  ldloc.s  6
0x5c85f  box      [mscorlib]System.Guid
0x5c864  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c869  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x5c86e  ldc.i4.0
0x5c86f  stloc.s  7
0x5c871  ldloc.2
0x5c872  ldarg.s  4
0x5c874  ldnull
0x5c875  ldc.i4.0
0x5c876  ldloc.s  7
0x5c878  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache, bool, bool)
0x5c87d  ldloc.3
0x5c87e  ret
```
