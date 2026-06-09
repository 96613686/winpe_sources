# Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::SetPageNumberAndPageCookie

- ea: `0x14e10`
- end: `0x14e6f`
- name: `Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::SetPageNumberAndPageCookie`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14a10`
- `0x14df0`

## callees

- `0x14e10`
- `0x1d530`
- `0x1d540`
- `0x202c0`
- `0x24e10`
- `0x28fe0`

## string_xrefs

- `0x14e1d`: `$skiptoken`
- `0x14e2a`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x14e10  ldarg.1
0x14e11  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x14e16  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x14e1b  stloc.0
0x14e1c  ldloc.0
0x14e1d  ldstr    aSkiptoken// "$skiptoken"
0x14e22  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x14e27  brfalse.s loc_14E62
0x14e29  ldloc.0
0x14e2a  ldstr    aSkiptoken// "$skiptoken"
0x14e2f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x14e34  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x14e39  stloc.1
0x14e3a  ldarg.0
0x14e3b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x14e40  ldloc.1
0x14e41  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_PageNumber()
0x14e46  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0x14e4b  ldarg.0
0x14e4c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x14e51  ldloc.1
0x14e52  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_PagingCookie()
0x14e57  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x14e5c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PagingCookie(string)
0x14e61  ret
0x14e62  ldarg.0
0x14e63  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x14e68  ldc.i4.1
0x14e69  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0x14e6e  ret
```
