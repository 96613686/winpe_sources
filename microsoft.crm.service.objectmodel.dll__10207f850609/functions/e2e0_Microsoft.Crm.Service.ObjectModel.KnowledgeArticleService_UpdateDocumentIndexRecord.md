# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateDocumentIndexRecord

- ea: `0xe2e0`
- end: `0xe45d`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateDocumentIndexRecord`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xd3e0`

## callees

- `0x61a0`
- `0xe2e0`
- `0xe460`
- `0xf770`

## pseudocode

```c

```

## disassembly

```asm
0xe2e0  ldarg.2
0xe2e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe2e6  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0xe2eb  stloc.0
0xe2ec  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0xe2f1  stloc.1
0xe2f2  ldloc.0
0xe2f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xe2f8  ldarg.2
0xe2f9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe2fe  stloc.2
0xe2ff  ldloc.2
0xe300  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0xe305  ldloc.0
0xe306  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xe30b  ldarg.2
0xe30c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xe311  ldloc.2
0xe312  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0xe317  ldloc.0
0xe318  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xe31d  ldarg.2
0xe31e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe323  stloc.3
0xe324  ldloc.3
0xe325  ldstr    aDocumentid// "documentid"
0xe32a  ldc.i4.0
0xe32b  ldarg.1
0xe32c  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xe331  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe336  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xe33b  pop
0xe33c  ldloc.1
0xe33d  ldloc.3
0xe33e  ldloc.2
0xe33f  ldarg.2
0xe340  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe345  dup
0xe346  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe34b  ldc.i4.1
0xe34c  beq.s    loc_E363
0xe34e  ldc.i4   0x80042C05
0xe353  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xe358  ldc.i4   0x80042C05
0xe35d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe362  throw
0xe363  ldc.i4.0
0xe364  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xe369  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex
0xe36e  stloc.0
0xe36f  ldarg.0
0xe370  ldarg.1
0xe371  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xe376  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe37b  unbox.any [mscorlib]System.Guid
0xe380  ldarg.2
0xe381  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticleById(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe386  stloc.s  4
0xe388  ldloc.0
0xe389  ldstr    aSearchtext// "searchtext"
0xe38e  ldstr    a01234// "{0} {1} {2} {3} {4}"
0xe393  ldc.i4.5
0xe394  newarr   [mscorlib]System.Object
0xe399  dup
0xe39a  ldc.i4.0
0xe39b  ldarg.0
0xe39c  ldloc.s  4
0xe39e  ldstr    aContent// "content"
0xe3a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe3a8  castclass [mscorlib]System.String
0xe3ad  call     instance string Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SanitizeExtractedSearchTextFromHtml(string html)
0xe3b2  stelem.ref
0xe3b3  dup
0xe3b4  ldc.i4.1
0xe3b5  ldloc.s  4
0xe3b7  ldstr    aTitle// "title"
0xe3bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe3c1  castclass [mscorlib]System.String
0xe3c6  stelem.ref
0xe3c7  dup
0xe3c8  ldc.i4.2
0xe3c9  ldarg.1
0xe3ca  ldstr    aKeywords// "keywords"
0xe3cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe3d4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe3d9  beq.s    loc_E3ED
0xe3db  ldarg.1
0xe3dc  ldstr    aKeywords// "keywords"
0xe3e1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe3e6  castclass [mscorlib]System.String
0xe3eb  br.s     loc_E3F2
0xe3ed  ldstr    asc_1EEAE// ""
0xe3f2  stelem.ref
0xe3f3  dup
0xe3f4  ldc.i4.3
0xe3f5  ldloc.s  4
0xe3f7  ldstr    aArticlepublicn// "articlepublicnumber"
0xe3fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe401  castclass [mscorlib]System.String
0xe406  stelem.ref
0xe407  dup
0xe408  ldc.i4.4
0xe409  ldarg.1
0xe40a  ldstr    aDescription// "description"
0xe40f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe414  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe419  beq.s    loc_E42D
0xe41b  ldarg.1
0xe41c  ldstr    aDescription// "description"
0xe421  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe426  castclass [mscorlib]System.String
0xe42b  br.s     loc_E432
0xe42d  ldstr    asc_1EEAE// ""
0xe432  stelem.ref
0xe433  call     string [mscorlib]System.String::Format(string, object[])
0xe438  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe43d  ldloc.0
0xe43e  ldstr    aIslatestversio// "islatestversion"
0xe443  ldloc.s  4
0xe445  ldstr    aIslatestversio// "islatestversion"
0xe44a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe44f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe454  ldloc.1
0xe455  ldloc.0
0xe456  ldarg.2
0xe457  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe45c  ret
```
