# Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CanCacheSelectExpandNode

- ea: `0x2ae0`
- end: `0x2b0f`
- name: `Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CanCacheSelectExpandNode`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23e0`

## callees

- `0x2ae0`

## string_xrefs

- `0x2af1`: `odata.cacheselectexpandnode`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldc.i4.1
0x2ae1  stloc.0
0x2ae2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2ae7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2aec  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x2af1  ldstr    aOdataCachesele// "odata.cacheselectexpandnode"
0x2af6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2afb  stloc.1
0x2afc  ldloc.1
0x2afd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b02  brtrue.s loc_2B0D
0x2b04  ldloc.1
0x2b05  ldloca.s 0
0x2b07  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x2b0c  pop
0x2b0d  ldloc.0
0x2b0e  ret
```
