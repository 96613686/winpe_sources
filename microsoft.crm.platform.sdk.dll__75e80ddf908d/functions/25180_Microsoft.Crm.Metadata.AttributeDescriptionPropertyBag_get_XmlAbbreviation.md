# Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_XmlAbbreviation

- ea: `0x25180`
- end: `0x251aa`
- name: `Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_XmlAbbreviation`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x25180`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x25186`: `xmlabbreviation`
- `0x2519a`: `xmlabbreviation`

## pseudocode

```c

```

## disassembly

```asm
0x25180  ldarg.0
0x25181  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x25186  ldstr    aXmlabbreviatio_1// "xmlabbreviation"
0x2518b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x25190  brfalse.s loc_25194
0x25192  ldnull
0x25193  ret
0x25194  ldarg.0
0x25195  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x2519a  ldstr    aXmlabbreviatio_1// "xmlabbreviation"
0x2519f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x251a4  castclass [mscorlib]System.String
0x251a9  ret
```
