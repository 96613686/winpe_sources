# Microsoft.Crm.ParameterValidationResult::.ctor_0

- ea: `0xa00`
- end: `0xa1c`
- name: `Microsoft.Crm.ParameterValidationResult::.ctor_0`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1700`
- `0x18e0`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldarg.0
0xa01  ldc.i4.1
0xa02  stfld    bool Microsoft.Crm.ParameterValidationResult::_isValid
0xa07  ldarg.0
0xa08  call     instance void [mscorlib]System.Object::.ctor()
0xa0d  ldarg.0
0xa0e  ldc.i4.0
0xa0f  stfld    bool Microsoft.Crm.ParameterValidationResult::_isValid
0xa14  ldarg.0
0xa15  ldarg.1
0xa16  stfld    class [mscorlib]System.Exception Microsoft.Crm.ParameterValidationResult::_exception
0xa1b  ret
```
