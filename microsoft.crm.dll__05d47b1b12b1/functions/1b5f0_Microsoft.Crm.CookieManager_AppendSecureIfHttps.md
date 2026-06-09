# Microsoft.Crm.CookieManager::AppendSecureIfHttps

- ea: `0x1b5f0`
- end: `0x1b636`
- name: `Microsoft.Crm.CookieManager::AppendSecureIfHttps`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b390`
- `0x1b430`

## callees

- `0x1b5f0`

## string_xrefs

- `0x1b5f1`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b5f0  ldarg.0
0x1b5f1  ldstr    aTargeturi// "targetUri"
0x1b5f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b5fb  ldarg.1
0x1b5fc  ldstr    aCookiedata// "cookieData"
0x1b601  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b606  ldarg.0
0x1b607  callvirt instance string [System]System.Uri::get_Scheme()
0x1b60c  ldstr    aHttps// "https"
0x1b611  ldc.i4.5
0x1b612  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b617  brtrue.s loc_1B634
0x1b619  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b61e  ldstr    a0Secure// "{0}; secure"
0x1b623  ldc.i4.1
0x1b624  newarr   [mscorlib]System.Object
0x1b629  dup
0x1b62a  ldc.i4.0
0x1b62b  ldarg.1
0x1b62c  stelem.ref
0x1b62d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b632  starg.s  1
0x1b634  ldarg.1
0x1b635  ret
```
