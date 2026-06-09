# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_AvailableForUpdate

- ea: `0x33140`
- end: `0x3316a`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_AvailableForUpdate`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x33140`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x33146`: `availableforupdate`
- `0x3315a`: `availableforupdate`

## pseudocode

```c

```

## disassembly

```asm
0x33140  ldarg.0
0x33141  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x33146  ldstr    aAvailableforup_0// "availableforupdate"
0x3314b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x33150  brfalse.s loc_33154
0x33152  ldc.i4.0
0x33153  ret
0x33154  ldarg.0
0x33155  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x3315a  ldstr    aAvailableforup_0// "availableforupdate"
0x3315f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x33164  unbox.any [mscorlib]System.Int32
0x33169  ret
```
