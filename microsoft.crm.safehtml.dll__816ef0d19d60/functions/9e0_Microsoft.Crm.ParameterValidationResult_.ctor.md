# Microsoft.Crm.ParameterValidationResult::.ctor

- ea: `0x9e0`
- end: `0x9f5`
- name: `Microsoft.Crm.ParameterValidationResult::.ctor`
- size: `21`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc40`
- `0x1580`
- `0x15e0`
- `0x1650`
- `0x1690`
- `0x1700`
- `0x17a0`
- `0x1800`
- `0x1830`
- `0x18a0`
- `0x18e0`
- `0x1930`
- `0x1960`
- `0x1990`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.0
0x9e1  ldc.i4.1
0x9e2  stfld    bool Microsoft.Crm.ParameterValidationResult::_isValid
0x9e7  ldarg.0
0x9e8  call     instance void [mscorlib]System.Object::.ctor()
0x9ed  ldarg.0
0x9ee  ldarg.1
0x9ef  stfld    bool Microsoft.Crm.ParameterValidationResult::_isValid
0x9f4  ret
```
