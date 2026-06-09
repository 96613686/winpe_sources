# RetrievePluginTypesCommand::DecorateQuery

- ea: `0x9f1d0`
- end: `0x9f205`
- name: `RetrievePluginTypesCommand::DecorateQuery`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9cb20`
- `0x9cbb0`

## string_xrefs

- `0x9f1d8`: `pluginassemblyid`
- `0x9f1f2`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x9f1d0  ldloca.s 0
0x9f1d2  ldarg.0
0x9f1d3  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f1d8  ldstr    aPluginassembly_0// "pluginassemblyid"
0x9f1dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9f1e2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x9f1e7  ldarg.0
0x9f1e8  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f1ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9f1f2  ldstr    aPluginassembly_0// "pluginassemblyid"
0x9f1f7  ldc.i4.0
0x9f1f8  ldloc.0
0x9f1f9  box      [mscorlib]System.Guid
0x9f1fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x9f203  pop
0x9f204  ret
```
