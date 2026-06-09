# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::IncrementKnowledgeArticleViewCount

- ea: `0x10340`
- end: `0x10467`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::IncrementKnowledgeArticleViewCount`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x10340`
- `0x10470`
- `0x104e0`

## string_xrefs

- `0x10358`: `prvReadKnowledgeArticle`
- `0x10381`: `knowledgearticleviewsid`
- `0x1041d`: `knowledgearticleviewsid`

## pseudocode

```c

```

## disassembly

```asm
0x10340  ldarg.s  5
0x10342  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x10347  ldarg.s  5
0x10349  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1034e  ldstr    aKnowledgeartic// "KnowledgeArticle"
0x10353  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x10358  ldstr    aPrvreadknowled// "prvReadKnowledgeArticle"
0x1035d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x10362  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x10367  ldarg.s  5
0x10369  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1036e  ldstr    aKnowledgeartic_7// "KnowledgeArticleViews"
0x10373  ldarg.s  5
0x10375  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1037a  stloc.0
0x1037b  ldloc.0
0x1037c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x10381  ldstr    aKnowledgeartic_8// "knowledgearticleviewsid"
0x10386  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1038b  ldloc.0
0x1038c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x10391  ldstr    aKnowledgeartic_9// "knowledgearticleview"
0x10396  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1039b  ldloc.0
0x1039c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x103a1  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0x103a6  ldc.i4.0
0x103a7  ldarg.1
0x103a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x103ad  box      [mscorlib]System.Guid
0x103b2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x103b7  pop
0x103b8  ldloc.0
0x103b9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x103be  ldstr    aViewdate// "viewdate"
0x103c3  ldc.i4.0
0x103c4  ldarga.s 2
0x103c6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x103cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x103d0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x103d5  pop
0x103d6  ldloc.0
0x103d7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x103dc  ldstr    aLocation// "location"
0x103e1  ldc.i4.0
0x103e2  ldarg.3
0x103e3  box      [mscorlib]System.Int32
0x103e8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x103ed  pop
0x103ee  ldarg.0
0x103ef  ldloc.0
0x103f0  ldarg.s  5
0x103f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x103f7  stloc.1
0x103f8  ldloc.1
0x103f9  brfalse.s loc_1043F
0x103fb  ldloc.1
0x103fc  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10401  ldc.i4.0
0x10402  ble.s    loc_1043F
0x10404  ldloc.1
0x10405  ldc.i4.0
0x10406  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1040b  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticleViews
0x10410  stloc.2
0x10411  ldarg.0
0x10412  ldarg.s  5
0x10414  ldloc.2
0x10415  ldarg.s  4
0x10417  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::IncrementKnowledgeArticleViewCountId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticleViews knowledgeArticleView, int32 count)
0x1041c  ldloc.2
0x1041d  ldstr    aKnowledgeartic_8// "knowledgearticleviewsid"
0x10422  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10427  unbox.any [mscorlib]System.Guid
0x1042c  stloc.3
0x1042d  ldloc.2
0x1042e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x10433  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10438  ldloc.3
0x10439  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1043e  ret
0x1043f  ldarg.0
0x10440  ldarg.1
0x10441  ldarg.2
0x10442  ldarg.3
0x10443  ldarg.s  4
0x10445  ldarg.s  5
0x10447  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::CreateKnowledgeArticleViewId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference source, valuetype [mscorlib]System.DateTime viewDate, int32 location, int32 count, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1044c  stloc.s  4
0x1044e  ldloc.s  4
0x10450  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x10455  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1045a  ldloc.s  4
0x1045c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x10461  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x10466  ret
```
