# Microsoft.Crm.WebParameterAttribute::.ctor

- ea: `0xb10`
- end: `0xb1c`
- name: `Microsoft.Crm.WebParameterAttribute::.ctor`
- size: `12`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa50`
- `0xa70`
- `0xad0`
- `0x1570`
- `0x15d0`
- `0x1640`
- `0x1680`
- `0x16c0`
- `0x17f0`
- `0x1820`
- `0x1890`
- `0x1920`
- `0x1950`
- `0x1980`

## callees

- `0xb20`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldarg.0
0xb11  ldarg.1
0xb12  ldarg.2
0xb13  ldarg.3
0xb14  ldc.i4.0
0xb15  ldc.i4.0
0xb16  call     instance void Microsoft.Crm.WebParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterType parameterType, valuetype Microsoft.Crm.ParameterSources sources, bool allowMultipleValues, bool isPassThrough)
0xb1b  ret
```
