# Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_ValidForUpdateApi

- ea: `0x25310`
- end: `0x2533a`
- name: `Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_ValidForUpdateApi`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x25310`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x25316`: `validforupdateapi`
- `0x2532a`: `validforupdateapi`

## pseudocode

```c

```

## disassembly

```asm
0x25310  ldarg.0
0x25311  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x25316  ldstr    aValidforupdate_1// "validforupdateapi"
0x2531b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x25320  brfalse.s loc_25324
0x25322  ldc.i4.0
0x25323  ret
0x25324  ldarg.0
0x25325  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x2532a  ldstr    aValidforupdate_1// "validforupdateapi"
0x2532f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x25334  unbox.any [mscorlib]System.Boolean
0x25339  ret
```
