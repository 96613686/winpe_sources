# Microsoft.Crm.PageParametersCache::.ctor

- ea: `0x3a0`
- end: `0x3be`
- name: `Microsoft.Crm.PageParametersCache::.ctor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xe50`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.0
0x3a1  call     instance void [mscorlib]System.Object::.ctor()
0x3a6  ldarg.0
0x3a7  ldc.i4.1
0x3a8  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x3ad  stfld    class [System]System.Collections.Specialized.HybridDictionary Microsoft.Crm.PageParametersCache::_pageParametersCache
0x3b2  ldarg.0
0x3b3  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x3b8  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x3bd  ret
```
