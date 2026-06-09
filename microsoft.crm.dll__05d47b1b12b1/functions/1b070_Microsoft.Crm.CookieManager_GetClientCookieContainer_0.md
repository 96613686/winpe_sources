# Microsoft.Crm.CookieManager::GetClientCookieContainer_0

- ea: `0x1b070`
- end: `0x1b0b1`
- name: `Microsoft.Crm.CookieManager::GetClientCookieContainer_0`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1b060`

## callees

- `0x1b070`
- `0x1b160`
- `0x1b1d0`

## string_xrefs

- `0x1b071`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b070  ldarg.1
0x1b071  ldstr    aTargeturi// "targetUri"
0x1b076  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b07b  newobj   instance void [System]System.Net.CookieContainer::.ctor()
0x1b080  stloc.0
0x1b081  ldarg.0
0x1b082  call     string Microsoft.Crm.CookieManager::GetCookie(class [System]System.Uri targetUri)
0x1b087  stloc.1
0x1b088  ldloc.1
0x1b089  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b08e  brtrue.s loc_1B098
0x1b090  ldloc.0
0x1b091  ldarg.1
0x1b092  ldloc.1
0x1b093  callvirt instance void [System]System.Net.CookieContainer::SetCookies(class [System]System.Uri, string)
0x1b098  ldarg.0
0x1b099  call     string Microsoft.Crm.CookieManager::GetOutlookClientCookie(class [System]System.Uri targetUri)
0x1b09e  stloc.1
0x1b09f  ldloc.1
0x1b0a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b0a5  brtrue.s loc_1B0AF
0x1b0a7  ldloc.0
0x1b0a8  ldarg.1
0x1b0a9  ldloc.1
0x1b0aa  callvirt instance void [System]System.Net.CookieContainer::SetCookies(class [System]System.Uri, string)
0x1b0af  ldloc.0
0x1b0b0  ret
```
