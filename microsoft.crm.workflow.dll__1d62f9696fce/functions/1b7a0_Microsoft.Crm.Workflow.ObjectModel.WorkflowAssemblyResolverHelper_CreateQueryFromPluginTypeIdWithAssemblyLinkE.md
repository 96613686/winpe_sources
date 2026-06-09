# Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreateQueryFromPluginTypeIdWithAssemblyLinkEntity

- ea: `0x1b7a0`
- end: `0x1b84d`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreateQueryFromPluginTypeIdWithAssemblyLinkEntity`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xfd0`
- `0x9000`

## string_xrefs

- `0x1b7f4`: `pluginassemblyid`
- `0x1b7f9`: `pluginassemblyid`
- `0x1b822`: `pluginassemblyid`
- `0x1b7a0`: `plugintype`
- `0x1b7ea`: `plugintype`
- `0x1b7b4`: `plugintypeid`
- `0x1b7ca`: `plugintypeid`
- `0x1b7ef`: `pluginassembly`
- `0x1b841`: `pluginassembly`

## pseudocode

```c

```

## disassembly

```asm
0x1b7a0  ldstr    aPlugintype// "plugintype"
0x1b7a5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1b7aa  stloc.0
0x1b7ab  ldloc.0
0x1b7ac  ldc.i4.1
0x1b7ad  newarr   [mscorlib]System.String
0x1b7b2  dup
0x1b7b3  ldc.i4.0
0x1b7b4  ldstr    aPlugintypeid// "plugintypeid"
0x1b7b9  stelem.ref
0x1b7ba  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1b7bf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1b7c4  ldloc.0
0x1b7c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1b7ca  ldstr    aPlugintypeid// "plugintypeid"
0x1b7cf  ldc.i4.0
0x1b7d0  ldc.i4.1
0x1b7d1  newarr   [mscorlib]System.Object
0x1b7d6  dup
0x1b7d7  ldc.i4.0
0x1b7d8  ldarg.0
0x1b7d9  box      [mscorlib]System.Guid
0x1b7de  stelem.ref
0x1b7df  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1b7e4  ldloc.0
0x1b7e5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b7ea  ldstr    aPlugintype// "plugintype"
0x1b7ef  ldstr    aPluginassembly_1// "pluginassembly"
0x1b7f4  ldstr    aPluginassembly// "pluginassemblyid"
0x1b7f9  ldstr    aPluginassembly// "pluginassemblyid"
0x1b7fe  ldc.i4.0
0x1b7ff  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x1b804  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x1b809  ldloc.0
0x1b80a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b80f  ldc.i4.0
0x1b810  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x1b815  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x1b81a  ldc.i4.2
0x1b81b  newarr   [mscorlib]System.String
0x1b820  dup
0x1b821  ldc.i4.0
0x1b822  ldstr    aPluginassembly// "pluginassemblyid"
0x1b827  stelem.ref
0x1b828  dup
0x1b829  ldc.i4.1
0x1b82a  ldstr    aSourcetype// "sourcetype"
0x1b82f  stelem.ref
0x1b830  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x1b835  ldloc.0
0x1b836  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x1b83b  ldc.i4.0
0x1b83c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x1b841  ldstr    aPluginassembly_1// "pluginassembly"
0x1b846  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_EntityAlias(string)
0x1b84b  ldloc.0
0x1b84c  ret
```
