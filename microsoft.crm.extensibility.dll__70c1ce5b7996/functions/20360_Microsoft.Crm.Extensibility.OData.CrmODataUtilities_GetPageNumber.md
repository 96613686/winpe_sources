# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber

- ea: `0x20360`
- end: `0x20393`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetPageNumber`
- size: `51`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1d660`
- `0x1d750`
- `0x1e010`
- `0x1eb40`
- `0x1f4d0`
- `0x209c0`
- `0x21100`

## callees

- `0x1d530`
- `0x202c0`
- `0x20360`
- `0x24e10`
- `0x28fe0`

## string_xrefs

- `0x2036f`: `$skiptoken`
- `0x2037c`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x20360  ldarg.0
0x20361  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x20366  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2036b  stloc.0
0x2036c  ldc.i4.1
0x2036d  stloc.1
0x2036e  ldloc.0
0x2036f  ldstr    aSkiptoken// "$skiptoken"
0x20374  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20379  brfalse.s loc_20391
0x2037b  ldloc.0
0x2037c  ldstr    aSkiptoken// "$skiptoken"
0x20381  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20386  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x2038b  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_PageNumber()
0x20390  stloc.1
0x20391  ldloc.1
0x20392  ret
```
