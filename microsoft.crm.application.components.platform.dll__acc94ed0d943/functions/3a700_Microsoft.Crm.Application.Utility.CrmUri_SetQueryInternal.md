# Microsoft.Crm.Application.Utility.CrmUri::SetQueryInternal

- ea: `0x3a700`
- end: `0x3a790`
- name: `Microsoft.Crm.Application.Utility.CrmUri::SetQueryInternal`
- size: `144`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x39c00`
- `0x39c60`
- `0x39d10`
- `0x3a020`
- `0x3a160`
- `0x3a210`

## callees

- `0x39e00`
- `0x3a700`
- `0x47920`

## string_xrefs

- `0x3a720`: `CrmUri: QueryString parameter name must never be blank.`
- `0x3a72c`: `CrmUri: QueryString parameter name must never be blank.`

## pseudocode

```c

```

## disassembly

```asm
0x3a700  ldarg.1
0x3a701  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3a706  brfalse.s loc_3A736
0x3a708  ldnull
0x3a709  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3a70e  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x3a713  ldstr    a0// "{0}"
0x3a718  ldc.i4.1
0x3a719  newarr   [mscorlib]System.Object
0x3a71e  dup
0x3a71f  ldc.i4.0
0x3a720  ldstr    aCrmuriQuerystr// "CrmUri: QueryString parameter name must"...
0x3a725  stelem.ref
0x3a726  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3a72b  ldc.i4.0
0x3a72c  ldstr    aCrmuriQuerystr// "CrmUri: QueryString parameter name must"...
0x3a731  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3a736  ldarg.2
0x3a737  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a73c  brfalse.s loc_3A745
0x3a73e  ldsfld   string [mscorlib]System.String::Empty
0x3a743  starg.s  2
0x3a745  ldarg.0
0x3a746  ldfld    class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::queryDictionary
0x3a74b  brtrue.s loc_3A782
0x3a74d  ldarg.0
0x3a74e  ldfld    class [System]System.UriBuilder Microsoft.Crm.Application.Utility.CrmUri::uriBuilder
0x3a753  callvirt instance string [System]System.UriBuilder::get_Query()
0x3a758  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3a75d  ldc.i4.1
0x3a75e  bgt.s    loc_3A782
0x3a760  ldarg.0
0x3a761  ldfld    class [System]System.UriBuilder Microsoft.Crm.Application.Utility.CrmUri::uriBuilder
0x3a766  ldarg.1
0x3a767  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x3a76c  ldstr    asc_C4E70// "="
0x3a771  ldarg.2
0x3a772  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x3a777  call     string [mscorlib]System.String::Concat(string, string, string)
0x3a77c  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x3a781  ret
0x3a782  ldarg.0
0x3a783  call     instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3a788  ldarg.1
0x3a789  ldarg.2
0x3a78a  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3a78f  ret
```
