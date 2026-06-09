# Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegeDirectly

- ea: `0xd3600`
- end: `0xd36bd`
- name: `Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegeDirectly`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xd3600`

## string_xrefs

- `0xd3662`: `privilegedepthmask`
- `0xd3668`: `privilegedepthmask`
- `0xd362d`: `privilegeid`
- `0xd3633`: `privilegeid`
- `0xd3600`: `RolePrivileges`
- `0xd3696`: `RolePrivileges`
- `0xd364d`: `roleprivilegeid`

## pseudocode

```c

```

## disassembly

```asm
0xd3600  ldstr    aRoleprivileges// "RolePrivileges"
0xd3605  ldarg.2
0xd3606  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd360b  stloc.0
0xd360c  ldloc.0
0xd360d  ldstr    aRoleid// "roleid"
0xd3612  ldarg.1
0xd3613  ldstr    aRoleid// "roleid"
0xd3618  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd361d  unbox.any [mscorlib]System.Guid
0xd3622  box      [mscorlib]System.Guid
0xd3627  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0xd362c  ldloc.0
0xd362d  ldstr    aPrivilegeid// "privilegeid"
0xd3632  ldarg.1
0xd3633  ldstr    aPrivilegeid// "privilegeid"
0xd3638  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd363d  unbox.any [mscorlib]System.Guid
0xd3642  box      [mscorlib]System.Guid
0xd3647  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0xd364c  ldloc.0
0xd364d  ldstr    aRoleprivilegei// "roleprivilegeid"
0xd3652  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0xd3657  box      [mscorlib]System.Guid
0xd365c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0xd3661  ldloc.0
0xd3662  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd3667  ldarg.1
0xd3668  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd366d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd3672  unbox.any [mscorlib]System.Int32
0xd3677  box      [mscorlib]System.Int32
0xd367c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0xd3681  ldloc.0
0xd3682  ldstr    aSolutionid// "solutionid"
0xd3687  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0xd368c  box      [mscorlib]System.Guid
0xd3691  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0xd3696  ldstr    aRoleprivileges// "RolePrivileges"
0xd369b  ldloc.0
0xd369c  ldarg.2
0xd369d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CreatePlan::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd36a2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryPlan::get_Command()
0xd36a7  stloc.1
0xd36a8  ldloc.1
0xd36a9  ldarg.2
0xd36aa  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd36af  pop
0xd36b0  leave.s  loc_D36BC
0xd36b2  ldloc.1
0xd36b3  brfalse.s loc_D36BB
0xd36b5  ldloc.1
0xd36b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd36bb  endfinally
0xd36bc  ret
```
