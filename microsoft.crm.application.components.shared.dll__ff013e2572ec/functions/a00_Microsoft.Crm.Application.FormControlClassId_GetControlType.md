# Microsoft.Crm.Application.FormControlClassId::GetControlType

- ea: `0xa00`
- end: `0xa13`
- name: `Microsoft.Crm.Application.FormControlClassId::GetControlType`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xa00`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0xa05  ldarg.0
0xa06  ldloca.s 0
0xa08  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::TryGetValue(var<u1>, !!T0)
0xa0d  brfalse.s loc_A11
0xa0f  ldloc.0
0xa10  ret
0xa11  ldc.i4.0
0xa12  ret
```
