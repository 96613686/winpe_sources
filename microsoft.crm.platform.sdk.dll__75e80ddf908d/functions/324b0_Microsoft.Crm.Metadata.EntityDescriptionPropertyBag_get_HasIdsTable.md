# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_HasIdsTable

- ea: `0x324b0`
- end: `0x324da`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_HasIdsTable`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x324b0`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x324b6`: `hasidstable`
- `0x324ca`: `hasidstable`

## pseudocode

```c

```

## disassembly

```asm
0x324b0  ldarg.0
0x324b1  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x324b6  ldstr    aHasidstable_0// "hasidstable"
0x324bb  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x324c0  brfalse.s loc_324C4
0x324c2  ldc.i4.0
0x324c3  ret
0x324c4  ldarg.0
0x324c5  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x324ca  ldstr    aHasidstable_0// "hasidstable"
0x324cf  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x324d4  unbox.any [mscorlib]System.Boolean
0x324d9  ret
```
