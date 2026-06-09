# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::AssociateKnowledgeArticle

- ea: `0xccb0`
- end: `0xcdfd`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::AssociateKnowledgeArticle`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xef10`

## callees

- `0xccb0`

## string_xrefs

- `0xcdda`: `KBInvalidCreateAssociation`

## pseudocode

```c

```

## disassembly

```asm
0xccb0  ldarg.s  5
0xccb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xccb7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xccbc  ldsfld   string Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SkipAssociateFlag
0xccc1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0xccc6  brfalse  loc_CDFC
0xcccb  ldarg.s  5
0xcccd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xccd2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xccd7  ldsfld   string Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SkipAssociateFlag
0xccdc  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xcce1  unbox.any [mscorlib]System.Boolean
0xcce6  brtrue   loc_CDFC
0xcceb  ldarg.s  6
0xcced  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xccf2  brfalse.s loc_CD04
0xccf4  ldarg.s  5
0xccf6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xccfb  ldarg.2
0xccfc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xcd01  stloc.0
0xcd02  br.s     loc_CD14
0xcd04  ldarg.s  5
0xcd06  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd0b  ldarg.s  6
0xcd0d  ldc.i4.1
0xcd0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xcd13  stloc.0
0xcd14  ldloc.0
0xcd15  brtrue.s loc_CD28
0xcd17  ldc.i4   0x80040369
0xcd1c  ldc.i4.0
0xcd1d  newarr   [mscorlib]System.Object
0xcd22  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcd27  throw
0xcd28  ldloc.0
0xcd29  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0xcd2e  starg.s  6
0xcd30  ldarg.1
0xcd31  ldarg.s  6
0xcd33  ldarg.s  5
0xcd35  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd3a  stloc.1
0xcd3b  ldarg.s  4
0xcd3d  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xcd42  ldarg.s  5
0xcd44  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd49  stloc.2
0xcd4a  ldarg.0
0xcd4b  ldarg.3
0xcd4c  ldarg.s  5
0xcd4e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetAssociationEntityRelationship(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd53  ldloc.1
0xcd54  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xcd59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xcd5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::GetRelationshipInvolvingEntity(valuetype [mscorlib]System.Guid)
0xcd63  stloc.3
0xcd64  ldloc.3
0xcd65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xcd6a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0xcd6f  ldarg.s  5
0xcd71  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xcd76  stloc.s  4
0xcd78  ldloc.s  4
0xcd7a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xcd7f  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xcd84  ldc.i4.0
0xcd85  ldloc.2
0xcd86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xcd8b  box      [mscorlib]System.Guid
0xcd90  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xcd95  pop
0xcd96  ldloc.s  4
0xcd98  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xcd9d  ldloc.3
0xcd9e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingColumnName()
0xcda3  ldc.i4.0
0xcda4  ldarg.1
0xcda5  box      [mscorlib]System.Guid
0xcdaa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xcdaf  pop
0xcdb0  ldarg.0
0xcdb1  ldloc.s  4
0xcdb3  ldarg.s  5
0xcdb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcdba  stloc.s  5
0xcdbc  ldloc.s  5
0xcdbe  brfalse.s loc_CDD5
0xcdc0  ldloc.s  5
0xcdc2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xcdc7  brtrue.s loc_CDD5
0xcdc9  ldarg.0
0xcdca  ldloc.1
0xcdcb  ldloc.2
0xcdcc  ldarg.3
0xcdcd  ldarg.s  5
0xcdcf  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::AssociateEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcdd4  ret
0xcdd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcdda  ldstr    aKbinvalidcreat// "KBInvalidCreateAssociation"
0xcddf  ldarg.s  5
0xcde1  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcde6  ldc.i4.0
0xcde7  newarr   [mscorlib]System.Object
0xcdec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcdf1  ldc.i4   0x80060861
0xcdf6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xcdfb  throw
0xcdfc  ret
```
