# Microsoft.Crm.IntegerParameterAttribute::IsValid

- ea: `0x17a0`
- end: `0x17d8`
- name: `Microsoft.Crm.IntegerParameterAttribute::IsValid`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1790`
- `0x1870`

## callees

- `0x9e0`
- `0x17a0`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldarg.1
0x17a1  ldstr    aUndefined// "undefined"
0x17a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17ab  brfalse.s loc_17B4
0x17ad  ldc.i4.1
0x17ae  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(bool isValid)
0x17b3  ret
0x17b4  ldarg.1
0x17b5  ldloca.s 0
0x17b7  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x17bc  brfalse.s loc_17D1
0x17be  ldarg.2
0x17bf  brfalse.s loc_17CA
0x17c1  ldloc.0
0x17c2  ldc.i4.0
0x17c3  clt
0x17c5  ldc.i4.0
0x17c6  ceq
0x17c8  br.s     loc_17CB
0x17ca  ldc.i4.1
0x17cb  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(bool isValid)
0x17d0  ret
0x17d1  ldc.i4.0
0x17d2  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(bool isValid)
0x17d7  ret
```
