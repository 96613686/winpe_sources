# Microsoft.Crm.Authentication.CrmServiceRedirectAuthenticationProvider::GetWsdlRedirectUrl

- ea: `0x4800`
- end: `0x4847`
- name: `Microsoft.Crm.Authentication.CrmServiceRedirectAuthenticationProvider::GetWsdlRedirectUrl`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x47b0`

## callees

- `0x4800`

## string_xrefs

- `0x4827`: `CrmServiceWsdl.aspx?uniquename={0}`
- `0x4841`: `CrmServiceWsdl.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x4800  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4805  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x480a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x480f  ldstr    aUniquename// "uniquename"
0x4814  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4819  stloc.0
0x481a  ldloc.0
0x481b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4820  brtrue.s loc_4841
0x4822  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4827  ldstr    aCrmservicewsdl// "CrmServiceWsdl.aspx?uniquename={0}"
0x482c  ldc.i4.1
0x482d  newarr   [mscorlib]System.Object
0x4832  dup
0x4833  ldc.i4.0
0x4834  ldloc.0
0x4835  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x483a  stelem.ref
0x483b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4840  ret
0x4841  ldstr    aCrmservicewsdl_0// "CrmServiceWsdl.aspx"
0x4846  ret
```
