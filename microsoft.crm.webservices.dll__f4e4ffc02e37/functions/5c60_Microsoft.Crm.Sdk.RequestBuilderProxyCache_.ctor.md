# Microsoft.Crm.Sdk.RequestBuilderProxyCache::.ctor

- ea: `0x5c60`
- end: `0x5c6d`
- name: `Microsoft.Crm.Sdk.RequestBuilderProxyCache::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b30`

## string_xrefs

- `0x5c61`: `RequestBuilderProxyCache`

## pseudocode

```c

```

## disassembly

```asm
0x5c60  ldarg.0
0x5c61  ldstr    aRequestbuilder_0// "RequestBuilderProxyCache"
0x5c66  ldarg.1
0x5c67  call     instance void class Microsoft.Crm.Sdk.RequestBuilderCacheBase`1<class Microsoft.Crm.Sdk.RequestBuilderProxy>::.ctor(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<class Microsoft.Crm.Sdk.RequestBuilderKey, var<u1>>)
0x5c6c  ret
```
