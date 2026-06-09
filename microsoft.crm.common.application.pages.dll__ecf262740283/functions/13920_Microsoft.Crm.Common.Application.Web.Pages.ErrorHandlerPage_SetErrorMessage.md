# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::SetErrorMessage

- ea: `0x13920`
- end: `0x13af2`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::SetErrorMessage`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x13810`

## callees

- `0x13530`
- `0x13920`
- `0x13b00`

## pseudocode

```c

```

## disassembly

```asm
0x13920  ldarg.0
0x13921  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorText
0x13926  ldarg.0
0x13927  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x1392c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_MessageHtml()
0x13931  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x13936  ldarg.0
0x13937  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x1393c  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x13941  stloc.0
0x13942  ldloca.s 0
0x13944  ldstr    aX// "x"
0x13949  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1394e  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x13953  ldstr    a80050016// "80050016"
0x13958  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1395d  brfalse  loc_13A1B
0x13962  ldarg.0
0x13963  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x13968  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Title()
0x1396d  stloc.1
0x1396e  ldc.i4.6
0x1396f  newarr   [mscorlib]System.String
0x13974  dup
0x13975  ldc.i4.0
0x13976  ldarg.0
0x13977  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1397c  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x13981  callvirt instance string [System]System.Uri::get_Scheme()
0x13986  stelem.ref
0x13987  dup
0x13988  ldc.i4.1
0x13989  ldstr    asc_2FD6A// "://"
0x1398e  stelem.ref
0x1398f  dup
0x13990  ldc.i4.2
0x13991  ldarg.0
0x13992  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13997  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1399c  callvirt instance string [System]System.Uri::get_Host()
0x139a1  stelem.ref
0x139a2  dup
0x139a3  ldc.i4.3
0x139a4  ldarg.0
0x139a5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139aa  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x139af  callvirt instance string[] [System]System.Uri::get_Segments()
0x139b4  ldc.i4.0
0x139b5  ldelem.ref
0x139b6  stelem.ref
0x139b7  dup
0x139b8  ldc.i4.4
0x139b9  ldarg.0
0x139ba  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139bf  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x139c4  callvirt instance string[] [System]System.Uri::get_Segments()
0x139c9  ldc.i4.1
0x139ca  ldelem.ref
0x139cb  stelem.ref
0x139cc  dup
0x139cd  ldc.i4.5
0x139ce  ldstr    aToolsSolutionH// "tools/Solution/home_solution.aspx?etc=7"...
0x139d3  stelem.ref
0x139d4  call     string [mscorlib]System.String::Concat(string[])
0x139d9  stloc.2
0x139da  ldarg.0
0x139db  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorText
0x139e0  stloc.3
0x139e1  ldloc.3
0x139e2  ldc.i4.6
0x139e3  newarr   [mscorlib]System.String
0x139e8  dup
0x139e9  ldc.i4.0
0x139ea  ldloc.3
0x139eb  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x139f0  stelem.ref
0x139f1  dup
0x139f2  ldc.i4.1
0x139f3  ldstr    aAStyleTextDeco// "<a style='text-decoration: underline;' "...
0x139f8  stelem.ref
0x139f9  dup
0x139fa  ldc.i4.2
0x139fb  ldloc.2
0x139fc  stelem.ref
0x139fd  dup
0x139fe  ldc.i4.3
0x139ff  ldstr    asc_2FE22// ">"
0x13a04  stelem.ref
0x13a05  dup
0x13a06  ldc.i4.4
0x13a07  ldloc.1
0x13a08  stelem.ref
0x13a09  dup
0x13a0a  ldc.i4.5
0x13a0b  ldstr    aA_0// " </a>"
0x13a10  stelem.ref
0x13a11  call     string [mscorlib]System.String::Concat(string[])
0x13a16  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x13a1b  ldarg.0
0x13a1c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x13a21  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x13a26  stloc.0
0x13a27  ldloca.s 0
0x13a29  ldstr    aX// "x"
0x13a2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a33  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x13a38  call     bool Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::DoesErrorContainPlaceholder(string errorCode)
0x13a3d  brfalse  loc_13AF1
0x13a42  ldarg.0
0x13a43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13a48  ldarg.0
0x13a49  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x13a4e  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x13a53  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessageWithoutEncoding(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a5d  stloc.s  4
0x13a5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a64  ldloc.s  4
0x13a66  ldc.i4.3
0x13a67  newarr   [mscorlib]System.Object
0x13a6c  dup
0x13a6d  ldc.i4.0
0x13a6e  ldarg.0
0x13a6f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13a74  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13a79  ldstr    aParm0// "Parm0"
0x13a7e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13a83  stelem.ref
0x13a84  dup
0x13a85  ldc.i4.1
0x13a86  ldarg.0
0x13a87  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13a8c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13a91  ldstr    aParm1// "Parm1"
0x13a96  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13a9b  stelem.ref
0x13a9c  dup
0x13a9d  ldc.i4.2
0x13a9e  ldarg.0
0x13a9f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13aa4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13aa9  ldstr    aParm2// "Parm2"
0x13aae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13ab3  stelem.ref
0x13ab4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13ab9  stloc.s  4
0x13abb  ldloc.s  4
0x13abd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x13ac2  stloc.s  4
0x13ac4  ldloc.s  4
0x13ac6  ldstr    asc_2FE4A// "\r\n"
0x13acb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x13ad0  ldstr    aBr// "<br/>"
0x13ad5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x13ada  stloc.s  4
0x13adc  ldarg.0
0x13add  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorText
0x13ae2  ldloc.s  4
0x13ae4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x13ae9  ldarg.0
0x13aea  ldloc.s  4
0x13aec  stfld    string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_errorTextString
0x13af1  ret
```
