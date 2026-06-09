# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::.ctor

- ea: `0x10c0`
- end: `0x10e4`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10c0  ldarg.0
0x10c1  call     instance void [mscorlib]System.Object::.ctor()
0x10c6  ldarg.0
0x10c7  ldarg.1
0x10c8  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::inner
0x10cd  ldarg.0
0x10ce  ldarg.2
0x10cf  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::cache
0x10d4  ldarg.0
0x10d5  ldarg.3
0x10d6  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::events
0x10db  ldarg.0
0x10dc  ldarg.s  4
0x10de  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecureStringConverter Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::secureStringConverter
0x10e3  ret
```
