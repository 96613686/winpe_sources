# Microsoft.Crm.Entities.RollupProperties::set_Id

- ea: `0x2d20`
- end: `0x2d32`
- name: `Microsoft.Crm.Entities.RollupProperties::set_Id`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x2d21`: `rolluppropertiesid`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.0
0x2d21  ldstr    aRollupproperti_0// "rolluppropertiesid"
0x2d26  ldarg.1
0x2d27  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x2d2c  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2d31  ret
```
