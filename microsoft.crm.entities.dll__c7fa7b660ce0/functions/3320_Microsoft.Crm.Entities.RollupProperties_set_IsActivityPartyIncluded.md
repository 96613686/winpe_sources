# Microsoft.Crm.Entities.RollupProperties::set_IsActivityPartyIncluded

- ea: `0x3320`
- end: `0x3364`
- name: `Microsoft.Crm.Entities.RollupProperties::set_IsActivityPartyIncluded`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3320`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldarga.s 1
0x3322  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x3327  brfalse.s loc_3341
0x3329  ldarg.0
0x332a  ldstr    aIsactivitypart// "isactivitypartyincluded"
0x332f  ldarga.s 1
0x3331  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x3336  box      [mscorlib]System.Int32
0x333b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3340  ret
0x3341  ldarg.0
0x3342  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3347  ldstr    aIsactivitypart// "isactivitypartyincluded"
0x334c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x3351  brfalse.s loc_3363
0x3353  ldarg.0
0x3354  ldstr    aIsactivitypart// "isactivitypartyincluded"
0x3359  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x335e  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3363  ret
```
