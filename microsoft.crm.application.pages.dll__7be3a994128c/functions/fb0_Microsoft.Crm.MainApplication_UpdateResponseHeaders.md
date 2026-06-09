# Microsoft.Crm.MainApplication::UpdateResponseHeaders

- ea: `0xfb0`
- end: `0x11ee`
- name: `Microsoft.Crm.MainApplication::UpdateResponseHeaders`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0xf60`

## callees

- `0xfb0`

## string_xrefs

- `0x10b1`: `Access-Control-Request-Method`
- `0x10ed`: `DELETE`
- `0x1126`: `Access-Control-Allow-Origin`
- `0x1158`: `Access-Control-Allow-Methods`
- `0x1172`: `Access-Control-Expose-Headers`
- `0x118b`: `Access-Control-Max-Age`
- `0x11c2`: `Access-Control-Request-Headers`
- `0x11dc`: `Access-Control-Allow-Headers`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xfb5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xfba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0xfbf  ldstr    aOrigin// "Origin"
0xfc4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfc9  brfalse.s loc_FF0
0xfcb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xfd0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xfd5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0xfda  ldstr    aOrigin// "Origin"
0xfdf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfe4  ldstr    asc_113394// "*"
0xfe9  callvirt instance bool [mscorlib]System.String::Equals(string)
0xfee  brfalse.s loc_FF1
0xff0  ret
0xff1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xff6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xffb  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1000  callvirt instance string [System]System.Uri::get_OriginalString()
0x1005  newobj   instance void [System]System.Uri::.ctor(string)
0x100a  stloc.0
0x100b  ldloc.0
0x100c  callvirt instance string [System]System.Uri::get_Host()
0x1011  ldstr    asc_113398// ":"
0x1016  ldloc.0
0x1017  callvirt instance int32 [System]System.Uri::get_Port()
0x101c  box      [mscorlib]System.Int32
0x1021  call     string [mscorlib]System.String::Concat(object, object, object)
0x1026  stloc.1
0x1027  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x102c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1031  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x1036  ldstr    aOrigin// "Origin"
0x103b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1040  ldloc.1
0x1041  ldc.i4.1
0x1042  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1047  brfalse.s loc_104A
0x1049  ret
0x104a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x104f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1054  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x1059  ldstr    aHost// "Host"
0x105e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1063  stloc.2
0x1064  ldloc.2
0x1065  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x106a  brtrue.s loc_10A2
0x106c  ldloc.2
0x106d  ldc.i4.s 0x3A
0x106f  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1074  stloc.s  5
0x1076  ldloc.s  5
0x1078  ldc.i4.m1
0x1079  beq.s    loc_1085
0x107b  ldloc.2
0x107c  ldc.i4.0
0x107d  ldloc.s  5
0x107f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1084  stloc.2
0x1085  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x108a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x108f  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1094  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1099  ldloc.2
0x109a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x109f  brfalse.s loc_10A2
0x10a1  ret
0x10a2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x10a7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x10ac  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x10b1  ldstr    aAccessControlR// "Access-Control-Request-Method"
0x10b6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10bb  stloc.3
0x10bc  ldloc.3
0x10bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10c2  brfalse.s loc_10C5
0x10c4  ret
0x10c5  ldloc.3
0x10c6  ldstr    aGet// "GET"
0x10cb  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10d0  brtrue.s loc_1107
0x10d2  ldloc.3
0x10d3  ldstr    aPut// "PUT"
0x10d8  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10dd  brtrue.s loc_1107
0x10df  ldloc.3
0x10e0  ldstr    aPost// "POST"
0x10e5  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10ea  brtrue.s loc_1107
0x10ec  ldloc.3
0x10ed  ldstr    aDelete_0// "DELETE"
0x10f2  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10f7  brtrue.s loc_1107
0x10f9  ldloc.3
0x10fa  ldstr    aPatch// "PATCH"
0x10ff  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1104  brtrue.s loc_1107
0x1106  ret
0x1107  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x110c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1111  ldc.i4.1
0x1112  bne.un.s loc_111C
0x1114  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x1119  brtrue.s loc_111C
0x111b  ret
0x111c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1121  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1126  ldstr    aAccessControlA// "Access-Control-Allow-Origin"
0x112b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1130  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1135  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x113a  ldstr    aOrigin// "Origin"
0x113f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1144  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1149  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x114e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1153  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1158  ldstr    aAccessControlA_0// "Access-Control-Allow-Methods"
0x115d  ldloc.3
0x115e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1163  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x1168  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x116d  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1172  ldstr    aAccessControlE// "Access-Control-Expose-Headers"
0x1177  ldstr    aPreferenceAppl// "Preference-Applied,OData-EntityId,Locat"...
0x117c  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x1181  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1186  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x118b  ldstr    aAccessControlM// "Access-Control-Max-Age"
0x1190  ldstr    a3600// "3600"
0x1195  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x119a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x11a4  ldstr    aVary// "Vary"
0x11a9  ldstr    aOrigin// "Origin"
0x11ae  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x11b3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x11b8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x11bd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x11c2  ldstr    aAccessControlR_0// "Access-Control-Request-Headers"
0x11c7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11cc  stloc.s  4
0x11ce  ldloc.s  4
0x11d0  brfalse.s loc_11ED
0x11d2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x11d7  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x11dc  ldstr    aAccessControlA_1// "Access-Control-Allow-Headers"
0x11e1  ldloc.s  4
0x11e3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x11e8  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x11ed  ret
```
