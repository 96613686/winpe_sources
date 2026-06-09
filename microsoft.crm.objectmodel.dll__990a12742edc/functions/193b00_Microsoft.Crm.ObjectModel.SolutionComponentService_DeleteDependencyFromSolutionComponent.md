# Microsoft.Crm.ObjectModel.SolutionComponentService::DeleteDependencyFromSolutionComponent

- ea: `0x193b00`
- end: `0x193bc1`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::DeleteDependencyFromSolutionComponent`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x193bd0`

## callees

- `0x193b00`
- `0x193d00`
- `0x193fa0`

## string_xrefs

- `0x193b53`: `componenttype`
- `0x193b00`: `SolutionComponent`
- `0x193b7c`: `SolutionComponent`
- `0x193bb4`: `SolutionComponent`
- `0x193b25`: `solutioncomponentid`
- `0x193b91`: `solutioncomponentid`
- `0x193b89`: `rootsolutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x193b00  ldstr    aSolutioncompon// "SolutionComponent"
0x193b05  ldarg.2
0x193b06  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x193b0b  stloc.0
0x193b0c  ldloc.0
0x193b0d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x193b12  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x193b17  ldloc.0
0x193b18  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x193b1d  ldc.i4.1
0x193b1e  newarr   [mscorlib]System.String
0x193b23  dup
0x193b24  ldc.i4.0
0x193b25  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x193b2a  stelem.ref
0x193b2b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x193b30  ldloc.0
0x193b31  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x193b36  ldstr    aObjectid// "objectid"
0x193b3b  ldc.i4.0
0x193b3c  ldarg.1
0x193b3d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::get_Id()
0x193b42  box      [mscorlib]System.Guid
0x193b47  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x193b4c  pop
0x193b4d  ldloc.0
0x193b4e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x193b53  ldstr    aComponenttype// "componenttype"
0x193b58  ldc.i4.0
0x193b59  ldarg.1
0x193b5a  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::get_ComponentType()
0x193b5f  box      [mscorlib]System.Int32
0x193b64  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x193b69  pop
0x193b6a  ldarg.0
0x193b6b  ldloc.0
0x193b6c  ldarg.2
0x193b6d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x193b72  stloc.1
0x193b73  ldloc.1
0x193b74  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x193b79  ldc.i4.0
0x193b7a  ble.s    loc_193BC0
0x193b7c  ldstr    aSolutioncompon// "SolutionComponent"
0x193b81  ldarg.2
0x193b82  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x193b87  stloc.2
0x193b88  ldloc.2
0x193b89  ldstr    aRootsolutionco// "rootsolutioncomponentid"
0x193b8e  ldc.i4.8
0x193b8f  ldarg.0
0x193b90  ldloc.1
0x193b91  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x193b96  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.ObjectModel.SolutionComponentService::BusinessEntityCollectionToArray(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection bec, string id)
0x193b9b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x193ba0  pop
0x193ba1  ldarg.3
0x193ba2  brfalse.s loc_193BB3
0x193ba4  ldloc.2
0x193ba5  ldstr    aSolutionid// "solutionid"
0x193baa  ldc.i4.s 9
0x193bac  ldarg.3
0x193bad  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x193bb2  pop
0x193bb3  ldarg.0
0x193bb4  ldstr    aSolutioncompon// "SolutionComponent"
0x193bb9  ldloc.2
0x193bba  ldarg.2
0x193bbb  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::ExecuteDeletePlan(string entityPlatformName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression filter, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x193bc0  ret
```
