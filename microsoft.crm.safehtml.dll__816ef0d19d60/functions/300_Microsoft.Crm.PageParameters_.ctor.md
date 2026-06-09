# Microsoft.Crm.PageParameters::.ctor

- ea: `0x300`
- end: `0x328`
- name: `Microsoft.Crm.PageParameters::.ctor`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x660`
- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.0
0x301  call     instance void [mscorlib]System.Object::.ctor()
0x306  ldarg.0
0x307  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x30c  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::_queryStringParameters
0x311  ldarg.0
0x312  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x317  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::_formParameters
0x31c  ldarg.0
0x31d  ldsfld   string [mscorlib]System.String::Empty
0x322  stfld    string Microsoft.Crm.PageParameters::_pagephysicalPath
0x327  ret
```
