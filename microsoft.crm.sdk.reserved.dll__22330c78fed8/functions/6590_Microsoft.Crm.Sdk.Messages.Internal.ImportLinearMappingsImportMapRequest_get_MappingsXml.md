# Microsoft.Crm.Sdk.Messages.Internal.ImportLinearMappingsImportMapRequest::get_MappingsXml

- ea: `0x6590`
- end: `0x65ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ImportLinearMappingsImportMapRequest::get_MappingsXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6590`

## string_xrefs

- `0x6596`: `MappingsXml`
- `0x65a8`: `MappingsXml`

## pseudocode

```c

```

## disassembly

```asm
0x6590  ldarg.0
0x6591  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6596  ldstr    aMappingsxml// "MappingsXml"
0x659b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x65a0  brfalse.s loc_65B8
0x65a2  ldarg.0
0x65a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x65a8  ldstr    aMappingsxml// "MappingsXml"
0x65ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x65b2  castclass [mscorlib]System.String
0x65b7  ret
0x65b8  ldnull
0x65b9  ret
```
