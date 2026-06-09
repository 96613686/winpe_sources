# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ExtensionTableName

- ea: `0x30490`
- end: `0x304ba`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ExtensionTableName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x30490`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x30496`: `extensiontablename`
- `0x304aa`: `extensiontablename`

## pseudocode

```c

```

## disassembly

```asm
0x30490  ldarg.0
0x30491  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x30496  ldstr    aExtensiontable_0// "extensiontablename"
0x3049b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x304a0  brfalse.s loc_304A4
0x304a2  ldnull
0x304a3  ret
0x304a4  ldarg.0
0x304a5  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x304aa  ldstr    aExtensiontable_0// "extensiontablename"
0x304af  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x304b4  castclass [mscorlib]System.String
0x304b9  ret
```
