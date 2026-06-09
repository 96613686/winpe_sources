# Microsoft.Crm.Metadata.EntityService::RetrieveEntitiesInSolution

- ea: `0x30fa0`
- end: `0x31068`
- name: `Microsoft.Crm.Metadata.EntityService::RetrieveEntitiesInSolution`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30c00`

## callees

- `0x30fa0`

## string_xrefs

- `0x30fa0`: `SolutionComponent`
- `0x30fb2`: `componenttype`

## pseudocode

```c

```

## disassembly

```asm
0x30fa0  ldstr    aSolutioncompon// "SolutionComponent"
0x30fa5  ldarg.2
0x30fa6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x30fab  stloc.0
0x30fac  ldloc.0
0x30fad  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x30fb2  ldstr    aComponenttype// "componenttype"
0x30fb7  ldc.i4.0
0x30fb8  ldc.i4.1
0x30fb9  newarr   [mscorlib]System.Int32
0x30fbe  dup
0x30fbf  ldc.i4.0
0x30fc0  ldc.i4.1
0x30fc1  stelem.i4
0x30fc2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x30fc7  pop
0x30fc8  ldloc.0
0x30fc9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x30fce  ldstr    aSolutionid// "solutionid"
0x30fd3  ldc.i4.0
0x30fd4  ldc.i4.1
0x30fd5  newarr   [mscorlib]System.Guid
0x30fda  dup
0x30fdb  ldc.i4.0
0x30fdc  ldarg.1
0x30fdd  stelem   [mscorlib]System.Guid
0x30fe2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x30fe7  pop
0x30fe8  ldloc.0
0x30fe9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x30fee  ldstr    aObjectid// "objectid"
0x30ff3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x30ff8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x30ffd  ldloc.0
0x30ffe  ldarg.2
0x30fff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31004  stloc.1
0x31005  ldloc.1
0x31006  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x3100b  ldc.i4.0
0x3100c  ble.s    loc_31062
0x3100e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x31013  stloc.2
0x31014  ldloc.1
0x31015  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3101a  stloc.3
0x3101b  br.s     loc_31042
0x3101d  ldloc.3
0x3101e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x31023  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x31028  stloc.s  4
0x3102a  ldloc.2
0x3102b  ldloc.s  4
0x3102d  ldstr    aObjectid// "objectid"
0x31032  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x31037  unbox.any [mscorlib]System.Guid
0x3103c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x31041  pop
0x31042  ldloc.3
0x31043  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31048  brtrue.s loc_3101D
0x3104a  leave.s  loc_31060
0x3104c  ldloc.3
0x3104d  isinst   [mscorlib]System.IDisposable
0x31052  stloc.s  5
0x31054  ldloc.s  5
0x31056  brfalse.s loc_3105F
0x31058  ldloc.s  5
0x3105a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3105f  endfinally
0x31060  ldloc.2
0x31061  ret
0x31062  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x31067  ret
```
