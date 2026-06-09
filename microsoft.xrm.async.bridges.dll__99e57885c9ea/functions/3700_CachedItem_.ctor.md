# CachedItem::.ctor

- ea: `0x3700`
- end: `0x3715`
- name: `CachedItem::.ctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x3700  ldarg.0
0x3701  call     instance void [mscorlib]System.Object::.ctor()
0x3706  ldarg.0
0x3707  ldarg.1
0x3708  stfld    var<u1> class CachedItem<var<u1>, !!T0>::<Value>k__BackingField
0x370d  ldarg.0
0x370e  ldarg.2
0x370f  stfld    valuetype [mscorlib]System.DateTimeOffset class CachedItem<var<u1>, !!T0>::<CachedAt>k__BackingField
0x3714  ret
```
