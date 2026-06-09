# Microsoft.Crm.Sdk.RequestBuilderCache::.ctor

- ea: `0x56b0`
- end: `0x56c1`
- name: `Microsoft.Crm.Sdk.RequestBuilderCache::.ctor`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b30`

## callees

- `0xff10`

## string_xrefs

- `0x56b1`: `RequestBuilderCache`

## pseudocode

```c

```

## disassembly

```asm
0x56b0  ldarg.0
0x56b1  ldstr    aRequestbuilder// "RequestBuilderCache"
0x56b6  newobj   instance void RequestBuilderCacheLoader::.ctor()
0x56bb  call     instance void class Microsoft.Crm.Sdk.RequestBuilderCacheBase`1<class Microsoft.Crm.Sdk.RequestBuilder>::.ctor(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<class Microsoft.Crm.Sdk.RequestBuilderKey, var<u1>>)
0x56c0  ret
```
