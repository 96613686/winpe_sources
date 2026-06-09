# Microsoft.Crm.Entities.RollupProperties::set_BootstrapRetryCount

- ea: `0x3480`
- end: `0x34b2`
- name: `Microsoft.Crm.Entities.RollupProperties::set_BootstrapRetryCount`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3480`

## pseudocode

```c

```

## disassembly

```asm
0x3480  ldarga.s 1
0x3482  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x3487  brfalse.s loc_34A1
0x3489  ldarg.0
0x348a  ldstr    aBootstrapretry// "bootstrapretrycount"
0x348f  ldarga.s 1
0x3491  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x3496  box      [mscorlib]System.Int32
0x349b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x34a0  ret
0x34a1  ldarg.0
0x34a2  ldstr    aBootstrapretry// "bootstrapretrycount"
0x34a7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x34ac  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x34b1  ret
```
