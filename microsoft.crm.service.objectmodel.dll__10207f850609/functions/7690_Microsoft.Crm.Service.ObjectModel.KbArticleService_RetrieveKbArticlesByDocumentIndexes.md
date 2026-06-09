# Microsoft.Crm.Service.ObjectModel.KbArticleService::RetrieveKbArticlesByDocumentIndexes

- ea: `0x7690`
- end: `0x771d`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::RetrieveKbArticlesByDocumentIndexes`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x75b0`
- `0x7600`
- `0x7650`

## callees

- `0x7690`

## pseudocode

```c

```

## disassembly

```asm
0x7690  ldarg.1
0x7691  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7696  brtrue.s loc_76AB
0x7698  ldstr    aKbarticle// "KbArticle"
0x769d  ldarg.3
0x769e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x76a3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x76a8  stloc.0
0x76a9  br.s     loc_771B
0x76ab  newobj   instance void [Microsoft.Crm]Microsoft.Crm.GuidSet::.ctor()
0x76b0  stloc.1
0x76b1  ldarg.1
0x76b2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x76b7  stloc.2
0x76b8  br.s     loc_76DC
0x76ba  ldloc.2
0x76bb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x76c0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x76c5  stloc.3
0x76c6  ldloc.1
0x76c7  ldloc.3
0x76c8  ldstr    aDocumentid// "documentid"
0x76cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x76d2  unbox.any [mscorlib]System.Guid
0x76d7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.GuidSet::Add(valuetype [mscorlib]System.Guid)
0x76dc  ldloc.2
0x76dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x76e2  brtrue.s loc_76BA
0x76e4  leave.s  loc_76FA
0x76e6  ldloc.2
0x76e7  isinst   [mscorlib]System.IDisposable
0x76ec  stloc.s  4
0x76ee  ldloc.s  4
0x76f0  brfalse.s loc_76F9
0x76f2  ldloc.s  4
0x76f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76f9  endfinally
0x76fa  ldarg.2
0x76fb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x7700  ldstr    aKbarticleid// "kbarticleid"
0x7705  ldc.i4.8
0x7706  ldloc.1
0x7707  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm]Microsoft.Crm.GuidSet::ToArray()
0x770c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x7711  pop
0x7712  ldarg.0
0x7713  ldarg.2
0x7714  ldarg.3
0x7715  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x771a  stloc.0
0x771b  ldloc.0
0x771c  ret
```
