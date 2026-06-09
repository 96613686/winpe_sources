# Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_IsIdentity

- ea: `0x25820`
- end: `0x2584a`
- name: `Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_IsIdentity`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x25820`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x25826`: `isidentity`
- `0x2583a`: `isidentity`

## pseudocode

```c

```

## disassembly

```asm
0x25820  ldarg.0
0x25821  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x25826  ldstr    aIsidentity_0// "isidentity"
0x2582b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x25830  brfalse.s loc_25834
0x25832  ldc.i4.0
0x25833  ret
0x25834  ldarg.0
0x25835  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x2583a  ldstr    aIsidentity_0// "isidentity"
0x2583f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x25844  unbox.any [mscorlib]System.Boolean
0x25849  ret
```
