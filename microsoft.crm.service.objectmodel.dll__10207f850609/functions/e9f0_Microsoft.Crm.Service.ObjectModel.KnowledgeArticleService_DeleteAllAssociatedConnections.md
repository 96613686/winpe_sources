# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::DeleteAllAssociatedConnections

- ea: `0xe9f0`
- end: `0xeb99`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::DeleteAllAssociatedConnections`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xedc0`

## callees

- `0xe9f0`

## string_xrefs

- `0xea06`: `Attempting to Deleting All Associated connections KnowledgeArticleId={0} targetObjectTypeCode={1} targetRoleId={2} `
- `0xeb59`: `Deleted Associated connections for KnowledgeArticleId={0} targetObjectTypeCode={1} targetRoleId={2} TotalConnectionDeleted={3} `

## pseudocode

```c

```

## disassembly

```asm
0xe9f0  ldarg.s  4
0xe9f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe9f7  ldc.i4.s 0x1A
0xe9f9  ldstr    a0// "{0}"
0xe9fe  ldc.i4.1
0xe9ff  newarr   [mscorlib]System.Object
0xea04  dup
0xea05  ldc.i4.0
0xea06  ldstr    aAttemptingToDe// "Attempting to Deleting All Associated c"...
0xea0b  ldarg.1
0xea0c  box      [mscorlib]System.Guid
0xea11  ldarg.2
0xea12  box      [mscorlib]System.Int32
0xea17  ldarg.3
0xea18  box      [mscorlib]System.Guid
0xea1d  call     string [mscorlib]System.String::Format(string, object, object, object)
0xea22  stelem.ref
0xea23  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xea28  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConnectionService::.ctor()
0xea2d  stloc.0
0xea2e  ldstr    aConnection// "Connection"
0xea33  ldarg.s  4
0xea35  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xea3a  stloc.1
0xea3b  ldloc.1
0xea3c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xea41  ldc.i4.3
0xea42  newarr   [mscorlib]System.String
0xea47  dup
0xea48  ldc.i4.0
0xea49  ldstr    aRecord1id// "record1id"
0xea4e  stelem.ref
0xea4f  dup
0xea50  ldc.i4.1
0xea51  ldstr    aRecord2id// "record2id"
0xea56  stelem.ref
0xea57  dup
0xea58  ldc.i4.2
0xea59  ldstr    aConnectionid// "connectionid"
0xea5e  stelem.ref
0xea5f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xea64  ldloc.1
0xea65  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xea6a  ldstr    aRecord1id// "record1id"
0xea6f  ldc.i4.0
0xea70  ldarg.1
0xea71  box      [mscorlib]System.Guid
0xea76  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xea7b  pop
0xea7c  ldloc.1
0xea7d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xea82  ldstr    aRecord1objectt// "record1objecttypecode"
0xea87  ldc.i4.0
0xea88  ldc.i4   0x26E1
0xea8d  box      [mscorlib]System.Int32
0xea92  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xea97  pop
0xea98  ldloc.1
0xea99  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xea9e  ldstr    aRecord2objectt// "record2objecttypecode"
0xeaa3  ldc.i4.0
0xeaa4  ldarg.2
0xeaa5  box      [mscorlib]System.Int32
0xeaaa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xeaaf  pop
0xeab0  ldloc.1
0xeab1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xeab6  ldstr    aRecord2roleid// "record2roleid"
0xeabb  ldc.i4.0
0xeabc  ldarg.3
0xeabd  box      [mscorlib]System.Guid
0xeac2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xeac7  pop
0xeac8  ldarg.0
0xeac9  ldloc.1
0xeaca  ldarg.s  4
0xeacc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xead1  stloc.2
0xead2  ldloc.2
0xead3  ldnull
0xead4  cgt.un
0xead6  ldloc.2
0xead7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xeadc  ldc.i4.0
0xeadd  cgt
0xeadf  and
0xeae0  brfalse  loc_EB98
0xeae5  ldloc.2
0xeae6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xeaeb  stloc.3
0xeaec  br.s     loc_EB25
0xeaee  ldloc.3
0xeaef  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xeaf4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xeaf9  stloc.s  4
0xeafb  ldloc.0
0xeafc  ldloc.s  4
0xeafe  ldstr    aConnectionid// "connectionid"
0xeb03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeb08  unbox.any [mscorlib]System.Guid
0xeb0d  ldstr    aConnection// "Connection"
0xeb12  ldarg.s  4
0xeb14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb19  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xeb1e  ldarg.s  4
0xeb20  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb25  ldloc.3
0xeb26  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xeb2b  brtrue.s loc_EAEE
0xeb2d  leave.s  loc_EB43
0xeb2f  ldloc.3
0xeb30  isinst   [mscorlib]System.IDisposable
0xeb35  stloc.s  5
0xeb37  ldloc.s  5
0xeb39  brfalse.s loc_EB42
0xeb3b  ldloc.s  5
0xeb3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeb42  endfinally
0xeb43  ldarg.s  4
0xeb45  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb4a  ldc.i4.s 0x1A
0xeb4c  ldstr    a0// "{0}"
0xeb51  ldc.i4.1
0xeb52  newarr   [mscorlib]System.Object
0xeb57  dup
0xeb58  ldc.i4.0
0xeb59  ldstr    aDeletedAssocia// "Deleted Associated connections for Know"...
0xeb5e  ldc.i4.4
0xeb5f  newarr   [mscorlib]System.Object
0xeb64  dup
0xeb65  ldc.i4.0
0xeb66  ldarg.1
0xeb67  box      [mscorlib]System.Guid
0xeb6c  stelem.ref
0xeb6d  dup
0xeb6e  ldc.i4.1
0xeb6f  ldarg.2
0xeb70  box      [mscorlib]System.Int32
0xeb75  stelem.ref
0xeb76  dup
0xeb77  ldc.i4.2
0xeb78  ldarg.3
0xeb79  box      [mscorlib]System.Guid
0xeb7e  stelem.ref
0xeb7f  dup
0xeb80  ldc.i4.3
0xeb81  ldloc.2
0xeb82  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xeb87  box      [mscorlib]System.Int32
0xeb8c  stelem.ref
0xeb8d  call     string [mscorlib]System.String::Format(string, object[])
0xeb92  stelem.ref
0xeb93  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb98  ret
```
