# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::RenderListItem_0

- ea: `0x29e0`
- end: `0x2b5e`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::RenderListItem_0`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x29c0`
- `0x2b60`

## callees

- `0x29e0`

## pseudocode

```c

```

## disassembly

```asm
0x29e0  ldarg.2
0x29e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29e6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29eb  brfalse  loc_2B5D
0x29f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x29fa  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x29ff  ldstr    aRenderingQcIte// "Rendering QC item for OTC = {0}"
0x2a04  ldc.i4.1
0x2a05  newarr   [mscorlib]System.Object
0x2a0a  dup
0x2a0b  ldc.i4.0
0x2a0c  ldarg.1
0x2a0d  box      [mscorlib]System.Int32
0x2a12  stelem.ref
0x2a13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a18  ldarga.s 1
0x2a1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a1f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2a24  stloc.0
0x2a25  ldarg.0
0x2a26  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a2b  ldstr    aLiClassMsCrmDi// "<li class=\"ms-crm-Dialog-ListItem\" on"...
0x2a30  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a35  ldarg.0
0x2a36  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a3b  ldloc.0
0x2a3c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a41  ldarg.0
0x2a42  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a47  ldstr    aId_1// "\" id=\""
0x2a4c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a51  ldarg.0
0x2a52  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a57  ldarg.3
0x2a58  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a5d  ldarg.0
0x2a5e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a63  ldloc.0
0x2a64  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a69  ldarg.0
0x2a6a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a6f  ldstr    aInputTypeRadio// "\"><input type=\"radio\" style=\"visibi"...
0x2a74  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a79  ldarg.0
0x2a7a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a7f  ldarg.3
0x2a80  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a85  ldarg.0
0x2a86  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a8b  ldloc.0
0x2a8c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2a91  ldarg.s  5
0x2a93  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a98  brtrue.s loc_2ACC
0x2a9a  ldarg.0
0x2a9b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2aa0  ldstr    asc_7D62// "\""
0x2aa5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2aaa  ldarg.0
0x2aab  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ab0  ldstr    aName_0// " name=\""
0x2ab5  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2aba  ldarg.0
0x2abb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ac0  ldarg.s  5
0x2ac2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2ac7  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2acc  ldarg.0
0x2acd  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ad2  ldstr    asc_7D76// "\"/>"
0x2ad7  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2adc  ldarg.0
0x2add  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2ae2  ldstr    aImgAltAlignAbs// "<img alt=\"\" align=\"absmiddle\" CLASS"...
0x2ae7  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2aec  ldarg.0
0x2aed  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2af2  ldloc.0
0x2af3  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2af8  ldarg.0
0x2af9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2afe  ldstr    aGif// ".gif\">"
0x2b03  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b08  ldarg.0
0x2b09  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b0e  ldstr    aLabelForType// "<label for=\"type_"
0x2b13  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b18  ldarg.0
0x2b19  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b1e  ldarg.3
0x2b1f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b24  ldarg.0
0x2b25  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b2a  ldloc.0
0x2b2b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b30  ldarg.0
0x2b31  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b36  ldstr    asc_7E6C// "\">"
0x2b3b  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b40  ldarg.0
0x2b41  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b46  ldarg.s  4
0x2b48  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b4d  ldarg.0
0x2b4e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2b53  ldstr    aLabelLi// "</label></li>"
0x2b58  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2b5d  ret
```
