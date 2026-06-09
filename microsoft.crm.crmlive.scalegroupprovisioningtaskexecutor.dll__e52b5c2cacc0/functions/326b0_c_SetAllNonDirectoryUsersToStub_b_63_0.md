# <>c::<SetAllNonDirectoryUsersToStub>b__63_0

- ea: `0x326b0`
- end: `0x3276f`
- name: `<>c::<SetAllNonDirectoryUsersToStub>b__63_0`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x326b0`

## string_xrefs

- `0x326e0`: `accessmode`
- `0x326f8`: `accessmode`
- `0x326c8`: `issyncwithdirectory`

## pseudocode

```c

```

## disassembly

```asm
0x326b0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisionSystemUserService::.ctor()
0x326b5  stloc.0
0x326b6  ldstr    aSystemuser// "SystemUser"
0x326bb  ldarg.1
0x326bc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x326c1  stloc.1
0x326c2  ldloc.1
0x326c3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x326c8  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x326cd  ldc.i4.0
0x326ce  ldc.i4.0
0x326cf  box      [mscorlib]System.Boolean
0x326d4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x326d9  pop
0x326da  ldloc.1
0x326db  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x326e0  ldstr    aAccessmode// "accessmode"
0x326e5  ldc.i4.1
0x326e6  ldc.i4.3
0x326e7  box      [mscorlib]System.Int32
0x326ec  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x326f1  pop
0x326f2  ldloc.1
0x326f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x326f8  ldstr    aAccessmode// "accessmode"
0x326fd  ldc.i4.1
0x326fe  ldc.i4.5
0x326ff  box      [mscorlib]System.Int32
0x32704  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x32709  pop
0x3270a  ldloc.0
0x3270b  ldloc.1
0x3270c  ldarg.1
0x3270d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32712  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x32717  stloc.2
0x32718  br.s     loc_32750
0x3271a  ldloc.2
0x3271b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32720  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x32725  stloc.3
0x32726  ldloc.3
0x32727  ldstr    aIslicensed// "islicensed"
0x3272c  ldc.i4.0
0x3272d  box      [mscorlib]System.Boolean
0x32732  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32737  ldloc.3
0x32738  ldstr    aIsdisabled// "isdisabled"
0x3273d  ldc.i4.1
0x3273e  box      [mscorlib]System.Boolean
0x32743  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32748  ldloc.0
0x32749  ldloc.3
0x3274a  ldarg.1
0x3274b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32750  ldloc.2
0x32751  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32756  brtrue.s loc_3271A
0x32758  leave.s  loc_3276E
0x3275a  ldloc.2
0x3275b  isinst   [mscorlib]System.IDisposable
0x32760  stloc.s  4
0x32762  ldloc.s  4
0x32764  brfalse.s loc_3276D
0x32766  ldloc.s  4
0x32768  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3276d  endfinally
0x3276e  ret
```
