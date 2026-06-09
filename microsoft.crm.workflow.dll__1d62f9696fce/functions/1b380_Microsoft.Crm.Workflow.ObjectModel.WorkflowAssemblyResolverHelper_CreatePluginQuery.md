# Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreatePluginQuery

- ea: `0x1b380`
- end: `0x1b511`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreatePluginQuery`
- size: `401`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b260`
- `0x1b280`
- `0x1b2a0`

## callees

- `0x1b380`

## string_xrefs

- `0x1b48c`: `pluginassemblyid`
- `0x1b491`: `pluginassemblyid`
- `0x1b4ba`: `pluginassemblyid`
- `0x1b41f`: `publickeytoken`
- `0x1b380`: `plugintype`
- `0x1b482`: `plugintype`
- `0x1b394`: `plugintypeid`
- `0x1b487`: `pluginassembly`

## pseudocode

```c

```

## disassembly

```asm
0x1b380  ldstr    aPlugintype// "plugintype"
0x1b385  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1b38a  stloc.0
0x1b38b  ldloc.0
0x1b38c  ldc.i4.4
0x1b38d  newarr   [mscorlib]System.String
0x1b392  dup
0x1b393  ldc.i4.0
0x1b394  ldstr    aPlugintypeid// "plugintypeid"
0x1b399  stelem.ref
0x1b39a  dup
0x1b39b  ldc.i4.1
0x1b39c  ldstr    aVersion// "version"
0x1b3a1  stelem.ref
0x1b3a2  dup
0x1b3a3  ldc.i4.2
0x1b3a4  ldstr    aName// "name"
0x1b3a9  stelem.ref
0x1b3aa  dup
0x1b3ab  ldc.i4.3
0x1b3ac  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1b3b1  stelem.ref
0x1b3b2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1b3b7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1b3bc  ldloc.0
0x1b3bd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b3c2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b3c7  ldstr    aIsworkflowacti// "isworkflowactivity"
0x1b3cc  ldc.i4.0
0x1b3cd  ldstr    a1// "1"
0x1b3d2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b3d7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b3dc  ldloc.0
0x1b3dd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b3e2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b3e7  ldstr    aAssemblyname// "assemblyname"
0x1b3ec  ldc.i4.0
0x1b3ed  ldarg.2
0x1b3ee  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b3f3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b3f8  ldloc.0
0x1b3f9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b3fe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b403  ldstr    aCulture// "culture"
0x1b408  ldc.i4.0
0x1b409  ldarg.3
0x1b40a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b40f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b414  ldloc.0
0x1b415  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b41a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b41f  ldstr    aPublickeytoken// "publickeytoken"
0x1b424  ldc.i4.0
0x1b425  ldarg.s  4
0x1b427  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b42c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b431  ldarg.s  5
0x1b433  brtrue.s loc_1B451
0x1b435  ldloc.0
0x1b436  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b43b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b440  ldstr    aName// "name"
0x1b445  ldc.i4.s 0xD
0x1b447  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x1b44c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b451  ldarg.1
0x1b452  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b457  brtrue.s loc_1B475
0x1b459  ldloc.0
0x1b45a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b45f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1b464  ldstr    aTypename// "typename"
0x1b469  ldc.i4.0
0x1b46a  ldarg.1
0x1b46b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b470  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1b475  ldarg.s  6
0x1b477  brfalse  loc_1B50F
0x1b47c  ldloc.0
0x1b47d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b482  ldstr    aPlugintype// "plugintype"
0x1b487  ldstr    aPluginassembly_1// "pluginassembly"
0x1b48c  ldstr    aPluginassembly// "pluginassemblyid"
0x1b491  ldstr    aPluginassembly// "pluginassemblyid"
0x1b496  ldc.i4.0
0x1b497  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x1b49c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x1b4a1  ldloc.0
0x1b4a2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b4a7  ldc.i4.0
0x1b4a8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x1b4ad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x1b4b2  ldc.i4.2
0x1b4b3  newarr   [mscorlib]System.String
0x1b4b8  dup
0x1b4b9  ldc.i4.0
0x1b4ba  ldstr    aPluginassembly// "pluginassemblyid"
0x1b4bf  stelem.ref
0x1b4c0  dup
0x1b4c1  ldc.i4.1
0x1b4c2  ldstr    aSourcetype// "sourcetype"
0x1b4c7  stelem.ref
0x1b4c8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x1b4cd  ldloc.0
0x1b4ce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b4d3  ldc.i4.0
0x1b4d4  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x1b4d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x1b4de  ldstr    aSourcetype// "sourcetype"
0x1b4e3  ldc.i4.1
0x1b4e4  ldc.i4.1
0x1b4e5  newarr   [mscorlib]System.Object
0x1b4ea  dup
0x1b4eb  ldc.i4.0
0x1b4ec  ldc.i4.3
0x1b4ed  box      [mscorlib]System.Int32
0x1b4f2  stelem.ref
0x1b4f3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1b4f8  ldloc.0
0x1b4f9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b4fe  ldc.i4.0
0x1b4ff  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x1b504  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x1b509  ldc.i4.0
0x1b50a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1b50f  ldloc.0
0x1b510  ret
```
