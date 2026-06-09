# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::GetCachedSecret

- ea: `0x1210`
- end: `0x1246`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::GetCachedSecret`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3570`

## callees

- `0x1210`
- `0x1610`
- `0x1720`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldarga.s 2
0x1212  call     instance bool Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions::get_ForceRefresh()
0x1217  brfalse.s loc_1227
0x1219  ldarg.0
0x121a  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::cache
0x121f  ldarg.1
0x1220  callvirt instance void class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString>::Expire(var<u1>)
0x1225  ldnull
0x1226  ret
0x1227  ldarg.0
0x1228  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::cache
0x122d  ldarg.1
0x122e  ldloca.s 0
0x1230  callvirt instance bool class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString>::TryGet(var<u1>, !!T0)
0x1235  brtrue.s loc_1239
0x1237  ldnull
0x1238  ret
0x1239  ldarg.0
0x123a  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecureStringConverter Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::secureStringConverter
0x123f  ldloc.0
0x1240  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommon.ISecureStringConverter::ToString(class [mscorlib]System.Security.SecureString secureString)
0x1245  ret
```
