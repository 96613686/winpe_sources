# Microsoft.Crm.Service.ObjectModel.IncidentService::ChangeActivitiesStatus

- ea: `0x2360`
- end: `0x24ef`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ChangeActivitiesStatus`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1980`
- `0x2160`

## callees

- `0x2360`

## string_xrefs

- `0x24be`: `Error occoured while checking open activities status`

## pseudocode

```c

```

## disassembly

```asm
0x2360  ldarg.3
0x2361  ldc.i4.2
0x2362  beq.s    loc_236B
0x2364  ldarg.3
0x2365  ldc.i4.1
0x2366  bne.un   loc_24EE
0x236b  ldarg.1
0x236c  ldstr    aIncidentid// "incidentid"
0x2371  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2376  unbox.any [mscorlib]System.Guid
0x237b  stloc.0
0x237c  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActivityPointerService::.ctor()
0x2381  ldstr    aActivitypointe// "ActivityPointer"
0x2386  ldarg.2
0x2387  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x238c  stloc.1
0x238d  ldloc.1
0x238e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2393  ldstr    aActivitytypeco// "activitytypecode"
0x2398  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x239d  ldloc.1
0x239e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a3  ldstr    aActivityid// "activityid"
0x23a8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23ad  ldloc.1
0x23ae  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x23b3  ldstr    aRegardingobjec// "regardingobjectid"
0x23b8  ldc.i4.0
0x23b9  ldloc.0
0x23ba  box      [mscorlib]System.Guid
0x23bf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x23c4  pop
0x23c5  ldstr    aActivitypointe// "ActivityPointer"
0x23ca  ldarg.2
0x23cb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23d0  stloc.2
0x23d1  ldloc.2
0x23d2  ldc.i4.1
0x23d3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x23d8  ldloc.2
0x23d9  ldstr    aStatecode// "statecode"
0x23de  ldc.i4.0
0x23df  ldc.i4.0
0x23e0  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState
0x23e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x23ea  pop
0x23eb  ldloc.2
0x23ec  ldstr    aStatecode// "statecode"
0x23f1  ldc.i4.0
0x23f2  ldc.i4.3
0x23f3  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState
0x23f8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x23fd  pop
0x23fe  ldloc.1
0x23ff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2404  ldloc.2
0x2405  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x240a  ldloc.1
0x240b  ldarg.2
0x240c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2411  stloc.3
0x2412  ldloc.3
0x2413  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2418  ldc.i4.0
0x2419  ble      loc_24EE
0x241e  ldloc.3
0x241f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2424  stloc.s  4
0x2426  br       loc_24CB
0x242b  ldloc.s  4
0x242d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2432  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2437  stloc.s  5
0x2439  ldloc.s  5
0x243b  ldstr    aActivitytypeco// "activitytypecode"
0x2440  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2445  unbox.any [mscorlib]System.Int32
0x244a  ldarg.2
0x244b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2450  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GenericActivityServiceBase
0x2455  stloc.s  6
0x2457  ldloc.s  5
0x2459  ldstr    aActivitytypeco// "activitytypecode"
0x245e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2463  unbox.any [mscorlib]System.Int32
0x2468  ldarg.2
0x2469  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x246e  stloc.s  7
0x2470  ldloc.s  7
0x2472  brfalse.s loc_24A8
0x2474  ldloc.s  7
0x2476  ldstr    aActivityid// "activityid"
0x247b  ldloc.s  5
0x247d  ldstr    aActivityid// "activityid"
0x2482  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2487  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x248c  ldloc.s  7
0x248e  ldstr    aStatecode// "statecode"
0x2493  ldc.i4.2
0x2494  box      [mscorlib]System.Int32
0x2499  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x249e  ldloc.s  6
0x24a0  ldloc.s  7
0x24a2  ldarg.2
0x24a3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x24a8  leave.s  loc_24CB
0x24aa  ldarg.2
0x24ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x24b0  ldc.i4.6
0x24b1  ldstr    a0// "{0}"
0x24b6  ldc.i4.1
0x24b7  newarr   [mscorlib]System.Object
0x24bc  dup
0x24bd  ldc.i4.0
0x24be  ldstr    aErrorOccouredW// "Error occoured while checking open acti"...
0x24c3  stelem.ref
0x24c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24c9  leave.s  loc_24CB
0x24cb  ldloc.s  4
0x24cd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24d2  brtrue   loc_242B
0x24d7  leave.s  loc_24EE
0x24d9  ldloc.s  4
0x24db  isinst   [mscorlib]System.IDisposable
0x24e0  stloc.s  8
0x24e2  ldloc.s  8
0x24e4  brfalse.s loc_24ED
0x24e6  ldloc.s  8
0x24e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24ed  endfinally
0x24ee  ret
```
