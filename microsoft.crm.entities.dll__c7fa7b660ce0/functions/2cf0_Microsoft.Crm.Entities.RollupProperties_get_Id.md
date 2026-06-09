# Microsoft.Crm.Entities.RollupProperties::get_Id

- ea: `0x2cf0`
- end: `0x2d18`
- name: `Microsoft.Crm.Entities.RollupProperties::get_Id`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x2cf0`

## string_xrefs

- `0x2cf1`: `rolluppropertiesid`
- `0x2d08`: `rolluppropertiesid`

## pseudocode

```c

```

## disassembly

```asm
0x2cf0  ldarg.0
0x2cf1  ldstr    aRollupproperti_0// "rolluppropertiesid"
0x2cf6  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2cfb  brtrue.s loc_2D07
0x2cfd  ldloca.s 0
0x2cff  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x2d05  ldloc.0
0x2d06  ret
0x2d07  ldarg.0
0x2d08  ldstr    aRollupproperti_0// "rolluppropertiesid"
0x2d0d  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d12  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x2d17  ret
```
