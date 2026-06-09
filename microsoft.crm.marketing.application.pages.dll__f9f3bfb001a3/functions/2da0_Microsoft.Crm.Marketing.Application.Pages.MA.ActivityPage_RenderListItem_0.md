# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::RenderListItem_0

- ea: `0x2da0`
- end: `0x2f1e`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::RenderListItem_0`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2d80`
- `0x2f20`

## callees

- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0x2da0  ldarg.2
0x2da1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2da6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dab  brfalse  loc_2F1D
0x2db0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2db5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2dba  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2dbf  ldstr    aRenderingQcIte// "Rendering QC item for OTC = {0}"
0x2dc4  ldc.i4.1
0x2dc5  newarr   [mscorlib]System.Object
0x2dca  dup
0x2dcb  ldc.i4.0
0x2dcc  ldarg.1
0x2dcd  box      [mscorlib]System.Int32
0x2dd2  stelem.ref
0x2dd3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2dd8  ldarga.s 1
0x2dda  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ddf  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2de4  stloc.0
0x2de5  ldarg.0
0x2de6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2deb  ldstr    aLiClassMsCrmDi// "<li class=\"ms-crm-Dialog-ListItem\" on"...
0x2df0  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2df5  ldarg.0
0x2df6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2dfb  ldloc.0
0x2dfc  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e01  ldarg.0
0x2e02  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e07  ldstr    aId_1// "\" id=\""
0x2e0c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e11  ldarg.0
0x2e12  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e17  ldarg.3
0x2e18  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e1d  ldarg.0
0x2e1e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e23  ldloc.0
0x2e24  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e29  ldarg.0
0x2e2a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e2f  ldstr    aInputTypeRadio// "\"><input type=\"radio\" style=\"visibi"...
0x2e34  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e39  ldarg.0
0x2e3a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e3f  ldarg.3
0x2e40  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e45  ldarg.0
0x2e46  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e4b  ldloc.0
0x2e4c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e51  ldarg.s  5
0x2e53  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e58  brtrue.s loc_2E8C
0x2e5a  ldarg.0
0x2e5b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e60  ldstr    asc_7D62// "\""
0x2e65  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e6a  ldarg.0
0x2e6b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e70  ldstr    aName_0// " name=\""
0x2e75  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e7a  ldarg.0
0x2e7b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e80  ldarg.s  5
0x2e82  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2e87  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e8c  ldarg.0
0x2e8d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2e92  ldstr    asc_7D76// "\"/>"
0x2e97  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2e9c  ldarg.0
0x2e9d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ea2  ldstr    aImgAltAlignAbs// "<img alt=\"\" align=\"absmiddle\" CLASS"...
0x2ea7  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2eac  ldarg.0
0x2ead  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2eb2  ldloc.0
0x2eb3  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2eb8  ldarg.0
0x2eb9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ebe  ldstr    aGif// ".gif\">"
0x2ec3  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2ec8  ldarg.0
0x2ec9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ece  ldstr    aLabelForType// "<label for=\"type_"
0x2ed3  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2ed8  ldarg.0
0x2ed9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ede  ldarg.3
0x2edf  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2ee4  ldarg.0
0x2ee5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2eea  ldloc.0
0x2eeb  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2ef0  ldarg.0
0x2ef1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ef6  ldstr    asc_7E6C// "\">"
0x2efb  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2f00  ldarg.0
0x2f01  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f06  ldarg.s  4
0x2f08  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2f0d  ldarg.0
0x2f0e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2f13  ldstr    aLabelLi// "</label></li>"
0x2f18  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2f1d  ret
```
