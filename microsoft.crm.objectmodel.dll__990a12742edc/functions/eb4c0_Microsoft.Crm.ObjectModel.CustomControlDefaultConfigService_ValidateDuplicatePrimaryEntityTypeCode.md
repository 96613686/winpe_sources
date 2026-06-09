# Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateDuplicatePrimaryEntityTypeCode

- ea: `0xeb4c0`
- end: `0xeb626`
- name: `Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::ValidateDuplicatePrimaryEntityTypeCode`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xeb400`

## callees

- `0xeb4c0`

## string_xrefs

- `0xeb4d1`: `CustomControlDefaultConfig`
- `0xeb4f0`: `CustomControlDefaultConfig`
- `0xeb4fc`: `CustomControlDefaultConfig`
- `0xeb579`: `CustomControlDefaultConfig`
- `0xeb54f`: `CustomControl import default config failed because of insert duplicate key {0}.`
- `0xeb5fb`: `CustomControl import default config failed because of insert duplicate key {0}.`
- `0xeb593`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0xeb4c0  ldarg.1
0xeb4c1  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb4c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xeb4cb  unbox.any [mscorlib]System.Int32
0xeb4d0  stloc.0
0xeb4d1  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb4d6  ldarg.2
0xeb4d7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb4dc  stloc.1
0xeb4dd  ldloc.1
0xeb4de  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb4e3  ldc.i4.0
0xeb4e4  ldloc.0
0xeb4e5  box      [mscorlib]System.Int32
0xeb4ea  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xeb4ef  pop
0xeb4f0  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb4f5  ldarg.2
0xeb4f6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb4fb  stloc.2
0xeb4fc  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb501  ldarg.2
0xeb502  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xeb507  dup
0xeb508  ldloc.1
0xeb509  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xeb50e  ldloc.2
0xeb50f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0xeb514  ldarg.2
0xeb515  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb51a  stloc.s  4
0xeb51c  ldarg.0
0xeb51d  ldloc.1
0xeb51e  ldarg.2
0xeb51f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb524  stloc.s  5
0xeb526  ldloc.s  5
0xeb528  brfalse.s loc_EB56B
0xeb52a  ldloc.s  5
0xeb52c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xeb531  ldc.i4.0
0xeb532  ble.s    loc_EB56B
0xeb534  ldstr    aCannotInsertDu// "Cannot insert duplicate key."
0xeb539  ldc.i4   0x80040237
0xeb53e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmDuplicateRecordException::.ctor(string, int32)
0xeb543  stloc.s  6
0xeb545  ldloc.s  6
0xeb547  ldarg.2
0xeb548  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb54d  ldc.i4.s 0x11
0xeb54f  ldstr    aCustomcontrolI// "CustomControl import default config fai"...
0xeb554  ldc.i4.1
0xeb555  newarr   [mscorlib]System.Object
0xeb55a  dup
0xeb55b  ldc.i4.0
0xeb55c  ldloc.0
0xeb55d  box      [mscorlib]System.Int32
0xeb562  stelem.ref
0xeb563  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb568  ldloc.s  6
0xeb56a  throw
0xeb56b  leave.s  loc_EB579
0xeb56d  ldloc.s  4
0xeb56f  brfalse.s loc_EB578
0xeb571  ldloc.s  4
0xeb573  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeb578  endfinally
0xeb579  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0xeb57e  ldarg.2
0xeb57f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xeb584  stloc.3
0xeb585  ldloc.3
0xeb586  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xeb58b  ldc.i4.1
0xeb58c  newarr   [mscorlib]System.String
0xeb591  dup
0xeb592  ldc.i4.0
0xeb593  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0xeb598  stelem.ref
0xeb599  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xeb59e  ldloc.3
0xeb59f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xeb5a4  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xeb5a9  ldc.i4.0
0xeb5aa  ldc.i4.1
0xeb5ab  newarr   [mscorlib]System.Object
0xeb5b0  dup
0xeb5b1  ldc.i4.0
0xeb5b2  ldloc.0
0xeb5b3  box      [mscorlib]System.Int32
0xeb5b8  stelem.ref
0xeb5b9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xeb5be  pop
0xeb5bf  ldarg.2
0xeb5c0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb5c5  stloc.s  4
0xeb5c7  ldarg.0
0xeb5c8  ldloc.3
0xeb5c9  ldc.i4.1
0xeb5ca  ldarg.2
0xeb5cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeb5d0  stloc.s  7
0xeb5d2  ldloc.s  7
0xeb5d4  brfalse.s loc_EB617
0xeb5d6  ldloc.s  7
0xeb5d8  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xeb5dd  ldc.i4.0
0xeb5de  ble.s    loc_EB617
0xeb5e0  ldstr    aCannotInsertDu// "Cannot insert duplicate key."
0xeb5e5  ldc.i4   0x80040237
0xeb5ea  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmDuplicateRecordException::.ctor(string, int32)
0xeb5ef  stloc.s  8
0xeb5f1  ldloc.s  8
0xeb5f3  ldarg.2
0xeb5f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeb5f9  ldc.i4.s 0x11
0xeb5fb  ldstr    aCustomcontrolI// "CustomControl import default config fai"...
0xeb600  ldc.i4.1
0xeb601  newarr   [mscorlib]System.Object
0xeb606  dup
0xeb607  ldc.i4.0
0xeb608  ldloc.0
0xeb609  box      [mscorlib]System.Int32
0xeb60e  stelem.ref
0xeb60f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb614  ldloc.s  8
0xeb616  throw
0xeb617  leave.s  loc_EB625
0xeb619  ldloc.s  4
0xeb61b  brfalse.s loc_EB624
0xeb61d  ldloc.s  4
0xeb61f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeb624  endfinally
0xeb625  ret
```
