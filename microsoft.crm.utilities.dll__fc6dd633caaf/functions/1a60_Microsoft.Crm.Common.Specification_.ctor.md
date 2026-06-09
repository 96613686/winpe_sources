# Microsoft.Crm.Common.Specification::.ctor

- ea: `0x1a60`
- end: `0x1a8f`
- name: `Microsoft.Crm.Common.Specification::.ctor`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x12c0`

## callees

- `0x1a60`
- `0x1aa0`
- `0x1ac0`
- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldarg.0
0x1a61  call     instance void [mscorlib]System.Object::.ctor()
0x1a66  ldarg.1
0x1a67  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1a6c  brfalse.s loc_1A79
0x1a6e  ldstr    aProperty// "property"
0x1a73  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a78  throw
0x1a79  ldarg.0
0x1a7a  ldarg.2
0x1a7b  call     instance void Microsoft.Crm.Common.Specification::set_Comparison(valuetype Microsoft.Crm.Common.ComparisonOperator value)
0x1a80  ldarg.0
0x1a81  ldarg.3
0x1a82  call     instance void Microsoft.Crm.Common.Specification::set_Value(object value)
0x1a87  ldarg.0
0x1a88  ldarg.1
0x1a89  call     instance void Microsoft.Crm.Common.Specification::set_Property(string value)
0x1a8e  ret
```
