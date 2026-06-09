# Microsoft.Crm.Entities.RollupProperties::set_BootstrapStepNumber

- ea: `0x3410`
- end: `0x3442`
- name: `Microsoft.Crm.Entities.RollupProperties::set_BootstrapStepNumber`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3410`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldarga.s 1
0x3412  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x3417  brfalse.s loc_3431
0x3419  ldarg.0
0x341a  ldstr    aBootstrapstepn// "bootstrapstepnumber"
0x341f  ldarga.s 1
0x3421  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x3426  box      [mscorlib]System.Int32
0x342b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3430  ret
0x3431  ldarg.0
0x3432  ldstr    aBootstrapstepn// "bootstrapstepnumber"
0x3437  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x343c  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3441  ret
```
