# Microsoft.Crm.Application.Platform.SolutionMarketplaceUtility::RetrieveForwardLinkTarget

- ea: `0x70d60`
- end: `0x70e09`
- name: `Microsoft.Crm.Application.Platform.SolutionMarketplaceUtility::RetrieveForwardLinkTarget`
- size: `169`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x70af0`
- `0x70b30`
- `0x70b70`
- `0x70bb0`
- `0x70c00`
- `0x70ca0`

## callees

- `0x70d60`
- `0x70e10`

## string_xrefs

- `0x70d65`: `http://go.microsoft.com/fwlink/?LinkId={0}`
- `0x70dc6`: `http://pinpoint.microsoft.com`
- `0x70dea`: `Unable to Resolve Forward link Target for {0}`

## pseudocode

```c

```

## disassembly

```asm
0x70d60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70d65  ldstr    aHttpGoMicrosof_3// "http://go.microsoft.com/fwlink/?LinkId="...
0x70d6a  ldc.i4.1
0x70d6b  newarr   [mscorlib]System.Object
0x70d70  dup
0x70d71  ldc.i4.0
0x70d72  ldarg.0
0x70d73  box      [mscorlib]System.Int32
0x70d78  stelem.ref
0x70d79  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70d7e  newobj   instance void [System]System.Uri::.ctor(string)
0x70d83  stloc.0
0x70d84  ldloc.0
0x70d85  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x70d8a  castclass [System]System.Net.HttpWebRequest
0x70d8f  stloc.1
0x70d90  call     class [System]System.Net.WebProxy Microsoft.Crm.Application.Platform.SolutionMarketplaceUtility::RetrieveInternetProxy()
0x70d95  stloc.2
0x70d96  ldloc.2
0x70d97  brfalse.s loc_70DA7
0x70d99  ldloc.1
0x70d9a  ldloc.2
0x70d9b  callvirt instance void [System]System.Net.WebRequest::set_Proxy(class [System]System.Net.IWebProxy)
0x70da0  ldloc.1
0x70da1  ldc.i4.0
0x70da2  callvirt instance void [System]System.Net.WebRequest::set_UseDefaultCredentials(bool)
0x70da7  nop
0x70da8  ldloc.1
0x70da9  ldc.i4.0
0x70daa  callvirt instance void [System]System.Net.HttpWebRequest::set_AllowAutoRedirect(bool)
0x70daf  ldloc.1
0x70db0  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x70db5  stloc.3
0x70db6  ldloc.3
0x70db7  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebResponse::get_Headers()
0x70dbc  ldstr    aLocation// "Location"
0x70dc1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x70dc6  ldstr    aHttpPinpointMi// "http://pinpoint.microsoft.com"
0x70dcb  ldstr    asc_A9652// ""
0x70dd0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x70dd5  stloc.s  4
0x70dd7  leave.s  loc_70E06
0x70dd9  ldloc.3
0x70dda  brfalse.s loc_70DE2
0x70ddc  ldloc.3
0x70ddd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70de2  endfinally
0x70de3  stloc.s  5
0x70de5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70dea  ldstr    aUnableToResolv_0// "Unable to Resolve Forward link Target f"...
0x70def  ldc.i4.1
0x70df0  newarr   [mscorlib]System.Object
0x70df5  dup
0x70df6  ldc.i4.0
0x70df7  ldloc.0
0x70df8  stelem.ref
0x70df9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70dfe  ldloc.s  5
0x70e00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x70e05  throw
0x70e06  ldloc.s  4
0x70e08  ret
```
