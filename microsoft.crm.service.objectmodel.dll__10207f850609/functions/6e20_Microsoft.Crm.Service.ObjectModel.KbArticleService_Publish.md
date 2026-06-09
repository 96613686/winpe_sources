# Microsoft.Crm.Service.ObjectModel.KbArticleService::Publish

- ea: `0x6e20`
- end: `0x70fd`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::Publish`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x61a0`
- `0x6e20`
- `0x7100`
- `0x7420`

## string_xrefs

- `0x6ee1`: `kbarticletemplateid`
- `0x6f2e`: `kbarticletemplateid`
- `0x6f53`: `kbarticletemplateid`
- `0x6f15`: `kbarticletemplate`
- `0x6f36`: `formatxml`
- `0x6f3e`: `structurexml`

## pseudocode

```c

```

## disassembly

```asm
0x6e20  ldarg.1
0x6e21  ldstr    aStatecode// "statecode"
0x6e26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e2b  unbox.any [mscorlib]System.Int32
0x6e30  ldc.i4.2
0x6e31  beq.s    loc_6E8C
0x6e33  ldarg.1
0x6e34  ldstr    aStatecode// "statecode"
0x6e39  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e3e  unbox.any [mscorlib]System.Int32
0x6e43  ldc.i4.3
0x6e44  bne.un.s loc_6E57
0x6e46  ldc.i4   0x80048DFB
0x6e4b  ldc.i4.0
0x6e4c  newarr   [mscorlib]System.Object
0x6e51  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6e56  throw
0x6e57  ldarg.1
0x6e58  ldstr    aStatecode// "statecode"
0x6e5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e62  unbox.any [mscorlib]System.Int32
0x6e67  ldc.i4.1
0x6e68  bne.un.s loc_6E7B
0x6e6a  ldc.i4   0x80048DFD
0x6e6f  ldc.i4.0
0x6e70  newarr   [mscorlib]System.Object
0x6e75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6e7a  throw
0x6e7b  ldc.i4   0x800404FC
0x6e80  ldc.i4.0
0x6e81  newarr   [mscorlib]System.Object
0x6e86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6e8b  throw
0x6e8c  ldarg.2
0x6e8d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x6e92  ldarg.2
0x6e93  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e98  ldarg.0
0x6e99  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x6e9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x6ea3  ldc.i4.2
0x6ea4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x6ea9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x6eae  ldarg.2
0x6eaf  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6eb4  ldarg.2
0x6eb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x6eba  ldarg.2
0x6ebb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ec0  ldarg.0
0x6ec1  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x6ec6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x6ecb  ldstr    aPrvpublisharti// "prvPublishArticle"
0x6ed0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x6ed5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x6eda  ldarg.2
0x6edb  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ee0  ldarg.1
0x6ee1  ldstr    aKbarticletempl// "kbarticletemplateid"
0x6ee6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x6eeb  brfalse.s loc_6F02
0x6eed  ldc.i4   0x800404FA
0x6ef2  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x6ef7  ldc.i4   0x800404FA
0x6efc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6f01  throw
0x6f02  ldarg.2
0x6f03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6f08  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate::.ctor(valuetype [mscorlib]System.Guid)
0x6f0d  stloc.0
0x6f0e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x6f13  stloc.1
0x6f14  ldloc.1
0x6f15  ldstr    aKbarticletempl_0// "kbarticletemplate"
0x6f1a  ldarg.2
0x6f1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6f20  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Sdk.ColumnSetHelper::AddPrimaryKey(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, string, valuetype [mscorlib]System.Guid)
0x6f25  ldloc.1
0x6f26  ldc.i4.3
0x6f27  newarr   [mscorlib]System.String
0x6f2c  dup
0x6f2d  ldc.i4.0
0x6f2e  ldstr    aKbarticletempl// "kbarticletemplateid"
0x6f33  stelem.ref
0x6f34  dup
0x6f35  ldc.i4.1
0x6f36  ldstr    aFormatxml// "formatxml"
0x6f3b  stelem.ref
0x6f3c  dup
0x6f3d  ldc.i4.2
0x6f3e  ldstr    aStructurexml// "structurexml"
0x6f43  stelem.ref
0x6f44  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x6f49  ldarg.2
0x6f4a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6f4f  stloc.s  5
0x6f51  ldarg.0
0x6f52  ldarg.1
0x6f53  ldstr    aKbarticletempl// "kbarticletemplateid"
0x6f58  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6f5d  unbox.any [mscorlib]System.Guid
0x6f62  ldloc.0
0x6f63  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6f68  ldarg.2
0x6f69  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f6e  ldloc.0
0x6f6f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6f74  ldloc.1
0x6f75  ldarg.2
0x6f76  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6f7b  ldarg.2
0x6f7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6f81  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate
0x6f86  stloc.0
0x6f87  leave.s  loc_6F95
0x6f89  ldloc.s  5
0x6f8b  brfalse.s loc_6F94
0x6f8d  ldloc.s  5
0x6f8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f94  endfinally
0x6f95  ldarg.1
0x6f96  ldstr    aContent// "content"
0x6f9b  ldarg.0
0x6f9c  ldarg.1
0x6f9d  ldloc.0
0x6f9e  call     instance string Microsoft.Crm.Service.ObjectModel.KbArticleService::GetStaticHtml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity article, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate template)
0x6fa3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6fa8  ldarg.1
0x6fa9  ldstr    aStatecode// "statecode"
0x6fae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x6fb3  ldarg.0
0x6fb4  ldarg.1
0x6fb5  ldarg.2
0x6fb6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6fbb  ldarg.2
0x6fbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6fc1  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0x6fc6  stloc.2
0x6fc7  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0x6fcc  ldloc.2
0x6fcd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6fd2  ldarg.2
0x6fd3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6fd8  stloc.3
0x6fd9  ldloc.3
0x6fda  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x6fdf  ldloc.2
0x6fe0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6fe5  ldarg.2
0x6fe6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6feb  ldloc.3
0x6fec  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x6ff1  ldloc.2
0x6ff2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6ff7  ldarg.2
0x6ff8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ffd  stloc.s  4
0x6fff  ldloc.s  4
0x7001  ldstr    aDocumentid// "documentid"
0x7006  ldc.i4.0
0x7007  ldarg.1
0x7008  ldstr    aKbarticleid// "kbarticleid"
0x700d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7012  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x7017  pop
0x7018  dup
0x7019  ldloc.s  4
0x701b  ldloc.3
0x701c  ldarg.2
0x701d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7022  dup
0x7023  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7028  ldc.i4.1
0x7029  beq.s    loc_7040
0x702b  ldc.i4   0x80042C05
0x7030  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x7035  ldc.i4   0x80042C05
0x703a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x703f  throw
0x7040  ldc.i4.0
0x7041  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x7046  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex
0x704b  stloc.2
0x704c  ldloc.2
0x704d  ldstr    aSearchtext// "searchtext"
0x7052  ldarg.0
0x7053  ldarg.1
0x7054  ldstr    aContent// "content"
0x7059  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x705e  castclass [mscorlib]System.String
0x7063  call     instance string Microsoft.Crm.Service.ObjectModel.KbArticleService::ExtractSearchTextFromHtml(string html)
0x7068  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x706d  ldloc.2
0x706e  ldstr    aIspublished// "ispublished"
0x7073  ldc.i4.1
0x7074  box      [mscorlib]System.Boolean
0x7079  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x707e  ldloc.2
0x707f  ldstr    aSubjectid// "subjectid"
0x7084  ldarg.1
0x7085  ldstr    aSubjectid// "subjectid"
0x708a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x708f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7094  ldloc.2
0x7095  ldstr    aTitle// "title"
0x709a  ldarg.1
0x709b  ldstr    aTitle// "title"
0x70a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70a5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x70aa  ldloc.2
0x70ab  ldstr    aNumber// "number"
0x70b0  ldarg.1
0x70b1  ldstr    aNumber// "number"
0x70b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70bb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x70c0  ldloc.2
0x70c1  ldstr    aKeywords// "keywords"
0x70c6  ldarg.1
0x70c7  ldstr    aKeywords// "keywords"
0x70cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70d1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x70d6  ldloc.2
0x70d7  ldarg.2
0x70d8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x70dd  ldarg.0
0x70de  ldarg.1
0x70df  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x70e4  unbox.any [mscorlib]System.Guid
0x70e9  ldstr    aKbarticle// "KbArticle"
0x70ee  ldarg.2
0x70ef  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x70f4  ldc.i4.3
0x70f5  ldc.i4.m1
0x70f6  ldarg.2
0x70f7  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x70fc  ret
```
