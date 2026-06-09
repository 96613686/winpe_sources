# Microsoft.Crm.Sdk.Messages.Internal.TestTopicModelRequest::get_ConfigurationUsedId

- ea: `0x18140`
- end: `0x18172`
- name: `Microsoft.Crm.Sdk.Messages.Internal.TestTopicModelRequest::get_ConfigurationUsedId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18140`

## string_xrefs

- `0x18146`: `ConfigurationUsedId`
- `0x18158`: `ConfigurationUsedId`

## pseudocode

```c

```

## disassembly

```asm
0x18140  ldarg.0
0x18141  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x18146  ldstr    aConfigurationu// "ConfigurationUsedId"
0x1814b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x18150  brfalse.s loc_18168
0x18152  ldarg.0
0x18153  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x18158  ldstr    aConfigurationu// "ConfigurationUsedId"
0x1815d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x18162  unbox.any [mscorlib]System.Guid
0x18167  ret
0x18168  ldloca.s 0
0x1816a  initobj  [mscorlib]System.Guid
0x18170  ldloc.0
0x18171  ret
```
