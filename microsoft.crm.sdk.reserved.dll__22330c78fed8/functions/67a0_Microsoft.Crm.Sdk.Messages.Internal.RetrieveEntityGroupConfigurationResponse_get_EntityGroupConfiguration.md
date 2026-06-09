# Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntityGroupConfigurationResponse::get_EntityGroupConfiguration

- ea: `0x67a0`
- end: `0x67ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntityGroupConfigurationResponse::get_EntityGroupConfiguration`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x67a0`

## string_xrefs

- `0x67a6`: `EntityGroupConfiguration`
- `0x67b8`: `EntityGroupConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x67a0  ldarg.0
0x67a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x67a6  ldstr    aEntitygroupcon// "EntityGroupConfiguration"
0x67ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x67b0  brfalse.s loc_67C8
0x67b2  ldarg.0
0x67b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x67b8  ldstr    aEntitygroupcon// "EntityGroupConfiguration"
0x67bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x67c2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfigurationCollection
0x67c7  ret
0x67c8  ldnull
0x67c9  ret
```
