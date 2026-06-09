# Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails_1

- ea: `0x42f0`
- end: `0x4399`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails_1`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x42c0`
- `0x42d0`
- `0x42e0`

## callees

- `0x3150`
- `0x42f0`

## pseudocode

```c

```

## disassembly

```asm
0x42f0  ldarg.s  6
0x42f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x42f7  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail::.ctor(valuetype [mscorlib]System.Guid)
0x42fc  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x4301  stloc.0
0x4302  dup
0x4303  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4308  ldarg.s  6
0x430a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x430f  stloc.1
0x4310  dup
0x4311  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4316  ldarg.s  6
0x4318  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x431d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x4322  ldarg.3
0x4323  brfalse.s loc_4332
0x4325  ldloc.1
0x4326  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x432b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x4330  br.s     loc_4341
0x4332  ldarg.2
0x4333  brfalse.s loc_4341
0x4335  ldloc.1
0x4336  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x433b  ldarg.2
0x433c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4341  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4346  ldarg.s  6
0x4348  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x434d  stloc.2
0x434e  ldloc.2
0x434f  ldstr    aContractid// "contractid"
0x4354  ldc.i4.0
0x4355  ldarg.1
0x4356  box      [mscorlib]System.Guid
0x435b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4360  pop
0x4361  ldarg.s  5
0x4363  brtrue.s loc_4378
0x4365  ldloc.2
0x4366  ldstr    aStatecode// "statecode"
0x436b  ldc.i4.1
0x436c  ldc.i4.2
0x436d  box      [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetailState
0x4372  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4377  pop
0x4378  ldloc.1
0x4379  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x437e  ldloc.2
0x437f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x4384  ldarg.s  4
0x4386  brfalse.s loc_438F
0x4388  ldloc.1
0x4389  ldc.i4.0
0x438a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_RetrieveBehaviorForSecuredAttributes(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior)
0x438f  ldloc.0
0x4390  ldloc.1
0x4391  ldarg.s  6
0x4393  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4398  ret
```
