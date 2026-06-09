# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKbArticlesByDocumentIndexes

- ea: `0xe500`
- end: `0xe748`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKbArticlesByDocumentIndexes`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xcbe0`

## callees

- `0xe500`
- `0xe750`
- `0xe8c0`

## pseudocode

```c

```

## disassembly

```asm
0xe500  ldc.i4.0
0xe501  stloc.1
0xe502  ldarg.s  4
0xe504  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xe509  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::get_Orders()
0xe50e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xe513  brfalse.s loc_E518
0xe515  ldc.i4.0
0xe516  br.s     loc_E519
0xe518  ldc.i4.1
0xe519  stloc.2
0xe51a  ldarg.1
0xe51b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe520  brtrue.s loc_E540
0xe522  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xe527  ldarg.s  5
0xe529  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe52e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0xe533  stloc.0
0xe534  ldloc.0
0xe535  ldc.i4.0
0xe536  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0xe53b  br       loc_E73F
0xe540  newobj   instance void [Microsoft.Crm]Microsoft.Crm.GuidSet::.ctor()
0xe545  stloc.3
0xe546  ldarg.1
0xe547  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xe54c  stloc.s  6
0xe54e  br.s     loc_E575
0xe550  ldloc.s  6
0xe552  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe557  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xe55c  stloc.s  7
0xe55e  ldloc.3
0xe55f  ldloc.s  7
0xe561  ldstr    aDocumentid// "documentid"
0xe566  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe56b  unbox.any [mscorlib]System.Guid
0xe570  callvirt instance void [Microsoft.Crm]Microsoft.Crm.GuidSet::Add(valuetype [mscorlib]System.Guid)
0xe575  ldloc.s  6
0xe577  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe57c  brtrue.s loc_E550
0xe57e  leave.s  loc_E595
0xe580  ldloc.s  6
0xe582  isinst   [mscorlib]System.IDisposable
0xe587  stloc.s  8
0xe589  ldloc.s  8
0xe58b  brfalse.s loc_E594
0xe58d  ldloc.s  8
0xe58f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe594  endfinally
0xe595  ldarg.s  4
0xe597  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xe59c  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xe5a1  ldc.i4.8
0xe5a2  ldloc.3
0xe5a3  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm]Microsoft.Crm.GuidSet::ToArray()
0xe5a8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xe5ad  pop
0xe5ae  ldarg.3
0xe5af  ldc.i4.m1
0xe5b0  ble.s    loc_E5F6
0xe5b2  ldarg.3
0xe5b3  ldc.i4.1
0xe5b4  beq.s    loc_E5BA
0xe5b6  ldarg.3
0xe5b7  ldc.i4.2
0xe5b8  bne.un.s loc_E5DD
0xe5ba  ldarg.s  4
0xe5bc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xe5c1  ldstr    aStatecode// "statecode"
0xe5c6  ldc.i4.8
0xe5c7  ldc.i4.2
0xe5c8  newarr   [mscorlib]System.Int32
0xe5cd  dup
0xe5ce  ldc.i4.0
0xe5cf  ldc.i4.1
0xe5d0  stelem.i4
0xe5d1  dup
0xe5d2  ldc.i4.1
0xe5d3  ldc.i4.2
0xe5d4  stelem.i4
0xe5d5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xe5da  pop
0xe5db  br.s     loc_E5F6
0xe5dd  ldarg.s  4
0xe5df  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xe5e4  ldstr    aStatecode// "statecode"
0xe5e9  ldc.i4.0
0xe5ea  ldarg.3
0xe5eb  box      [mscorlib]System.Int32
0xe5f0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xe5f5  pop
0xe5f6  ldarg.s  4
0xe5f8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe5fd  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_Count()
0xe602  stloc.s  4
0xe604  ldarg.s  4
0xe606  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe60b  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0xe610  stloc.s  5
0xe612  ldloc.2
0xe613  ldarg.2
0xe614  or
0xe615  brfalse.s loc_E631
0xe617  ldarg.s  4
0xe619  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe61e  ldc.i4.0
0xe61f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_Count(int32)
0xe624  ldarg.s  4
0xe626  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe62b  ldc.i4.0
0xe62c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0xe631  ldarg.0
0xe632  ldarg.s  4
0xe634  ldarg.s  5
0xe636  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe63b  stloc.0
0xe63c  ldarg.s  5
0xe63e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe643  ldc.i4.s 0x1A
0xe645  ldstr    a0// "{0}"
0xe64a  ldc.i4.1
0xe64b  newarr   [mscorlib]System.Object
0xe650  dup
0xe651  ldc.i4.0
0xe652  ldstr    aArticlesRetrie// "Articles retrieved based on search text"...
0xe657  stelem.ref
0xe658  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe65d  ldloc.0
0xe65e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_TotalRecordCount()
0xe663  stloc.1
0xe664  ldarg.2
0xe665  brfalse.s loc_E691
0xe667  ldarg.3
0xe668  ldc.i4.m1
0xe669  ble.s    loc_E691
0xe66b  ldarg.0
0xe66c  ldloc.0
0xe66d  ldarg.s  5
0xe66f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ReturnUniqueArticles(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection articles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe674  stloc.0
0xe675  ldloc.0
0xe676  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe67b  ldc.i4   0xFA
0xe680  ble.s    loc_E68A
0xe682  ldc.i4   0xFA
0xe687  stloc.1
0xe688  br.s     loc_E691
0xe68a  ldloc.0
0xe68b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe690  stloc.1
0xe691  ldloc.s  5
0xe693  ldc.i4.0
0xe694  bgt.s    loc_E699
0xe696  ldc.i4.1
0xe697  stloc.s  5
0xe699  ldloc.2
0xe69a  brfalse.s loc_E6A7
0xe69c  ldarg.0
0xe69d  ldarg.1
0xe69e  ldloc.0
0xe69f  ldarg.s  5
0xe6a1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ReturnArticlesByRelevance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection documentIndexEntities, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection knowledgeArticles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe6a6  stloc.0
0xe6a7  ldloc.2
0xe6a8  ldarg.2
0xe6a9  or
0xe6aa  brfalse  loc_E73F
0xe6af  ldloc.s  5
0xe6b1  ldc.i4.1
0xe6b2  beq.s    loc_E6BD
0xe6b4  ldloc.s  4
0xe6b6  ldloc.s  5
0xe6b8  ldc.i4.1
0xe6b9  sub
0xe6ba  mul
0xe6bb  br.s     loc_E6BE
0xe6bd  ldc.i4.0
0xe6be  stloc.s  9
0xe6c0  ldarg.s  4
0xe6c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe6c7  ldloc.s  4
0xe6c9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_Count(int32)
0xe6ce  ldloc.0
0xe6cf  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe6d4  ldc.i4.0
0xe6d5  blt.s    loc_E73F
0xe6d7  ldloc.s  9
0xe6d9  ldloc.0
0xe6da  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe6df  bge.s    loc_E73F
0xe6e1  ldloc.s  9
0xe6e3  ldloc.s  4
0xe6e5  add
0xe6e6  ldloc.0
0xe6e7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe6ec  blt.s    loc_E6F6
0xe6ee  ldloc.0
0xe6ef  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe6f4  br.s     loc_E6FB
0xe6f6  ldloc.s  9
0xe6f8  ldloc.s  4
0xe6fa  add
0xe6fb  stloc.s  0xA
0xe6fd  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xe702  ldarg.s  5
0xe704  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe709  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0xe70e  stloc.s  0xB
0xe710  ldloc.s  9
0xe712  stloc.s  0xC
0xe714  br.s     loc_E736
0xe716  ldloc.s  0xB
0xe718  ldloc.0
0xe719  ldloc.s  0xC
0xe71b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xe720  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xe725  pop
0xe726  ldloc.s  0xB
0xe728  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe72d  ldloc.1
0xe72e  bge.s    loc_E73C
0xe730  ldloc.s  0xC
0xe732  ldc.i4.1
0xe733  add
0xe734  stloc.s  0xC
0xe736  ldloc.s  0xC
0xe738  ldloc.s  0xA
0xe73a  blt.s    loc_E716
0xe73c  ldloc.s  0xB
0xe73e  stloc.0
0xe73f  ldloc.0
0xe740  ldloc.1
0xe741  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0xe746  ldloc.0
0xe747  ret
```
