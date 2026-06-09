# Microsoft.Crm.Metadata.EntityService::DeleteDocumentTemplates

- ea: `0x32090`
- end: `0x321dd`
- name: `Microsoft.Crm.Metadata.EntityService::DeleteDocumentTemplates`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x32090`

## string_xrefs

- `0x32096`: `DocumentTemplate`
- `0x32100`: `DocumentTemplate`
- `0x320a8`: `documenttemplateid`
- `0x320ec`: `documenttemplateid`
- `0x3213c`: `PersonalDocumentTemplate`
- `0x321a6`: `PersonalDocumentTemplate`
- `0x3214e`: `personaldocumenttemplateid`
- `0x32192`: `personaldocumenttemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x32090  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DocumentTemplateService::.ctor()
0x32095  stloc.0
0x32096  ldstr    aDocumenttempla// "DocumentTemplate"
0x3209b  ldarg.1
0x3209c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x320a1  stloc.1
0x320a2  ldloc.1
0x320a3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x320a8  ldstr    aDocumenttempla_0// "documenttemplateid"
0x320ad  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x320b2  ldloc.1
0x320b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x320b8  ldstr    aAssociatedenti// "associatedentitytypecode"
0x320bd  ldc.i4.0
0x320be  ldarg.0
0x320bf  box      [mscorlib]System.Int32
0x320c4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x320c9  pop
0x320ca  ldloc.0
0x320cb  ldloc.1
0x320cc  ldarg.1
0x320cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x320d2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x320d7  stloc.s  4
0x320d9  br.s     loc_32116
0x320db  ldloc.s  4
0x320dd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x320e2  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.DocumentTemplate
0x320e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x320ec  ldstr    aDocumenttempla_0// "documenttemplateid"
0x320f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x320f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x320fb  unbox.any [mscorlib]System.Guid
0x32100  ldstr    aDocumenttempla// "DocumentTemplate"
0x32105  ldarg.1
0x32106  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3210b  stloc.s  5
0x3210d  ldloc.0
0x3210e  ldloc.s  5
0x32110  ldarg.1
0x32111  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32116  ldloc.s  4
0x32118  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3211d  brtrue.s loc_320DB
0x3211f  leave.s  loc_32136
0x32121  ldloc.s  4
0x32123  isinst   [mscorlib]System.IDisposable
0x32128  stloc.s  6
0x3212a  ldloc.s  6
0x3212c  brfalse.s loc_32135
0x3212e  ldloc.s  6
0x32130  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32135  endfinally
0x32136  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PersonalDocumentTemplateService::.ctor()
0x3213b  stloc.2
0x3213c  ldstr    aPersonaldocume// "PersonalDocumentTemplate"
0x32141  ldarg.1
0x32142  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x32147  stloc.3
0x32148  ldloc.3
0x32149  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x3214e  ldstr    aPersonaldocume_0// "personaldocumenttemplateid"
0x32153  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x32158  ldloc.3
0x32159  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x3215e  ldstr    aAssociatedenti// "associatedentitytypecode"
0x32163  ldc.i4.0
0x32164  ldarg.0
0x32165  box      [mscorlib]System.Int32
0x3216a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x3216f  pop
0x32170  ldloc.2
0x32171  ldloc.3
0x32172  ldarg.1
0x32173  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32178  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3217d  stloc.s  4
0x3217f  br.s     loc_321BC
0x32181  ldloc.s  4
0x32183  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32188  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PersonalDocumentTemplate
0x3218d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x32192  ldstr    aPersonaldocume_0// "personaldocumenttemplateid"
0x32197  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x3219c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x321a1  unbox.any [mscorlib]System.Guid
0x321a6  ldstr    aPersonaldocume// "PersonalDocumentTemplate"
0x321ab  ldarg.1
0x321ac  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x321b1  stloc.s  7
0x321b3  ldloc.2
0x321b4  ldloc.s  7
0x321b6  ldarg.1
0x321b7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x321bc  ldloc.s  4
0x321be  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x321c3  brtrue.s loc_32181
0x321c5  leave.s  loc_321DC
0x321c7  ldloc.s  4
0x321c9  isinst   [mscorlib]System.IDisposable
0x321ce  stloc.s  6
0x321d0  ldloc.s  6
0x321d2  brfalse.s loc_321DB
0x321d4  ldloc.s  6
0x321d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x321db  endfinally
0x321dc  ret
```
