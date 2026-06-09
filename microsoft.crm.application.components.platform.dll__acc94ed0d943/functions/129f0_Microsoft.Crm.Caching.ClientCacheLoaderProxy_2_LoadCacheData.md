# Microsoft.Crm.Caching.ClientCacheLoaderProxy`2::LoadCacheData

- ea: `0x129f0`
- end: `0x12a37`
- name: `Microsoft.Crm.Caching.ClientCacheLoaderProxy`2::LoadCacheData`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x115b0`
- `0x129f0`

## string_xrefs

- `0x129f9`: `web service loader was not provided for this cache`
- `0x12a0b`: `Neither platform nor webservice loader were provided for this cache`

## pseudocode

```c

```

## disassembly

```asm
0x129f0  ldarg.0
0x129f1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.ClientCacheLoaderProxy`2<var<u1>, !!T0>::_webServiceLoader
0x129f6  brtrue.s loc_12A29
0x129f8  ldc.i4.0
0x129f9  ldstr    aWebServiceLoad// "web service loader was not provided for"...
0x129fe  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x12a03  ldarg.0
0x12a04  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.ClientCacheLoaderProxy`2<var<u1>, !!T0>::_platformLoader
0x12a09  brtrue.s loc_12A1B
0x12a0b  ldstr    aNeitherPlatfor// "Neither platform nor webservice loader "...
0x12a10  ldc.i4   0x80040216
0x12a15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x12a1a  throw
0x12a1b  ldarg.0
0x12a1c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.ClientCacheLoaderProxy`2<var<u1>, !!T0>::_platformLoader
0x12a21  ldarg.1
0x12a22  ldarg.2
0x12a23  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0>::LoadCacheData(void, var<u1>)
0x12a28  ret
0x12a29  ldarg.0
0x12a2a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.ClientCacheLoaderProxy`2<var<u1>, !!T0>::_webServiceLoader
0x12a2f  ldarg.1
0x12a30  ldarg.2
0x12a31  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0>::LoadCacheData(void, var<u1>)
0x12a36  ret
```
