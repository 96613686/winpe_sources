# Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::IsEntitySingleRootComponent

- ea: `0x2ef20`
- end: `0x2efcb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::IsEntitySingleRootComponent`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2e9c0`

## callees

- `0x2ef20`

## string_xrefs

- `0x2ef72`: `componenttype`
- `0x2ef92`: `rootcomponentbehavior`
- `0x2efb6`: `rootcomponentbehavior`
- `0x2ef26`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x2ef20  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x2ef25  stloc.0
0x2ef26  ldstr    aSolutioncompon// "SolutionComponent"
0x2ef2b  ldarg.3
0x2ef2c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2ef31  stloc.1
0x2ef32  ldloc.1
0x2ef33  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2ef38  ldstr    aSolutionid// "solutionid"
0x2ef3d  ldc.i4.0
0x2ef3e  ldarg.0
0x2ef3f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::_solutionid
0x2ef44  box      [mscorlib]System.Guid
0x2ef49  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2ef4e  pop
0x2ef4f  ldloc.1
0x2ef50  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2ef55  ldstr    aObjectid// "objectid"
0x2ef5a  ldc.i4.0
0x2ef5b  ldarg.2
0x2ef5c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x2ef61  box      [mscorlib]System.Guid
0x2ef66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2ef6b  pop
0x2ef6c  ldloc.1
0x2ef6d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2ef72  ldstr    aComponenttype// "componenttype"
0x2ef77  ldc.i4.0
0x2ef78  ldc.i4.1
0x2ef79  box      [mscorlib]System.Int32
0x2ef7e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2ef83  pop
0x2ef84  ldloc.1
0x2ef85  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2ef8a  ldc.i4.1
0x2ef8b  newarr   [mscorlib]System.String
0x2ef90  dup
0x2ef91  ldc.i4.0
0x2ef92  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2ef97  stelem.ref
0x2ef98  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2ef9d  ldloc.0
0x2ef9e  ldloc.1
0x2ef9f  ldarg.3
0x2efa0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2efa5  stloc.2
0x2efa6  ldloc.2
0x2efa7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2efac  ldc.i4.1
0x2efad  bne.un.s loc_2EFC9
0x2efaf  ldloc.2
0x2efb0  ldc.i4.0
0x2efb1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x2efb6  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2efbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2efc0  unbox.any [mscorlib]System.Int32
0x2efc5  ldc.i4.0
0x2efc6  ceq
0x2efc8  ret
0x2efc9  ldc.i4.0
0x2efca  ret
```
