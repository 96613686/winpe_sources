# Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::get_EntityGroupConfiguration

- ea: `0x6830`
- end: `0x685a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.SaveEntityGroupConfigurationRequest::get_EntityGroupConfiguration`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6830`

## string_xrefs

- `0x6836`: `EntityGroupConfiguration`
- `0x6848`: `EntityGroupConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x6830  ldarg.0
0x6831  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6836  ldstr    aEntitygroupcon// "EntityGroupConfiguration"
0x683b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x6840  brfalse.s loc_6858
0x6842  ldarg.0
0x6843  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6848  ldstr    aEntitygroupcon// "EntityGroupConfiguration"
0x684d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6852  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfigurationCollection
0x6857  ret
0x6858  ldnull
0x6859  ret
```
