# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_IsAIRUpdated

- ea: `0x31970`
- end: `0x3199a`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_IsAIRUpdated`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x31970`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x31976`: `isairupdated`
- `0x3198a`: `isairupdated`

## pseudocode

```c

```

## disassembly

```asm
0x31970  ldarg.0
0x31971  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x31976  ldstr    aIsairupdated_0// "isairupdated"
0x3197b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x31980  brfalse.s loc_31984
0x31982  ldc.i4.0
0x31983  ret
0x31984  ldarg.0
0x31985  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x3198a  ldstr    aIsairupdated_0// "isairupdated"
0x3198f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x31994  unbox.any [mscorlib]System.Boolean
0x31999  ret
```
