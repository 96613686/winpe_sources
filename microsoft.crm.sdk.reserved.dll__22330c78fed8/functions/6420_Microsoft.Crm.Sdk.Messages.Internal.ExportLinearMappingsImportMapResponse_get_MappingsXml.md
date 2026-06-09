# Microsoft.Crm.Sdk.Messages.Internal.ExportLinearMappingsImportMapResponse::get_MappingsXml

- ea: `0x6420`
- end: `0x644a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportLinearMappingsImportMapResponse::get_MappingsXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6420`

## string_xrefs

- `0x6426`: `MappingsXml`
- `0x6438`: `MappingsXml`

## pseudocode

```c

```

## disassembly

```asm
0x6420  ldarg.0
0x6421  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x6426  ldstr    aMappingsxml// "MappingsXml"
0x642b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x6430  brfalse.s loc_6448
0x6432  ldarg.0
0x6433  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x6438  ldstr    aMappingsxml// "MappingsXml"
0x643d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6442  castclass [mscorlib]System.String
0x6447  ret
0x6448  ldnull
0x6449  ret
```
