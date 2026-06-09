# Microsoft.Crm.XmlStringParameterAttribute::.ctor

- ea: `0x1980`
- end: `0x198b`
- name: `Microsoft.Crm.XmlStringParameterAttribute::.ctor`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc60`

## callees

- `0xb10`

## pseudocode

```c

```

## disassembly

```asm
0x1980  ldarg.0
0x1981  ldarg.1
0x1982  ldc.i4.s 0xE
0x1984  ldarg.2
0x1985  call     instance void Microsoft.Crm.WebParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterType parameterType, valuetype Microsoft.Crm.ParameterSources sources)
0x198a  ret
```
