# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPagingInfoForChangeTracking

- ea: `0x21200`
- end: `0x21265`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPagingInfoForChangeTracking`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1d660`
- `0x1e330`

## callees

- `0x1d530`
- `0x1d540`
- `0x202c0`
- `0x209c0`
- `0x21200`
- `0x24e10`
- `0x28fe0`

## string_xrefs

- `0x21220`: `$skiptoken`
- `0x2122d`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x21200  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::.ctor()
0x21205  stloc.0
0x21206  ldloc.0
0x21207  ldc.i4.0
0x21208  ldarg.0
0x21209  call     int32 Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageSize(int32 topOption, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x2120e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32)
0x21213  ldarg.0
0x21214  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x21219  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2121e  stloc.1
0x2121f  ldloc.1
0x21220  ldstr    aSkiptoken// "$skiptoken"
0x21225  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2122a  brfalse.s loc_2125C
0x2122c  ldloc.1
0x2122d  ldstr    aSkiptoken// "$skiptoken"
0x21232  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x21237  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x2123c  stloc.2
0x2123d  ldloc.0
0x2123e  ldloc.2
0x2123f  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_PageNumber()
0x21244  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PageNumber(int32)
0x21249  ldloc.0
0x2124a  ldloc.2
0x2124b  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_PagingCookie()
0x21250  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x21255  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PagingCookie(string)
0x2125a  br.s     loc_21263
0x2125c  ldloc.0
0x2125d  ldc.i4.1
0x2125e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PageNumber(int32)
0x21263  ldloc.0
0x21264  ret
```
