# Microsoft.Crm.Common.MemoryCacheProvider::.ctor

- ea: `0x390`
- end: `0x3a8`
- name: `Microsoft.Crm.Common.MemoryCacheProvider::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x370`

## string_xrefs

- `0x397`: `MemoryCacheProvider`

## pseudocode

```c

```

## disassembly

```asm
0x390  ldarg.0
0x391  call     instance void [mscorlib]System.Object::.ctor()
0x396  ldarg.0
0x397  ldstr    aMemorycachepro// "MemoryCacheProvider"
0x39c  ldnull
0x39d  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::.ctor(string, class [System]System.Collections.Specialized.NameValueCollection)
0x3a2  call     instance void Microsoft.Crm.Common.MemoryCacheProvider::set_Cache(class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache value)
0x3a7  ret
```
