# Microsoft.Crm.ObjectModel.GoalService::Create

- ea: `0x170960`
- end: `0x170b37`
- name: `Microsoft.Crm.ObjectModel.GoalService::Create`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x170960`
- `0x170b40`
- `0x170c60`
- `0x170cd0`
- `0x171ee0`
- `0x1725d0`
- `0x172600`
- `0x172670`
- `0x1726c0`
- `0x172790`
- `0x176820`
- `0x176870`
- `0x1f0b20`
- `0x1f0bc0`

## string_xrefs

- `0x1709f3`: `isamount`
- `0x170a5c`: `isamount`
- `0x170aa1`: `isamount`
- `0x1709fb`: `amountdatatype`
- `0x170a6c`: `amountdatatype`
- `0x170a79`: `amountdatatype`
- `0x170ab1`: `amountdatatype`
- `0x170abe`: `amountdatatype`

## pseudocode

```c

```

## disassembly

```asm
0x170960  ldarg.1
0x170961  ldstr    aMetricid// "metricid"
0x170966  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x17096b  brfalse.s loc_170978
0x17096d  ldnull
0x17096e  ldstr    aMetricid// "metricid"
0x170973  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x170978  ldarg.1
0x170979  ldstr    aMetricid// "metricid"
0x17097e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x170983  unbox.any [mscorlib]System.Guid
0x170988  ldstr    aMetricid// "metricid"
0x17098d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x170992  ldarg.1
0x170993  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Goal
0x170998  ldc.i4.0
0x170999  ldarg.2
0x17099a  newobj   instance void Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject::.ctor(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Goal incomingGoal, bool hasPreImages, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17099f  stloc.0
0x1709a0  ldarg.0
0x1709a1  ldloc.0
0x1709a2  ldarg.2
0x1709a3  call     instance void Microsoft.Crm.ObjectModel.GoalService::SetDefaultsForCreate(class Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject goalState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1709a8  ldarg.0
0x1709a9  ldloc.0
0x1709aa  ldarg.2
0x1709ab  call     instance void Microsoft.Crm.ObjectModel.GoalService::ValidateStateForCreate(class Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject goalState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1709b0  ldarg.0
0x1709b1  ldarg.1
0x1709b2  call     instance void Microsoft.Crm.ObjectModel.GoalService::HandleWritesOnRollupFields(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity goalEntity)
0x1709b7  ldarg.0
0x1709b8  ldarg.1
0x1709b9  ldarg.2
0x1709ba  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1709bf  stloc.1
0x1709c0  ldarg.0
0x1709c1  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1709c6  ldarg.2
0x1709c7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1709cc  stloc.2
0x1709cd  ldloc.2
0x1709ce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1709d3  ldc.i4.5
0x1709d4  newarr   [mscorlib]System.String
0x1709d9  dup
0x1709da  ldc.i4.0
0x1709db  ldstr    aOwnerid// "ownerid"
0x1709e0  stelem.ref
0x1709e1  dup
0x1709e2  ldc.i4.1
0x1709e3  ldstr    aGoalownerid// "goalownerid"
0x1709e8  stelem.ref
0x1709e9  dup
0x1709ea  ldc.i4.2
0x1709eb  ldstr    aGoalowneridtyp// "goalowneridtype"
0x1709f0  stelem.ref
0x1709f1  dup
0x1709f2  ldc.i4.3
0x1709f3  ldstr    aIsamount// "isamount"
0x1709f8  stelem.ref
0x1709f9  dup
0x1709fa  ldc.i4.4
0x1709fb  ldstr    aAmountdatatype// "amountdatatype"
0x170a00  stelem.ref
0x170a01  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x170a06  ldarg.0
0x170a07  ldloc.2
0x170a08  ldloc.1
0x170a09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x170a0e  ldarg.2
0x170a0f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.GoalService::RetrieveGoalInSystemUserContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, valuetype [mscorlib]System.Guid goalId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x170a14  stloc.3
0x170a15  ldarg.0
0x170a16  ldloc.3
0x170a17  ldstr    aOwnerid// "ownerid"
0x170a1c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170a21  unbox.any [mscorlib]System.Guid
0x170a26  ldloc.3
0x170a27  ldstr    aGoalownerid// "goalownerid"
0x170a2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170a31  unbox.any [mscorlib]System.Guid
0x170a36  ldloc.3
0x170a37  ldstr    aGoalowneridtyp// "goalowneridtype"
0x170a3c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170a41  unbox.any [mscorlib]System.Int32
0x170a46  ldloc.1
0x170a47  ldarg.2
0x170a48  call     instance void Microsoft.Crm.ObjectModel.GoalService::ShareGoalWithGoalOwner(valuetype [mscorlib]System.Guid ownerid, valuetype [mscorlib]System.Guid goalOwnerId, int32 goalOwnerType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker goalMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x170a4d  ldarg.0
0x170a4e  ldloc.1
0x170a4f  ldloc.0
0x170a50  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Goal Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject::get_PostImageParentGoal()
0x170a55  ldarg.2
0x170a56  call     instance void Microsoft.Crm.ObjectModel.GoalService::ShareWithParentGoalRecordOwnerInSystemUserContext(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker goalMoniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity parentGoal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x170a5b  ldloc.3
0x170a5c  ldstr    aIsamount// "isamount"
0x170a61  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170a66  unbox.any [mscorlib]System.Boolean
0x170a6b  ldloc.3
0x170a6c  ldstr    aAmountdatatype// "amountdatatype"
0x170a71  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x170a76  brtrue.s loc_170A8A
0x170a78  ldloc.3
0x170a79  ldstr    aAmountdatatype// "amountdatatype"
0x170a7e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170a83  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x170a88  br.s     loc_170A94
0x170a8a  ldloca.s 6
0x170a8c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x170a92  ldloc.s  6
0x170a94  call     class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.ObjectModel.GoalUtil::GetRollupQueryFields(bool isAmount, valuetype [mscorlib]System.Nullable`1<int32> amountDataType)
0x170a99  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0x170a9e  stloc.s  4
0x170aa0  ldloc.3
0x170aa1  ldstr    aIsamount// "isamount"
0x170aa6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170aab  unbox.any [mscorlib]System.Boolean
0x170ab0  ldloc.3
0x170ab1  ldstr    aAmountdatatype// "amountdatatype"
0x170ab6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x170abb  brtrue.s loc_170ACF
0x170abd  ldloc.3
0x170abe  ldstr    aAmountdatatype// "amountdatatype"
0x170ac3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170ac8  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x170acd  br.s     loc_170AD9
0x170acf  ldloca.s 6
0x170ad1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x170ad7  ldloc.s  6
0x170ad9  call     string Microsoft.Crm.ObjectModel.GoalUtil::GetTargetField(bool isAmount, valuetype [mscorlib]System.Nullable`1<int32> amountDataType)
0x170ade  stloc.s  5
0x170ae0  ldarg.0
0x170ae1  ldloc.0
0x170ae2  ldloc.s  4
0x170ae4  ldloc.3
0x170ae5  ldstr    aOwnerid// "ownerid"
0x170aea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170aef  unbox.any [mscorlib]System.Guid
0x170af4  ldloc.3
0x170af5  ldstr    aGoalownerid// "goalownerid"
0x170afa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170aff  unbox.any [mscorlib]System.Guid
0x170b04  ldloc.3
0x170b05  ldstr    aGoalowneridtyp// "goalowneridtype"
0x170b0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x170b0f  unbox.any [mscorlib]System.Int32
0x170b14  ldarg.2
0x170b15  call     instance void Microsoft.Crm.ObjectModel.GoalService::ShareRollUpQueryWithGoalOwner(class Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject goalState, class [mscorlib]System.Collections.Generic.List`1<string> rollUpQueryFields, valuetype [mscorlib]System.Guid ownerid, valuetype [mscorlib]System.Guid goalOwnerId, int32 goalOwnerType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x170b1a  ldarg.0
0x170b1b  ldloc.0
0x170b1c  ldloc.0
0x170b1d  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Goal Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject::get_PostImageParentGoal()
0x170b22  ldloc.s  4
0x170b24  ldarg.2
0x170b25  call     instance void Microsoft.Crm.ObjectModel.GoalService::ShareRollUpQueryWithParentGoalRecordOwner(class Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject goalState, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity parentGoal, class [mscorlib]System.Collections.Generic.List`1<string> rollUpQueryFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x170b2a  ldarg.0
0x170b2b  ldloc.0
0x170b2c  ldloc.s  4
0x170b2e  ldloc.s  5
0x170b30  call     instance void Microsoft.Crm.ObjectModel.GoalService::CaptureTelemetryForGoalEntity(class Microsoft.Crm.ObjectModel.GoalManagement.GoalStateObject goalState, class [mscorlib]System.Collections.Generic.List`1<string> rollUpQueryFields, string TargetType)
0x170b35  ldloc.1
0x170b36  ret
```
