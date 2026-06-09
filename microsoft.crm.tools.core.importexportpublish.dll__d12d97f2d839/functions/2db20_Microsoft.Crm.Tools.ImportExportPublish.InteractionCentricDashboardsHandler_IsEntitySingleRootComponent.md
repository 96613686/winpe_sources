# Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::IsEntitySingleRootComponent

- ea: `0x2db20`
- end: `0x2dbc3`
- name: `Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::IsEntitySingleRootComponent`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2d4c0`

## callees

- `0x2db20`

## string_xrefs

- `0x2db69`: `componenttype`
- `0x2db89`: `rootcomponentbehavior`
- `0x2dbae`: `rootcomponentbehavior`
- `0x2db26`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x2db20  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x2db25  stloc.0
0x2db26  ldstr    aSolutioncompon// "SolutionComponent"
0x2db2b  ldarg.s  4
0x2db2d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2db32  stloc.1
0x2db33  ldloc.1
0x2db34  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2db39  ldstr    aSolutionid// "solutionid"
0x2db3e  ldc.i4.0
0x2db3f  ldarg.3
0x2db40  box      [mscorlib]System.Guid
0x2db45  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2db4a  pop
0x2db4b  ldloc.1
0x2db4c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2db51  ldstr    aObjectid// "objectid"
0x2db56  ldc.i4.0
0x2db57  ldarg.2
0x2db58  box      [mscorlib]System.Guid
0x2db5d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2db62  pop
0x2db63  ldloc.1
0x2db64  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2db69  ldstr    aComponenttype// "componenttype"
0x2db6e  ldc.i4.0
0x2db6f  ldc.i4.1
0x2db70  box      [mscorlib]System.Int32
0x2db75  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2db7a  pop
0x2db7b  ldloc.1
0x2db7c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2db81  ldc.i4.1
0x2db82  newarr   [mscorlib]System.String
0x2db87  dup
0x2db88  ldc.i4.0
0x2db89  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2db8e  stelem.ref
0x2db8f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2db94  ldloc.0
0x2db95  ldloc.1
0x2db96  ldarg.s  4
0x2db98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2db9d  stloc.2
0x2db9e  ldloc.2
0x2db9f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2dba4  ldc.i4.1
0x2dba5  bne.un.s loc_2DBC1
0x2dba7  ldloc.2
0x2dba8  ldc.i4.0
0x2dba9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x2dbae  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2dbb3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2dbb8  unbox.any [mscorlib]System.Int32
0x2dbbd  ldc.i4.0
0x2dbbe  ceq
0x2dbc0  ret
0x2dbc1  ldc.i4.0
0x2dbc2  ret
```
