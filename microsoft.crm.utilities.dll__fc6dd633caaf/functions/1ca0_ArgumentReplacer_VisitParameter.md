# ArgumentReplacer::VisitParameter

- ea: `0x1ca0`
- end: `0x1cac`
- name: `ArgumentReplacer::VisitParameter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldfld    object ArgumentReplacer::_argumentValue
0x1ca6  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object)
0x1cab  ret
```
