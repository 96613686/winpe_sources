# Microsoft.Crm.Entities.RollupProperties::set_BootstrapCurrentDepth

- ea: `0x33a0`
- end: `0x33d2`
- name: `Microsoft.Crm.Entities.RollupProperties::set_BootstrapCurrentDepth`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x33a0`

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarga.s 1
0x33a2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x33a7  brfalse.s loc_33C1
0x33a9  ldarg.0
0x33aa  ldstr    aBootstrapcurre// "bootstrapcurrentdepth"
0x33af  ldarga.s 1
0x33b1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x33b6  box      [mscorlib]System.Int32
0x33bb  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x33c0  ret
0x33c1  ldarg.0
0x33c2  ldstr    aBootstrapcurre// "bootstrapcurrentdepth"
0x33c7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x33cc  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x33d1  ret
```
