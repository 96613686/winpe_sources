# Microsoft.Crm.Sdk.Messages.Internal.GetImportMapXmlResponse::get_importMapXml

- ea: `0x134a0`
- end: `0x134ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetImportMapXmlResponse::get_importMapXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x134a0`

## string_xrefs

- `0x134a6`: `importMapXml`
- `0x134b8`: `importMapXml`

## pseudocode

```c

```

## disassembly

```asm
0x134a0  ldarg.0
0x134a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x134a6  ldstr    aImportmapxml// "importMapXml"
0x134ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x134b0  brfalse.s loc_134C8
0x134b2  ldarg.0
0x134b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x134b8  ldstr    aImportmapxml// "importMapXml"
0x134bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x134c2  castclass [mscorlib]System.String
0x134c7  ret
0x134c8  ldnull
0x134c9  ret
```
