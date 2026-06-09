# Microsoft.Crm.Application.ProcessControl.Configuration.BpfDataBuilder::GetAppEnabledEntityIds

- ea: `0x4a600`
- end: `0x4a73e`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfDataBuilder::GetAppEnabledEntityIds`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a440`

## callees

- `0x4a600`

## string_xrefs

- `0x4a652`: `AppModuleComponent`
- `0x4a675`: `AppModuleComponent`
- `0x4a6a7`: `componenttype`
- `0x4a705`: `AppModuleComponent.objectid`

## pseudocode

```c

```

## disassembly

```asm
0x4a600  ldc.i4.1
0x4a601  newarr   [mscorlib]System.String
0x4a606  dup
0x4a607  ldc.i4.0
0x4a608  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x4a60d  stelem.ref
0x4a60e  stloc.0
0x4a60f  ldc.i4.1
0x4a610  newarr   [mscorlib]System.String
0x4a615  dup
0x4a616  ldc.i4.0
0x4a617  ldstr    aObjectid// "objectid"
0x4a61c  stelem.ref
0x4a61d  stloc.1
0x4a61e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::.ctor()
0x4a623  ldarg.0
0x4a624  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4a629  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4a62e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4a633  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4a638  stloc.2
0x4a639  ldstr    aAppmodule// "AppModule"
0x4a63e  ldloc.2
0x4a63f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4a644  stloc.3
0x4a645  ldloc.3
0x4a646  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4a64b  ldloc.0
0x4a64c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4a651  ldloc.3
0x4a652  ldstr    aAppmodulecompo// "AppModuleComponent"
0x4a657  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x4a65c  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x4a661  ldc.i4.0
0x4a662  ldc.i4.0
0x4a663  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x4a668  pop
0x4a669  ldloc.3
0x4a66a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x4a66f  ldc.i4.0
0x4a670  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x4a675  ldstr    aAppmodulecompo// "AppModuleComponent"
0x4a67a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0x4a67f  ldloc.3
0x4a680  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x4a685  ldc.i4.0
0x4a686  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x4a68b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x4a690  ldloc.1
0x4a691  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4a696  ldloc.3
0x4a697  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x4a69c  ldc.i4.0
0x4a69d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Item(!!T0)
0x4a6a2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x4a6a7  ldstr    aComponenttype// "componenttype"
0x4a6ac  ldc.i4.0
0x4a6ad  ldc.i4.1
0x4a6ae  box      [mscorlib]System.Int32
0x4a6b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4a6b8  pop
0x4a6b9  ldloc.3
0x4a6ba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4a6bf  ldstr    aAppmoduleid// "appmoduleid"
0x4a6c4  ldc.i4.0
0x4a6c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4a6ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0x4a6cf  box      [mscorlib]System.Guid
0x4a6d4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4a6d9  pop
0x4a6da  ldloc.3
0x4a6db  ldarg.0
0x4a6dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4a6e1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4a6e6  stloc.s  4
0x4a6e8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4a6ed  stloc.s  5
0x4a6ef  br.s     loc_4A71B
0x4a6f1  ldloc.s  5
0x4a6f3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a6f8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4a6fd  ldloca.s 6
0x4a6ff  initobj  [mscorlib]System.Guid
0x4a705  ldstr    aAppmodulecompo_0// "AppModuleComponent.objectid"
0x4a70a  ldloca.s 6
0x4a70c  callvirt T0x2B00005B
0x4a711  pop
0x4a712  ldloc.s  4
0x4a714  ldloc.s  6
0x4a716  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x4a71b  ldloc.s  5
0x4a71d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a722  brtrue.s loc_4A6F1
0x4a724  leave.s  loc_4A73B
0x4a726  ldloc.s  5
0x4a728  isinst   [mscorlib]System.IDisposable
0x4a72d  stloc.s  7
0x4a72f  ldloc.s  7
0x4a731  brfalse.s loc_4A73A
0x4a733  ldloc.s  7
0x4a735  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a73a  endfinally
0x4a73b  ldloc.s  4
0x4a73d  ret
```
