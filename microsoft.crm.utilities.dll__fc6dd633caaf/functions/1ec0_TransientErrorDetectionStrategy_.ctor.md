# TransientErrorDetectionStrategy::.ctor

- ea: `0x1ec0`
- end: `0x1efe`
- name: `TransientErrorDetectionStrategy::.ctor`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1b60`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldarg.0
0x1ec1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode>::.ctor()
0x1ec6  dup
0x1ec7  ldc.i4   0x1F8
0x1ecc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>)
0x1ed1  dup
0x1ed2  ldc.i4   0x198
0x1ed7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>)
0x1edc  dup
0x1edd  ldc.i4   0x1F7
0x1ee2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>)
0x1ee7  dup
0x1ee8  ldc.i4   0x1F4
0x1eed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>)
0x1ef2  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [System]System.Net.HttpStatusCode> TransientErrorDetectionStrategy::_statusCodes
0x1ef7  ldarg.0
0x1ef8  call     instance void [mscorlib]System.Object::.ctor()
0x1efd  ret
```
