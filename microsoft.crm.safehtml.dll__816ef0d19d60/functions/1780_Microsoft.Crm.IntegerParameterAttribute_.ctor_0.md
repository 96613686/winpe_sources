# Microsoft.Crm.IntegerParameterAttribute::.ctor_0

- ea: `0x1780`
- end: `0x178c`
- name: `Microsoft.Crm.IntegerParameterAttribute::.ctor_0`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1770`
- `0x1850`
- `0x1860`

## callees

- `0xb20`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.0
0x1781  ldarg.1
0x1782  ldarg.2
0x1783  ldarg.3
0x1784  ldc.i4.1
0x1785  ldc.i4.0
0x1786  call     instance void Microsoft.Crm.WebParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterType parameterType, valuetype Microsoft.Crm.ParameterSources sources, bool allowMultipleValues, bool isPassThrough)
0x178b  ret
```
