# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetRemainingPublishedVersionsToArchived

- ea: `0xf8c0`
- end: `0xfa7f`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetRemainingPublishedVersionsToArchived`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1c0`

## callees

- `0xf730`
- `0xf8c0`

## string_xrefs

- `0xfa09`: `Knowledge Article with Article Id {0}, public number {1} and version {2}.{3} moved to archived state.`

## pseudocode

```c

```

## disassembly

```asm
0xf8c0  ldc.i4.5
0xf8c1  newarr   [mscorlib]System.String
0xf8c6  dup
0xf8c7  ldc.i4.0
0xf8c8  ldstr    aArticlepublicn// "articlepublicnumber"
0xf8cd  stelem.ref
0xf8ce  dup
0xf8cf  ldc.i4.1
0xf8d0  ldstr    aLanguagelocale// "languagelocaleid"
0xf8d5  stelem.ref
0xf8d6  dup
0xf8d7  ldc.i4.2
0xf8d8  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xf8dd  stelem.ref
0xf8de  dup
0xf8df  ldc.i4.3
0xf8e0  ldstr    aMajorversionnu// "majorversionnumber"
0xf8e5  stelem.ref
0xf8e6  dup
0xf8e7  ldc.i4.4
0xf8e8  ldstr    aMinorversionnu// "minorversionnumber"
0xf8ed  stelem.ref
0xf8ee  stloc.0
0xf8ef  ldarg.0
0xf8f0  ldarg.1
0xf8f1  ldarg.0
0xf8f2  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xf8f7  ldarg.2
0xf8f8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf8fd  ldloc.0
0xf8fe  ldarg.2
0xf8ff  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticle(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, string[] columnSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf904  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle
0xf909  stloc.1
0xf90a  ldloc.1
0xf90b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xf910  ldarg.2
0xf911  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xf916  stloc.2
0xf917  ldloc.2
0xf918  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xf91d  ldloc.0
0xf91e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xf923  ldloc.2
0xf924  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf929  ldstr    aArticlepublicn// "articlepublicnumber"
0xf92e  ldc.i4.0
0xf92f  ldloc.1
0xf930  ldstr    aArticlepublicn// "articlepublicnumber"
0xf935  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf93a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf93f  pop
0xf940  ldloc.2
0xf941  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf946  ldstr    aLanguagelocale// "languagelocaleid"
0xf94b  ldc.i4.0
0xf94c  ldloc.1
0xf94d  ldstr    aLanguagelocale// "languagelocaleid"
0xf952  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf957  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf95c  pop
0xf95d  ldloc.2
0xf95e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf963  ldstr    aStatecode// "statecode"
0xf968  ldc.i4.0
0xf969  ldc.i4.3
0xf96a  box      [mscorlib]System.Int32
0xf96f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf974  pop
0xf975  ldloc.2
0xf976  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf97b  ldstr    aIsrootarticle// "isrootarticle"
0xf980  ldc.i4.0
0xf981  ldc.i4.0
0xf982  box      [mscorlib]System.Boolean
0xf987  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf98c  pop
0xf98d  ldloc.2
0xf98e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf993  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xf998  ldc.i4.1
0xf999  ldarg.1
0xf99a  box      [mscorlib]System.Guid
0xf99f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf9a4  pop
0xf9a5  ldarg.0
0xf9a6  ldloc.2
0xf9a7  ldarg.2
0xf9a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf9ad  stloc.3
0xf9ae  ldloc.3
0xf9af  brfalse  loc_FA7E
0xf9b4  ldloc.3
0xf9b5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xf9ba  stloc.s  4
0xf9bc  br       loc_FA5B
0xf9c1  ldloc.s  4
0xf9c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf9c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xf9cd  stloc.s  5
0xf9cf  ldarg.0
0xf9d0  ldloc.s  5
0xf9d2  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xf9d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf9dc  unbox.any [mscorlib]System.Guid
0xf9e1  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xf9e6  ldarg.2
0xf9e7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf9ec  ldc.i4.5
0xf9ed  ldc.i4.m1
0xf9ee  ldarg.2
0xf9ef  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf9f4  pop
0xf9f5  ldarg.2
0xf9f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf9fb  ldc.i4.0
0xf9fc  ldstr    a0// "{0}"
0xfa01  ldc.i4.1
0xfa02  newarr   [mscorlib]System.Object
0xfa07  dup
0xfa08  ldc.i4.0
0xfa09  ldstr    aKnowledgeArtic_0// "Knowledge Article with Article Id {0}, "...
0xfa0e  ldc.i4.4
0xfa0f  newarr   [mscorlib]System.Object
0xfa14  dup
0xfa15  ldc.i4.0
0xfa16  ldloc.s  5
0xfa18  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xfa1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xfa22  stelem.ref
0xfa23  dup
0xfa24  ldc.i4.1
0xfa25  ldloc.s  5
0xfa27  ldstr    aArticlepublicn// "articlepublicnumber"
0xfa2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xfa31  stelem.ref
0xfa32  dup
0xfa33  ldc.i4.2
0xfa34  ldloc.s  5
0xfa36  ldstr    aMajorversionnu// "majorversionnumber"
0xfa3b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xfa40  stelem.ref
0xfa41  dup
0xfa42  ldc.i4.3
0xfa43  ldloc.s  5
0xfa45  ldstr    aMinorversionnu// "minorversionnumber"
0xfa4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xfa4f  stelem.ref
0xfa50  call     string [mscorlib]System.String::Format(string, object[])
0xfa55  stelem.ref
0xfa56  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfa5b  ldloc.s  4
0xfa5d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xfa62  brtrue   loc_F9C1
0xfa67  leave.s  loc_FA7E
0xfa69  ldloc.s  4
0xfa6b  isinst   [mscorlib]System.IDisposable
0xfa70  stloc.s  6
0xfa72  ldloc.s  6
0xfa74  brfalse.s loc_FA7D
0xfa76  ldloc.s  6
0xfa78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfa7d  endfinally
0xfa7e  ret
```
