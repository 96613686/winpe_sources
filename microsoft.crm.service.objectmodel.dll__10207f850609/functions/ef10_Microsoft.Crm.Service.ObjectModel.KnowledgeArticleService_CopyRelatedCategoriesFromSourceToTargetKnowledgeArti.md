# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedCategoriesFromSourceToTargetKnowledgeArticle

- ea: `0xef10`
- end: `0xf01d`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedCategoriesFromSourceToTargetKnowledgeArticle`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd6f0`
- `0xdca0`

## callees

- `0xccb0`
- `0xce00`
- `0xef10`

## pseudocode

```c

```

## disassembly

```asm
0xef10  ldstr    aKnowledgeartic_2// "KnowledgeArticlesCategories"
0xef15  ldarg.s  4
0xef17  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xef1c  stloc.0
0xef1d  ldloc.0
0xef1e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xef23  ldc.i4.3
0xef24  newarr   [mscorlib]System.String
0xef29  dup
0xef2a  ldc.i4.0
0xef2b  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xef30  stelem.ref
0xef31  dup
0xef32  ldc.i4.1
0xef33  ldstr    aCategoryid// "categoryid"
0xef38  stelem.ref
0xef39  dup
0xef3a  ldc.i4.2
0xef3b  ldstr    aKnowledgeartic_3// "knowledgearticlecategoryid"
0xef40  stelem.ref
0xef41  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xef46  ldloc.0
0xef47  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xef4c  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xef51  ldc.i4.0
0xef52  ldarg.1
0xef53  box      [mscorlib]System.Guid
0xef58  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xef5d  pop
0xef5e  ldarg.0
0xef5f  ldloc.0
0xef60  ldarg.s  4
0xef62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xef67  stloc.1
0xef68  ldloc.1
0xef69  brfalse  loc_F01C
0xef6e  ldloc.1
0xef6f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xef74  ldc.i4.0
0xef75  ble      loc_F01C
0xef7a  ldarg.s  4
0xef7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xef81  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xef86  ldsfld   string Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SkipAssociateFlag
0xef8b  ldc.i4.0
0xef8c  box      [mscorlib]System.Boolean
0xef91  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xef96  ldloc.1
0xef97  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xef9c  stloc.2
0xef9d  br.s     loc_EFFE
0xef9f  ldloc.2
0xefa0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xefa5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xefaa  stloc.3
0xefab  ldarg.3
0xefac  brfalse.s loc_EFD6
0xefae  ldarg.0
0xefaf  ldloc.3
0xefb0  ldstr    aCategoryid// "categoryid"
0xefb5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xefba  unbox.any [mscorlib]System.Guid
0xefbf  ldc.i4   0x26E7
0xefc4  ldstr    aKnowledgeartic_4// "knowledgearticle_category"
0xefc9  ldarg.2
0xefca  ldarg.s  4
0xefcc  ldstr    asc_1EEAE// ""
0xefd1  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::DisassociateKnowledgeArticle(valuetype [mscorlib]System.Guid regardingObjectId, int32 regardingObjectTypeCode, string associationRelationshipName, valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] string entityName)
0xefd6  ldarg.0
0xefd7  ldloc.3
0xefd8  ldstr    aCategoryid// "categoryid"
0xefdd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xefe2  unbox.any [mscorlib]System.Guid
0xefe7  ldc.i4   0x26E7
0xefec  ldstr    aKnowledgeartic_4// "knowledgearticle_category"
0xeff1  ldarg.2
0xeff2  ldarg.s  4
0xeff4  ldstr    asc_1EEAE// ""
0xeff9  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::AssociateKnowledgeArticle(valuetype [mscorlib]System.Guid regardingObjectId, int32 regardingObjectTypeCode, string associationRelationshipName, valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] string entityName)
0xeffe  ldloc.2
0xefff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf004  brtrue.s loc_EF9F
0xf006  leave.s  loc_F01C
0xf008  ldloc.2
0xf009  isinst   [mscorlib]System.IDisposable
0xf00e  stloc.s  4
0xf010  ldloc.s  4
0xf012  brfalse.s loc_F01B
0xf014  ldloc.s  4
0xf016  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf01b  endfinally
0xf01c  ret
```
