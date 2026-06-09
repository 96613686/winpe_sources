# Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLARecord

- ea: `0xa8e0`
- end: `0xa94c`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLARecord`
- size: `108`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e70`
- `0x9f60`
- `0x9fc0`
- `0xa340`
- `0xa4b0`
- `0xac00`

## pseudocode

```c

```

## disassembly

```asm
0xa8e0  ldstr    aSla_0// "SLA"
0xa8e5  ldarg.2
0xa8e6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xa8eb  stloc.0
0xa8ec  ldloc.0
0xa8ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xa8f2  ldc.i4.5
0xa8f3  newarr   [mscorlib]System.String
0xa8f8  dup
0xa8f9  ldc.i4.0
0xa8fa  ldstr    aSlaid// "slaid"
0xa8ff  stelem.ref
0xa900  dup
0xa901  ldc.i4.1
0xa902  ldstr    aStatecode// "statecode"
0xa907  stelem.ref
0xa908  dup
0xa909  ldc.i4.2
0xa90a  ldstr    aWorkflowid// "workflowid"
0xa90f  stelem.ref
0xa910  dup
0xa911  ldc.i4.3
0xa912  ldstr    aName// "name"
0xa917  stelem.ref
0xa918  dup
0xa919  ldc.i4.4
0xa91a  ldstr    aOwnerid// "ownerid"
0xa91f  stelem.ref
0xa920  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xa925  ldloc.0
0xa926  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xa92b  ldstr    aSlaid// "slaid"
0xa930  ldc.i4.0
0xa931  ldarg.1
0xa932  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xa937  box      [mscorlib]System.Guid
0xa93c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa941  pop
0xa942  ldarg.0
0xa943  ldarg.1
0xa944  ldloc.0
0xa945  ldarg.2
0xa946  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa94b  ret
```
