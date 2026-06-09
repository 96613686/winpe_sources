# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Update

- ea: `0xd3e0`
- end: `0xd4a8`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Update`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xd3e0`
- `0xe2e0`
- `0xf550`
- `0xf7b0`
- `0xfc40`
- `0xff10`

## pseudocode

```c

```

## disassembly

```asm
0xd3e0  ldarg.1
0xd3e1  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd3e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd3eb  unbox.any [mscorlib]System.Guid
0xd3f0  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xd3f5  ldarg.2
0xd3f6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd3fb  stloc.0
0xd3fc  ldarg.0
0xd3fd  ldloc.0
0xd3fe  ldarg.2
0xd3ff  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CheckKnowledgeArticlePermission(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd404  ldarg.0
0xd405  ldloc.0
0xd406  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd40b  ldarg.2
0xd40c  ldc.i4.1
0xd40d  newarr   [mscorlib]System.String
0xd412  dup
0xd413  ldc.i4.0
0xd414  ldstr    aIsrootarticle// "isrootarticle"
0xd419  stelem.ref
0xd41a  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticleById(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string[] columns)
0xd41f  stloc.1
0xd420  ldarg.0
0xd421  ldarg.1
0xd422  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ParseUnsafeContent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0xd427  ldarg.0
0xd428  ldarg.1
0xd429  ldarg.2
0xd42a  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd42f  ldarg.1
0xd430  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle
0xd435  stloc.2
0xd436  ldloc.2
0xd437  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd43c  ldstr    aPublishon// "publishon"
0xd441  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd446  brtrue.s loc_D45A
0xd448  ldloc.2
0xd449  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd44e  ldstr    aExpirationdate// "expirationdate"
0xd453  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd458  brfalse.s loc_D480
0xd45a  ldarg.2
0xd45b  ldloc.2
0xd45c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd461  ldstr    aPublishon// "publishon"
0xd466  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd46b  ldloc.2
0xd46c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd471  ldstr    aExpirationdate// "expirationdate"
0xd476  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd47b  call     void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::RescheduleKnowledgeArticleAsyncJob(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo publishOn, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo expirationDate)
0xd480  ldloc.1
0xd481  ldstr    aIsrootarticle// "isrootarticle"
0xd486  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xd48b  brtrue.s loc_D4A7
0xd48d  ldloc.1
0xd48e  ldstr    aIsrootarticle// "isrootarticle"
0xd493  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd498  unbox.any [mscorlib]System.Boolean
0xd49d  brtrue.s loc_D4A7
0xd49f  ldarg.0
0xd4a0  ldarg.1
0xd4a1  ldarg.2
0xd4a2  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateDocumentIndexRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd4a7  ret
```
