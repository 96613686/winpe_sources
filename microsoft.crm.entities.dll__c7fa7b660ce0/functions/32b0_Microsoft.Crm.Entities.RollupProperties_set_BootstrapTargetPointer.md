# Microsoft.Crm.Entities.RollupProperties::set_BootstrapTargetPointer

- ea: `0x32b0`
- end: `0x32e2`
- name: `Microsoft.Crm.Entities.RollupProperties::set_BootstrapTargetPointer`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x32b0`

## pseudocode

```c

```

## disassembly

```asm
0x32b0  ldarga.s 1
0x32b2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x32b7  brfalse.s loc_32D1
0x32b9  ldarg.0
0x32ba  ldstr    aBootstraptarge// "bootstraptargetpointer"
0x32bf  ldarga.s 1
0x32c1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x32c6  box      [mscorlib]System.Int32
0x32cb  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32d0  ret
0x32d1  ldarg.0
0x32d2  ldstr    aBootstraptarge// "bootstraptargetpointer"
0x32d7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x32dc  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32e1  ret
```
