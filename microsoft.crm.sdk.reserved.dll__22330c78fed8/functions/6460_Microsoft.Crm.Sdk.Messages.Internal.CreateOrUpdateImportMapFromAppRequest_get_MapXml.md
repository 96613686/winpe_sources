# Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::get_MapXml

- ea: `0x6460`
- end: `0x648a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateOrUpdateImportMapFromAppRequest::get_MapXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x6460`

## string_xrefs

- `0x6466`: `MapXml`
- `0x6478`: `MapXml`

## pseudocode

```c

```

## disassembly

```asm
0x6460  ldarg.0
0x6461  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6466  ldstr    aMapxml// "MapXml"
0x646b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x6470  brfalse.s loc_6488
0x6472  ldarg.0
0x6473  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x6478  ldstr    aMapxml// "MapXml"
0x647d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6482  castclass [mscorlib]System.String
0x6487  ret
0x6488  ldnull
0x6489  ret
```
