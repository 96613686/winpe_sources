# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleError

- ea: `0x8690`
- end: `0x8748`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleError`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8630`

## callees

- `0x8690`

## string_xrefs

- `0x86df`: `YamTokenRefreshing`
- `0x8727`: `An unknown error occured during Yammer sign up`

## pseudocode

```c

```

## disassembly

```asm
0x8690  ldarg.0
0x8691  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8696  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x869b  ldstr    aError// "error"
0x86a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86a5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x86aa  brtrue.s loc_86BD
0x86ac  ldc.i4   0x8005F105
0x86b1  ldc.i4.0
0x86b2  newarr   [mscorlib]System.Object
0x86b7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x86bc  throw
0x86bd  ldarg.0
0x86be  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x86c3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x86c8  ldstr    aTimedout// "timedout"
0x86cd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86d2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x86d7  brtrue.s loc_871B
0x86d9  ldarg.0
0x86da  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x86df  ldstr    aYamtokenrefres// "YamTokenRefreshing"
0x86e4  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string)
0x86e9  dup
0x86ea  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0x86ef  stloc.0
0x86f0  ldloca.s 0
0x86f2  ldc.r8   -1.0
0x86fb  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x8700  callvirt instance void [System.Web]System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime)
0x8705  callvirt instance void [System.Web]System.Web.HttpResponse::SetCookie(class [System.Web]System.Web.HttpCookie)
0x870a  ldc.i4   0x8005F107
0x870f  ldc.i4.0
0x8710  newarr   [mscorlib]System.Object
0x8715  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x871a  throw
0x871b  ldnull
0x871c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8721  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8726  ldc.i4.0
0x8727  ldstr    aAnUnknownError// "An unknown error occured during Yammer "...
0x872c  ldc.i4.0
0x872d  newarr   [mscorlib]System.Object
0x8732  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8737  ldc.i4   0x8005F105
0x873c  ldc.i4.0
0x873d  newarr   [mscorlib]System.Object
0x8742  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8747  throw
```
