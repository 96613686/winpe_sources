# Microsoft.Crm.CookieManager::GetOutlookClientCookie

- ea: `0x1b1d0`
- end: `0x1b20a`
- name: `Microsoft.Crm.CookieManager::GetOutlookClientCookie`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1b070`

## callees

- `0x1b1d0`
- `0x1b210`

## string_xrefs

- `0x1b1d1`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b1d0  ldarg.0
0x1b1d1  ldstr    aTargeturi// "targetUri"
0x1b1d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b1db  ldstr    aLightclient// "LightClient"
0x1b1e0  ldc.i4.0
0x1b1e1  box      [mscorlib]System.Int32
0x1b1e6  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1b1eb  unbox.any [mscorlib]System.Int32
0x1b1f0  ldc.i4.0
0x1b1f1  cgt.un
0x1b1f3  brtrue.s loc_1B1FC
0x1b1f5  ldstr    aFullclient// "FullClient"
0x1b1fa  br.s     loc_1B201
0x1b1fc  ldstr    aLightclient// "LightClient"
0x1b201  stloc.0
0x1b202  ldarg.0
0x1b203  ldloc.0
0x1b204  call     string Microsoft.Crm.CookieManager::GetOutlookClientCookieByName(class [System]System.Uri targetUri, string clientCookieName)
0x1b209  ret
```
