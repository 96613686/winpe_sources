# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::.ctor

- ea: `0x2800`
- end: `0x2817`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::.ctor`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2640`

## pseudocode

```c

```

## disassembly

```asm
0x2800  ldarg.0
0x2801  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x2806  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x280b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x2810  ldarg.0
0x2811  call     instance void [mscorlib]System.Object::.ctor()
0x2816  ret
```
