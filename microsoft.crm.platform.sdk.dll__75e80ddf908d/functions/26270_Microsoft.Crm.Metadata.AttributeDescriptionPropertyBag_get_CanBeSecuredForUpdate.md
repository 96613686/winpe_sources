# Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_CanBeSecuredForUpdate

- ea: `0x26270`
- end: `0x2629a`
- name: `Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_CanBeSecuredForUpdate`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x26270`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x26276`: `canbesecuredforupdate`
- `0x2628a`: `canbesecuredforupdate`

## pseudocode

```c

```

## disassembly

```asm
0x26270  ldarg.0
0x26271  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x26276  ldstr    aCanbesecuredfo_4// "canbesecuredforupdate"
0x2627b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x26280  brfalse.s loc_26284
0x26282  ldc.i4.0
0x26283  ret
0x26284  ldarg.0
0x26285  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::_attributeData
0x2628a  ldstr    aCanbesecuredfo_4// "canbesecuredforupdate"
0x2628f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x26294  unbox.any [mscorlib]System.Boolean
0x26299  ret
```
