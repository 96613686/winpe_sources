# Microsoft.Crm.Sdk.Messages.Internal.RegisterSolutionResponse::get_PluginAssemblyId

- ea: `0x14730`
- end: `0x14762`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RegisterSolutionResponse::get_PluginAssemblyId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14730`

## string_xrefs

- `0x14736`: `PluginAssemblyId`
- `0x14748`: `PluginAssemblyId`

## pseudocode

```c

```

## disassembly

```asm
0x14730  ldarg.0
0x14731  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14736  ldstr    aPluginassembly_0// "PluginAssemblyId"
0x1473b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14740  brfalse.s loc_14758
0x14742  ldarg.0
0x14743  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14748  ldstr    aPluginassembly_0// "PluginAssemblyId"
0x1474d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14752  unbox.any [mscorlib]System.Guid
0x14757  ret
0x14758  ldloca.s 0
0x1475a  initobj  [mscorlib]System.Guid
0x14760  ldloc.0
0x14761  ret
```
