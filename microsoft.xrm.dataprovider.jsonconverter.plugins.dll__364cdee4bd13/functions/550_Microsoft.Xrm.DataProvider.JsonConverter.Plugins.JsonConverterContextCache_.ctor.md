# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::.ctor

- ea: `0x550`
- end: `0x5d8`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::.ctor`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1590`

## callees

- `0x1c40`

## pseudocode

```c

```

## disassembly

```asm
0x550  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x555  stloc.0
0x556  ldloc.0
0x557  ldarg.1
0x558  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass4_0::logger
0x55d  ldarg.0
0x55e  call     instance void [mscorlib]System.Object::.ctor()
0x563  nop
0x564  nop
0x565  ldarg.0
0x566  newobj   instance void [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions::.ctor()
0x56b  stfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::options
0x570  ldarg.0
0x571  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::options
0x576  ldc.i4.1
0x577  callvirt instance void [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions::set_CompactOnMemoryPressure(bool)
0x57c  nop
0x57d  ldarg.0
0x57e  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::options
0x583  ldc.r8   3.0
0x58c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x591  callvirt instance void [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions::set_ExpirationScanFrequency(valuetype [mscorlib]System.TimeSpan)
0x596  nop
0x597  ldarg.0
0x598  ldarg.0
0x599  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::options
0x59e  newobj   instance void [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCache::.ctor(class [Microsoft.Extensions.Options]Microsoft.Extensions.Options.IOptions`1<class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCacheOptions>)
0x5a3  stfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::memCache
0x5a8  ldarg.0
0x5a9  newobj   instance void [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions::.ctor()
0x5ae  ldc.r8   8.0
0x5b7  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x5bc  call     class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryExtensions::SetSlidingExpiration(class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions, valuetype [mscorlib]System.TimeSpan)
0x5c1  ldloc.0
0x5c2  ldftn    instance void <>c__DisplayClass4_0::<.ctor>b__0(object key, object value, valuetype [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.EvictionReason reason, object state)
0x5c8  newobj   instance void [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.PostEvictionDelegate::.ctor(object, native int)
0x5cd  call     class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryExtensions::RegisterPostEvictionCallback(class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions, class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.PostEvictionDelegate)
0x5d2  stfld    class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::cacheEntryOptions
0x5d7  ret
```
