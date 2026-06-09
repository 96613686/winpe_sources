# Microsoft.Crm.CookieManager::SetCookie

- ea: `0x1b390`
- end: `0x1b42b`
- name: `Microsoft.Crm.CookieManager::SetCookie`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1b4f0`
- `0x1b5c0`
- `0x1b5f0`

## string_xrefs

- `0x1b391`: `targetUri`
- `0x1b3b7`: `Setting cookie. Uri:{0}, expiration:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x1b390  ldarg.0
0x1b391  ldstr    aTargeturi// "targetUri"
0x1b396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b39b  ldarg.1
0x1b39c  ldstr    aCrmticket// "crmTicket"
0x1b3a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1b3a6  ldarg.2
0x1b3a7  ldstr    aExpirationdate// "expirationDate"
0x1b3ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1b3b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b3b6  ldc.i4.1
0x1b3b7  ldstr    aSettingCookieU// "Setting cookie. Uri:{0}, expiration:{1}"
0x1b3bc  ldc.i4.2
0x1b3bd  newarr   [mscorlib]System.Object
0x1b3c2  dup
0x1b3c3  ldc.i4.0
0x1b3c4  ldarg.0
0x1b3c5  callvirt instance string [mscorlib]System.Object::ToString()
0x1b3ca  stelem.ref
0x1b3cb  dup
0x1b3cc  ldc.i4.1
0x1b3cd  ldarg.2
0x1b3ce  callvirt instance string [mscorlib]System.Object::ToString()
0x1b3d3  stelem.ref
0x1b3d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b3d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b3de  ldstr    a0123ExpiresTue// "{0}={1}&{2}={3}; expires = Tue,01-Jan-2"...
0x1b3e3  ldc.i4.4
0x1b3e4  newarr   [mscorlib]System.Object
0x1b3e9  dup
0x1b3ea  ldc.i4.0
0x1b3eb  ldstr    aTicket// "ticket"
0x1b3f0  stelem.ref
0x1b3f1  dup
0x1b3f2  ldc.i4.1
0x1b3f3  ldarg.1
0x1b3f4  call     string Microsoft.Crm.CookieManager::EncodeCookie(string cookieValue)
0x1b3f9  stelem.ref
0x1b3fa  dup
0x1b3fb  ldc.i4.2
0x1b3fc  ldstr    aExpiration// "expiration"
0x1b401  stelem.ref
0x1b402  dup
0x1b403  ldc.i4.3
0x1b404  ldarg.2
0x1b405  call     string Microsoft.Crm.CookieManager::EncodeCookie(string cookieValue)
0x1b40a  stelem.ref
0x1b40b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b410  stloc.0
0x1b411  ldarg.0
0x1b412  ldloc.0
0x1b413  call     string Microsoft.Crm.CookieManager::AppendSecureIfHttps(class [System]System.Uri targetUri, string cookieData)
0x1b418  stloc.0
0x1b419  ldarg.0
0x1b41a  callvirt instance string [mscorlib]System.Object::ToString()
0x1b41f  ldstr    aMscrmsession// "MSCRMSession"
0x1b424  ldloc.0
0x1b425  call     void Microsoft.Crm.CookieManager::SetCookie(string url, string name, string data)
0x1b42a  ret
```
