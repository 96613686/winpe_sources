# Microsoft.Crm.Service.ObjectModel.ContractService::ValidateRenewedContractActiveExpireDates

- ea: `0x3f50`
- end: `0x403b`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::ValidateRenewedContractActiveExpireDates`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a80`

## callees

- `0x3150`
- `0x3f50`

## pseudocode

```c

```

## disassembly

```asm
0x3f50  ldarg.s  4
0x3f52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3f57  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract::.ctor(valuetype [mscorlib]System.Guid)
0x3f5c  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x3f61  stloc.0
0x3f62  dup
0x3f63  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3f68  ldarg.s  4
0x3f6a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3f6f  stloc.1
0x3f70  ldloc.1
0x3f71  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x3f76  ldloc.1
0x3f77  ldstr    aContractnumber// "contractnumber"
0x3f7c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x3f81  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3f86  ldarg.s  4
0x3f88  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3f8d  stloc.2
0x3f8e  ldloc.2
0x3f8f  ldstr    aContractnumber// "contractnumber"
0x3f94  ldc.i4.0
0x3f95  ldarg.1
0x3f96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x3f9b  pop
0x3f9c  ldc.i4.2
0x3f9d  newarr   [mscorlib]System.Int32
0x3fa2  dup
0x3fa3  ldc.i4.0
0x3fa4  ldc.i4.1
0x3fa5  stelem.i4
0x3fa6  dup
0x3fa7  ldc.i4.1
0x3fa8  ldc.i4.2
0x3fa9  stelem.i4
0x3faa  stloc.3
0x3fab  ldloc.2
0x3fac  ldstr    aStatecode// "statecode"
0x3fb1  ldc.i4.8
0x3fb2  ldloc.3
0x3fb3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x3fb8  pop
0x3fb9  ldloc.2
0x3fba  ldc.i4.1
0x3fbb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x3fc0  stloc.s  4
0x3fc2  ldc.i4.2
0x3fc3  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3fc8  dup
0x3fc9  ldc.i4.0
0x3fca  ldarg.2
0x3fcb  stelem.ref
0x3fcc  dup
0x3fcd  ldc.i4.1
0x3fce  ldarg.3
0x3fcf  stelem.ref
0x3fd0  stloc.s  5
0x3fd2  ldloc.s  4
0x3fd4  ldstr    aActiveon// "activeon"
0x3fd9  ldc.i4.s 0xA
0x3fdb  ldloc.s  5
0x3fdd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x3fe2  pop
0x3fe3  ldloc.s  4
0x3fe5  ldstr    aExpireson// "expireson"
0x3fea  ldc.i4.s 0xA
0x3fec  ldloc.s  5
0x3fee  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x3ff3  pop
0x3ff4  ldloc.s  4
0x3ff6  ldc.i4.0
0x3ff7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x3ffc  dup
0x3ffd  ldstr    aActiveon// "activeon"
0x4002  ldc.i4.5
0x4003  ldarg.2
0x4004  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4009  pop
0x400a  ldstr    aExpireson// "expireson"
0x400f  ldc.i4.4
0x4010  ldarg.3
0x4011  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4016  pop
0x4017  ldloc.0
0x4018  ldloc.2
0x4019  ldloc.1
0x401a  ldarg.s  4
0x401c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4021  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4026  ldc.i4.0
0x4027  ble.s    loc_403A
0x4029  ldc.i4   0x80043218
0x402e  ldc.i4.0
0x402f  newarr   [mscorlib]System.Object
0x4034  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4039  throw
0x403a  ret
```
