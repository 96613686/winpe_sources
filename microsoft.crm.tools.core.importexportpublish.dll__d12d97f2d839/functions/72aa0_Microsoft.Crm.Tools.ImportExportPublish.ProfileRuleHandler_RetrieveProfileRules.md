# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveProfileRules

- ea: `0x72aa0`
- end: `0x72b3b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveProfileRules`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x72860`
- `0x72c30`

## string_xrefs

- `0x72ac6`: `channelaccessprofileruleid`
- `0x72b0f`: `channelaccessprofileruleid`
- `0x72aa0`: `ChannelAccessProfileRule`
- `0x72aac`: `ChannelAccessProfileRule`

## pseudocode

```c

```

## disassembly

```asm
0x72aa0  ldstr    aChannelaccessp_16// "ChannelAccessProfileRule"
0x72aa5  ldarg.2
0x72aa6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72aab  stloc.0
0x72aac  ldstr    aChannelaccessp_16// "ChannelAccessProfileRule"
0x72ab1  ldarg.2
0x72ab2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x72ab7  stloc.1
0x72ab8  ldloc.1
0x72ab9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x72abe  ldc.i4.8
0x72abf  newarr   [mscorlib]System.String
0x72ac4  dup
0x72ac5  ldc.i4.0
0x72ac6  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72acb  stelem.ref
0x72acc  dup
0x72acd  ldc.i4.1
0x72ace  ldstr    aName// "name"
0x72ad3  stelem.ref
0x72ad4  dup
0x72ad5  ldc.i4.2
0x72ad6  ldstr    aDescription// "description"
0x72adb  stelem.ref
0x72adc  dup
0x72add  ldc.i4.3
0x72ade  ldstr    aStatuscode// "statuscode"
0x72ae3  stelem.ref
0x72ae4  dup
0x72ae5  ldc.i4.4
0x72ae6  ldstr    aStatecode// "statecode"
0x72aeb  stelem.ref
0x72aec  dup
0x72aed  ldc.i4.5
0x72aee  ldstr    aSolutionid// "solutionid"
0x72af3  stelem.ref
0x72af4  dup
0x72af5  ldc.i4.6
0x72af6  ldstr    aIsmanaged// "ismanaged"
0x72afb  stelem.ref
0x72afc  dup
0x72afd  ldc.i4.7
0x72afe  ldstr    aWorkflowid_0// "workflowid"
0x72b03  stelem.ref
0x72b04  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x72b09  ldloc.1
0x72b0a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x72b0f  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72b14  ldc.i4.8
0x72b15  ldarg.1
0x72b16  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x72b1b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x72b20  pop
0x72b21  ldloc.1
0x72b22  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x72b27  ldstr    aName// "name"
0x72b2c  ldc.i4.0
0x72b2d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x72b32  ldloc.0
0x72b33  ldloc.1
0x72b34  ldarg.2
0x72b35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72b3a  ret
```
