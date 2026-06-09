# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::RedirectToOAuthLoginPage

- ea: `0x87d0`
- end: `0x88e6`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::RedirectToOAuthLoginPage`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8630`

## callees

- `0x8610`
- `0x87d0`

## string_xrefs

- `0x87d6`: `YamTokenRefreshing`
- `0x882f`: `CRMWRPCToken=`
- `0x883f`: `CRMWRPCToken`
- `0x8861`: `CRMWRPCTokenTimeStamp=`
- `0x8871`: `CRMWRPCTokenTimeStamp`
- `0x88a6`: `https://www.yammer.com/dialog/oauth?client_id={0}&redirect_uri={1}`

## pseudocode

```c

```

## disassembly

```asm
0x87d0  ldarg.0
0x87d1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x87d6  ldstr    aYamtokenrefres// "YamTokenRefreshing"
0x87db  ldstr    aRefreshing// "Refreshing"
0x87e0  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string, string)
0x87e5  dup
0x87e6  ldc.i4.1
0x87e7  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0x87ec  dup
0x87ed  ldc.i4.1
0x87ee  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0x87f3  callvirt instance void [System.Web]System.Web.HttpResponse::SetCookie(class [System.Web]System.Web.HttpCookie)
0x87f8  ldarg.0
0x87f9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x87fe  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x8803  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x8808  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x880d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8812  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8817  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAbsoluteUrl(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x881c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x8821  stloc.0
0x8822  ldloc.0
0x8823  ldstr    asc_25DAA// "?"
0x8828  call     string [mscorlib]System.String::Concat(string, string)
0x882d  stloc.0
0x882e  ldloc.0
0x882f  ldstr    aCrmwrpctoken// "CRMWRPCToken="
0x8834  ldarg.0
0x8835  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x883a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x883f  ldstr    aCrmwrpctoken_0// "CRMWRPCToken"
0x8844  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8849  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x884e  call     string [mscorlib]System.String::Concat(string, string, string)
0x8853  stloc.0
0x8854  ldloc.0
0x8855  ldstr    asc_25DE4// "&"
0x885a  call     string [mscorlib]System.String::Concat(string, string)
0x885f  stloc.0
0x8860  ldloc.0
0x8861  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp="
0x8866  ldarg.0
0x8867  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x886c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8871  ldstr    aCrmwrpctokenti_0// "CRMWRPCTokenTimeStamp"
0x8876  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x887b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x8880  call     string [mscorlib]System.String::Concat(string, string, string)
0x8885  stloc.0
0x8886  ldloc.0
0x8887  ldarg.0
0x8888  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_IsAdminFlow()
0x888d  brtrue.s loc_8896
0x888f  ldstr    aUser1// "&user=1"
0x8894  br.s     loc_889B
0x8896  ldsfld   string [mscorlib]System.String::Empty
0x889b  call     string [mscorlib]System.String::Concat(string, string)
0x88a0  stloc.0
0x88a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x88a6  ldstr    aHttpsWwwYammer_0// "https://www.yammer.com/dialog/oauth?cli"...
0x88ab  ldc.i4.2
0x88ac  newarr   [mscorlib]System.Object
0x88b1  dup
0x88b2  ldc.i4.0
0x88b3  ldarg.0
0x88b4  ldfld    string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::applicationId
0x88b9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x88be  stelem.ref
0x88bf  dup
0x88c0  ldc.i4.1
0x88c1  ldloc.0
0x88c2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x88c7  stelem.ref
0x88c8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x88cd  stloc.1
0x88ce  ldarg.0
0x88cf  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x88d4  ldloc.1
0x88d5  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x88da  ldarg.0
0x88db  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x88e0  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x88e5  ret
```
