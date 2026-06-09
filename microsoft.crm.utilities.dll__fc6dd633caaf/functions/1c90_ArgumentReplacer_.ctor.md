# ArgumentReplacer::.ctor

- ea: `0x1c90`
- end: `0x1c9e`
- name: `ArgumentReplacer::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x630`

## pseudocode

```c

```

## disassembly

```asm
0x1c90  ldarg.0
0x1c91  call     instance void [System.Core]System.Linq.Expressions.ExpressionVisitor::.ctor()
0x1c96  ldarg.0
0x1c97  ldarg.1
0x1c98  stfld    object ArgumentReplacer::_argumentValue
0x1c9d  ret
```
