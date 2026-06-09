# Microsoft.Crm.Service.ObjectModel.ServiceService::RetrieveByResources

- ea: `0x14150`
- end: `0x141d1`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceService::RetrieveByResources`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14150`

## string_xrefs

- `0x14171`: `Service`

## pseudocode

```c

```

## disassembly

```asm
0x14150  ldarg.1
0x14151  ldstr    aResourceids// "resourceIds"
0x14156  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1415b  ldarg.1
0x1415c  newobj   instance void [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.ServicesByResourceCommand::.ctor(valuetype [mscorlib]System.Guid[])
0x14161  ldarg.3
0x14162  newobj   instance void [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.CrmSchedulingExecutionContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14167  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.ServicesByResourceCommand::Execute(class [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.ISchedulingExecutionContext)
0x1416c  stloc.0
0x1416d  ldloc.0
0x1416e  ldlen
0x1416f  brtrue.s loc_14182
0x14171  ldstr    aService// "Service"
0x14176  ldarg.3
0x14177  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1417c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x14181  ret
0x14182  ldarg.3
0x14183  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x14188  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Service::.ctor(valuetype [mscorlib]System.Guid)
0x1418d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x14192  stloc.1
0x14193  ldarg.2
0x14194  brtrue.s loc_141AF
0x14196  ldloc.1
0x14197  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1419c  ldarg.3
0x1419d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x141a2  starg.s  2
0x141a4  ldarg.2
0x141a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x141aa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x141af  ldarg.2
0x141b0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x141b5  ldloc.1
0x141b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x141bb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x141c0  ldc.i4.8
0x141c1  ldloc.0
0x141c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x141c7  pop
0x141c8  ldarg.0
0x141c9  ldarg.2
0x141ca  ldarg.3
0x141cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x141d0  ret
```
