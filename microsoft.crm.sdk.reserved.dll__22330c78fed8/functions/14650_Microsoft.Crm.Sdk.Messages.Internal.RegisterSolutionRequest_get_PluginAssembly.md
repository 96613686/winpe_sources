# Microsoft.Crm.Sdk.Messages.Internal.RegisterSolutionRequest::get_PluginAssembly

- ea: `0x14650`
- end: `0x1467a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RegisterSolutionRequest::get_PluginAssembly`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14650`

## string_xrefs

- `0x14656`: `PluginAssembly`
- `0x14668`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x14650  ldarg.0
0x14651  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14656  ldstr    aPluginassembly// "PluginAssembly"
0x1465b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14660  brfalse.s loc_14678
0x14662  ldarg.0
0x14663  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14668  ldstr    aPluginassembly// "PluginAssembly"
0x1466d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14672  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x14677  ret
0x14678  ldnull
0x14679  ret
```
