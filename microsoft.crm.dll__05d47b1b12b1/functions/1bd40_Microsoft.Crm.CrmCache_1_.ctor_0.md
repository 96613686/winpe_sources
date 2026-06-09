# Microsoft.Crm.CrmCache`1::.ctor_0

- ea: `0x1bd40`
- end: `0x1bda2`
- name: `Microsoft.Crm.CrmCache`1::.ctor_0`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1bd60`: `cacheIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x1bd40  ldarg.0
0x1bd41  ldc.i4.1
0x1bd42  stfld    bool class Microsoft.Crm.CrmCache`1<var<u1>>::_enablePerThreadCacheManager
0x1bd47  ldarg.0
0x1bd48  ldc.i4.3
0x1bd49  stfld    valuetype [System.Web]System.Web.Caching.CacheItemPriority class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheItemPriority
0x1bd4e  ldarg.0
0x1bd4f  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x1bd54  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.CrmCache`1<var<u1>>::cacheLock
0x1bd59  ldarg.0
0x1bd5a  call     instance void [mscorlib]System.Object::.ctor()
0x1bd5f  ldarg.1
0x1bd60  ldstr    aCacheidentifie// "cacheIdentifier"
0x1bd65  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1bd6a  ldarg.0
0x1bd6b  ldarg.1
0x1bd6c  stfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1bd71  ldarg.0
0x1bd72  ldarg.s  4
0x1bd74  stfld    valuetype [mscorlib]System.TimeSpan class Microsoft.Crm.CrmCache`1<var<u1>>::_expirationLength
0x1bd79  ldarg.0
0x1bd7a  ldarg.s  5
0x1bd7c  stfld    bool class Microsoft.Crm.CrmCache`1<var<u1>>::_isExpirationSliding
0x1bd81  ldarg.0
0x1bd82  ldarg.s  6
0x1bd84  stfld    bool class Microsoft.Crm.CrmCache`1<var<u1>>::_enablePerThreadCacheManager
0x1bd89  ldarg.0
0x1bd8a  ldarg.s  7
0x1bd8c  stfld    bool class Microsoft.Crm.CrmCache`1<var<u1>>::_enableMemoryCache
0x1bd91  ldarg.0
0x1bd92  ldarg.s  8
0x1bd94  stfld    valuetype [System.Web]System.Web.Caching.CacheItemPriority class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheItemPriority
0x1bd99  ldarg.0
0x1bd9a  ldarg.2
0x1bd9b  ldarg.3
0x1bd9c  call     instance void class Microsoft.Crm.CrmCache`1<var<u1>>::RegisterEvents(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType[], class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x1bda1  ret
```
