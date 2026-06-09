# Microsoft.Crm.CookieManager::GetCookie

- ea: `0x1b0c0`
- end: `0x1b12c`
- name: `Microsoft.Crm.CookieManager::GetCookie`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x419a0`

## callees

- `0x1b0c0`
- `0x1b160`
- `0x1b5e0`

## string_xrefs

- `0x1b0c1`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b0c0  ldarg.0
0x1b0c1  ldstr    aTargeturi// "targetUri"
0x1b0c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b0cb  ldnull
0x1b0cc  stloc.0
0x1b0cd  ldarg.1
0x1b0ce  ldnull
0x1b0cf  stind.ref
0x1b0d0  ldarg.0
0x1b0d1  call     string Microsoft.Crm.CookieManager::GetCookie(class [System]System.Uri targetUri)
0x1b0d6  stloc.1
0x1b0d7  ldloc.1
0x1b0d8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b0dd  brtrue.s loc_1B12A
0x1b0df  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CookieManager::regex
0x1b0e4  ldloc.1
0x1b0e5  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x1b0ea  stloc.2
0x1b0eb  ldloc.2
0x1b0ec  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x1b0f1  brfalse.s loc_1B12A
0x1b0f3  ldloc.2
0x1b0f4  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x1b0f9  ldstr    aTicket// "ticket"
0x1b0fe  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1b103  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x1b108  call     string Microsoft.Crm.CookieManager::DecodeCookie(string cookieValue)
0x1b10d  stloc.0
0x1b10e  ldarg.1
0x1b10f  ldloc.2
0x1b110  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x1b115  ldstr    aExpiration// "expiration"
0x1b11a  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1b11f  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x1b124  call     string Microsoft.Crm.CookieManager::DecodeCookie(string cookieValue)
0x1b129  stind.ref
0x1b12a  ldloc.0
0x1b12b  ret
```
