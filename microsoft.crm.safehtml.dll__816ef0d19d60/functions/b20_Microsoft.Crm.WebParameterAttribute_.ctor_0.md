# Microsoft.Crm.WebParameterAttribute::.ctor_0

- ea: `0xb20`
- end: `0xb54`
- name: `Microsoft.Crm.WebParameterAttribute::.ctor_0`
- size: `52`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa90`
- `0xab0`
- `0xb10`
- `0x1780`
- `0x18d0`

## callees

- `0xb20`

## pseudocode

```c

```

## disassembly

```asm
0xb20  ldarg.0
0xb21  call     instance void [mscorlib]System.Attribute::.ctor()
0xb26  ldarg.1
0xb27  brfalse.s loc_B35
0xb29  ldarg.0
0xb2a  ldarg.1
0xb2b  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xb30  stfld    string Microsoft.Crm.WebParameterAttribute::_name
0xb35  ldarg.0
0xb36  ldarg.s  4
0xb38  stfld    bool Microsoft.Crm.WebParameterAttribute::_allowMultipleValues
0xb3d  ldarg.0
0xb3e  ldarg.s  5
0xb40  stfld    bool Microsoft.Crm.WebParameterAttribute::_isPassThrough
0xb45  ldarg.0
0xb46  ldarg.2
0xb47  stfld    valuetype Microsoft.Crm.ParameterType Microsoft.Crm.WebParameterAttribute::_parameterType
0xb4c  ldarg.0
0xb4d  ldarg.3
0xb4e  stfld    valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.WebParameterAttribute::_sources
0xb53  ret
```
