# Microsoft.Crm.CookieManager::SetSessionCookie

- ea: `0x1b430`
- end: `0x1b4a3`
- name: `Microsoft.Crm.CookieManager::SetSessionCookie`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1b4f0`
- `0x1b5c0`
- `0x1b5f0`

## string_xrefs

- `0x1b431`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b430  ldarg.0
0x1b431  ldstr    aTargeturi// "targetUri"
0x1b436  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b43b  ldarg.1
0x1b43c  ldstr    aCrmticket// "crmTicket"
0x1b441  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1b446  ldarg.2
0x1b447  ldstr    aExpirationdate// "expirationDate"
0x1b44c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1b451  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b456  ldstr    a0123// "{0}={1}&{2}={3};"
0x1b45b  ldc.i4.4
0x1b45c  newarr   [mscorlib]System.Object
0x1b461  dup
0x1b462  ldc.i4.0
0x1b463  ldstr    aTicket// "ticket"
0x1b468  stelem.ref
0x1b469  dup
0x1b46a  ldc.i4.1
0x1b46b  ldarg.1
0x1b46c  call     string Microsoft.Crm.CookieManager::EncodeCookie(string cookieValue)
0x1b471  stelem.ref
0x1b472  dup
0x1b473  ldc.i4.2
0x1b474  ldstr    aExpiration// "expiration"
0x1b479  stelem.ref
0x1b47a  dup
0x1b47b  ldc.i4.3
0x1b47c  ldarg.2
0x1b47d  call     string Microsoft.Crm.CookieManager::EncodeCookie(string cookieValue)
0x1b482  stelem.ref
0x1b483  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b488  stloc.0
0x1b489  ldarg.0
0x1b48a  ldloc.0
0x1b48b  call     string Microsoft.Crm.CookieManager::AppendSecureIfHttps(class [System]System.Uri targetUri, string cookieData)
0x1b490  stloc.0
0x1b491  ldarg.0
0x1b492  callvirt instance string [mscorlib]System.Object::ToString()
0x1b497  ldstr    aMscrmsession// "MSCRMSession"
0x1b49c  ldloc.0
0x1b49d  call     void Microsoft.Crm.CookieManager::SetCookie(string url, string name, string data)
0x1b4a2  ret
```
