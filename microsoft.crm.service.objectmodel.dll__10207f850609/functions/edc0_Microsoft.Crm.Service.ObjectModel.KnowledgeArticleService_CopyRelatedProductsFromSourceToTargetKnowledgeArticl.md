# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedProductsFromSourceToTargetKnowledgeArticle

- ea: `0xedc0`
- end: `0xef06`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedProductsFromSourceToTargetKnowledgeArticle`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd6f0`
- `0xdca0`

## callees

- `0xe9f0`
- `0xedc0`

## pseudocode

```c

```

## disassembly

```asm
0xedc0  ldloca.s 0
0xedc2  ldstr    a131f5d069f364b// "131F5D06-9F36-4B59-B8B7-A1F7D6C5C5EF"
0xedc7  call     instance void [mscorlib]System.Guid::.ctor(string)
0xedcc  ldstr    aConnection// "Connection"
0xedd1  ldarg.s  4
0xedd3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xedd8  stloc.1
0xedd9  ldloc.1
0xedda  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeddf  ldc.i4.6
0xede0  newarr   [mscorlib]System.String
0xede5  dup
0xede6  ldc.i4.0
0xede7  ldstr    aRecord1id// "record1id"
0xedec  stelem.ref
0xeded  dup
0xedee  ldc.i4.1
0xedef  ldstr    aRecord2id// "record2id"
0xedf4  stelem.ref
0xedf5  dup
0xedf6  ldc.i4.2
0xedf7  ldstr    aRecord1roleid// "record1roleid"
0xedfc  stelem.ref
0xedfd  dup
0xedfe  ldc.i4.3
0xedff  ldstr    aRecord2roleid// "record2roleid"
0xee04  stelem.ref
0xee05  dup
0xee06  ldc.i4.4
0xee07  ldstr    aRecord1objectt// "record1objecttypecode"
0xee0c  stelem.ref
0xee0d  dup
0xee0e  ldc.i4.5
0xee0f  ldstr    aRecord2objectt// "record2objecttypecode"
0xee14  stelem.ref
0xee15  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xee1a  ldloc.1
0xee1b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xee20  ldstr    aRecord1id// "record1id"
0xee25  ldc.i4.0
0xee26  ldarg.1
0xee27  box      [mscorlib]System.Guid
0xee2c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xee31  pop
0xee32  ldloc.1
0xee33  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xee38  ldstr    aRecord2objectt// "record2objecttypecode"
0xee3d  ldc.i4.0
0xee3e  ldc.i4   0x400
0xee43  box      [mscorlib]System.Int32
0xee48  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xee4d  pop
0xee4e  ldloc.1
0xee4f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xee54  ldstr    aRecord2roleid// "record2roleid"
0xee59  ldc.i4.0
0xee5a  ldloc.0
0xee5b  box      [mscorlib]System.Guid
0xee60  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xee65  pop
0xee66  ldarg.0
0xee67  ldloc.1
0xee68  ldarg.s  4
0xee6a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xee6f  stloc.2
0xee70  ldloc.2
0xee71  brfalse  loc_EF05
0xee76  ldloc.2
0xee77  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xee7c  ldc.i4.0
0xee7d  ble      loc_EF05
0xee82  ldarg.3
0xee83  brfalse.s loc_EE94
0xee85  ldarg.0
0xee86  ldarg.2
0xee87  ldc.i4   0x400
0xee8c  ldloc.0
0xee8d  ldarg.s  4
0xee8f  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::DeleteAllAssociatedConnections(valuetype [mscorlib]System.Guid knowledgeArticleId, int32 targetObjectType, valuetype [mscorlib]System.Guid targetRoleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xee94  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConnectionService::.ctor()
0xee99  stloc.3
0xee9a  ldloc.2
0xee9b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xeea0  stloc.s  4
0xeea2  br.s     loc_EEE5
0xeea4  ldloc.s  4
0xeea6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xeeab  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xeeb0  stloc.s  5
0xeeb2  ldloc.s  5
0xeeb4  ldstr    aRecord1id// "record1id"
0xeeb9  ldarg.2
0xeeba  box      [mscorlib]System.Guid
0xeebf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xeec4  ldloc.s  5
0xeec6  ldstr    aConnectionid// "connectionid"
0xeecb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0xeed0  box      [mscorlib]System.Guid
0xeed5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xeeda  ldloc.3
0xeedb  ldloc.s  5
0xeedd  ldarg.s  4
0xeedf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeee4  pop
0xeee5  ldloc.s  4
0xeee7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xeeec  brtrue.s loc_EEA4
0xeeee  leave.s  loc_EF05
0xeef0  ldloc.s  4
0xeef2  isinst   [mscorlib]System.IDisposable
0xeef7  stloc.s  6
0xeef9  ldloc.s  6
0xeefb  brfalse.s loc_EF04
0xeefd  ldloc.s  6
0xeeff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xef04  endfinally
0xef05  ret
```
