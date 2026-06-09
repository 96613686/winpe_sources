# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ServiceClassName

- ea: `0x32280`
- end: `0x322aa`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ServiceClassName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x32280`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x32286`: `serviceclassname`
- `0x3229a`: `serviceclassname`

## pseudocode

```c

```

## disassembly

```asm
0x32280  ldarg.0
0x32281  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x32286  ldstr    aServiceclassna_0// "serviceclassname"
0x3228b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x32290  brfalse.s loc_32294
0x32292  ldnull
0x32293  ret
0x32294  ldarg.0
0x32295  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x3229a  ldstr    aServiceclassna_0// "serviceclassname"
0x3229f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x322a4  castclass [mscorlib]System.String
0x322a9  ret
```
