# Microsoft.Crm.CookieManager::DeleteCookie

- ea: `0x1b530`
- end: `0x1b58b`
- name: `Microsoft.Crm.CookieManager::DeleteCookie`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1b531`: `targetUri`
- `0x1b541`: `Deleting cookie. Uri:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x1b530  ldarg.0
0x1b531  ldstr    aTargeturi// "targetUri"
0x1b536  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b53b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b540  ldc.i4.1
0x1b541  ldstr    aDeletingCookie// "Deleting cookie. Uri:{0}"
0x1b546  ldc.i4.1
0x1b547  newarr   [mscorlib]System.Object
0x1b54c  dup
0x1b54d  ldc.i4.0
0x1b54e  ldarg.0
0x1b54f  callvirt instance string [mscorlib]System.Object::ToString()
0x1b554  stelem.ref
0x1b555  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b55a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b55f  ldstr    a0ExpiresTue01J// "{0}; expires = Tue,01-Jan-1980 00:00:00"...
0x1b564  ldc.i4.1
0x1b565  newarr   [mscorlib]System.Object
0x1b56a  dup
0x1b56b  ldc.i4.0
0x1b56c  ldsfld   string [mscorlib]System.String::Empty
0x1b571  stelem.ref
0x1b572  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b577  stloc.0
0x1b578  ldarg.0
0x1b579  callvirt instance string [mscorlib]System.Object::ToString()
0x1b57e  ldstr    aMscrmsession// "MSCRMSession"
0x1b583  ldloc.0
0x1b584  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetSetCookie(string, string, string)
0x1b589  pop
0x1b58a  ret
```
