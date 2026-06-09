# <>c::<ClearAllOsdpSystemUserFields>b__64_0

- ea: `0x32770`
- end: `0x32827`
- name: `<>c::<ClearAllOsdpSystemUserFields>b__64_0`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x32770`

## string_xrefs

- `0x32788`: `accessmode`
- `0x327a0`: `accessmode`
- `0x327e0`: `issyncwithdirectory`
- `0x327f1`: `azureactivedirectoryobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x32770  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisionSystemUserService::.ctor()
0x32775  stloc.0
0x32776  ldstr    aSystemuser// "SystemUser"
0x3277b  ldarg.1
0x3277c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x32781  stloc.1
0x32782  ldloc.1
0x32783  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x32788  ldstr    aAccessmode// "accessmode"
0x3278d  ldc.i4.1
0x3278e  ldc.i4.3
0x3278f  box      [mscorlib]System.Int32
0x32794  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x32799  pop
0x3279a  ldloc.1
0x3279b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x327a0  ldstr    aAccessmode// "accessmode"
0x327a5  ldc.i4.1
0x327a6  ldc.i4.5
0x327a7  box      [mscorlib]System.Int32
0x327ac  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x327b1  pop
0x327b2  ldloc.0
0x327b3  ldloc.1
0x327b4  ldarg.1
0x327b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x327ba  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x327bf  stloc.2
0x327c0  br.s     loc_32808
0x327c2  ldloc.2
0x327c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x327c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x327cd  stloc.3
0x327ce  ldloc.3
0x327cf  ldstr    aIslicensed// "islicensed"
0x327d4  ldc.i4.0
0x327d5  box      [mscorlib]System.Boolean
0x327da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x327df  ldloc.3
0x327e0  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x327e5  ldc.i4.0
0x327e6  box      [mscorlib]System.Boolean
0x327eb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x327f0  ldloc.3
0x327f1  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x327f6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x327fb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32800  ldloc.0
0x32801  ldloc.3
0x32802  ldarg.1
0x32803  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32808  ldloc.2
0x32809  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3280e  brtrue.s loc_327C2
0x32810  leave.s  loc_32826
0x32812  ldloc.2
0x32813  isinst   [mscorlib]System.IDisposable
0x32818  stloc.s  4
0x3281a  ldloc.s  4
0x3281c  brfalse.s loc_32825
0x3281e  ldloc.s  4
0x32820  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32825  endfinally
0x32826  ret
```
