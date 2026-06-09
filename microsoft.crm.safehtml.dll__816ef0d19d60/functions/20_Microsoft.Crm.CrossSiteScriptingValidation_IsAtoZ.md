# Microsoft.Crm.CrossSiteScriptingValidation::IsAtoZ

- ea: `0x20`
- end: `0x3c`
- name: `Microsoft.Crm.CrossSiteScriptingValidation::IsAtoZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x40`
- `0x1e0`

## callees

- `0x20`

## pseudocode

```c

```

## disassembly

```asm
0x20  ldarg.0
0x21  ldc.i4.s 0x61
0x23  blt.s    loc_2A
0x25  ldarg.0
0x26  ldc.i4.s 0x7A
0x28  ble.s    loc_3A
0x2a  ldarg.0
0x2b  ldc.i4.s 0x41
0x2d  blt.s    loc_38
0x2f  ldarg.0
0x30  ldc.i4.s 0x5A
0x32  cgt
0x34  ldc.i4.0
0x35  ceq
0x37  ret
0x38  ldc.i4.0
0x39  ret
0x3a  ldc.i4.1
0x3b  ret
```
