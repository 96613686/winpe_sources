# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::CacheSecret

- ea: `0x1250`
- end: `0x127c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::CacheSecret`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3570`

## callees

- `0x1570`
- `0x1730`

## string_xrefs

- `0x1271`: `ExpiringSecretCache`

## pseudocode

```c

```

## disassembly

```asm
0x1250  ldarg.0
0x1251  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecureStringConverter Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::secureStringConverter
0x1256  ldarg.2
0x1257  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Xrm.Async.Bridges.FromCommon.ISecureStringConverter::ToSecureString(string item)
0x125c  stloc.0
0x125d  ldarg.0
0x125e  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString> Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::cache
0x1263  ldarg.1
0x1264  ldloc.0
0x1265  callvirt instance void class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<string, class [mscorlib]System.Security.SecureString>::Put(var<u1>, !!T0)
0x126a  ldarg.0
0x126b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::events
0x1270  ldarg.1
0x1271  ldstr    aExpiringsecret// "ExpiringSecretCache"
0x1276  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnCompleteFind(string key, string callerType)
0x127b  ret
```
