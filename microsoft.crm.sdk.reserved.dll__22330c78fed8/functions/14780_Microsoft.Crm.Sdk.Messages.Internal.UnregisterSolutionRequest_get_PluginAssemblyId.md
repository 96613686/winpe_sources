# Microsoft.Crm.Sdk.Messages.Internal.UnregisterSolutionRequest::get_PluginAssemblyId

- ea: `0x14780`
- end: `0x147b2`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UnregisterSolutionRequest::get_PluginAssemblyId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14780`

## string_xrefs

- `0x14786`: `PluginAssemblyId`
- `0x14798`: `PluginAssemblyId`

## pseudocode

```c

```

## disassembly

```asm
0x14780  ldarg.0
0x14781  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14786  ldstr    aPluginassembly_0// "PluginAssemblyId"
0x1478b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14790  brfalse.s loc_147A8
0x14792  ldarg.0
0x14793  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14798  ldstr    aPluginassembly_0// "PluginAssemblyId"
0x1479d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x147a2  unbox.any [mscorlib]System.Guid
0x147a7  ret
0x147a8  ldloca.s 0
0x147aa  initobj  [mscorlib]System.Guid
0x147b0  ldloc.0
0x147b1  ret
```
