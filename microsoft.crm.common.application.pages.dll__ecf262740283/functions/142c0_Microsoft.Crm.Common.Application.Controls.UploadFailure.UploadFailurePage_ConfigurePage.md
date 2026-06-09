# Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::ConfigurePage

- ea: `0x142c0`
- end: `0x143d6`
- name: `Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::ConfigurePage`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x142c0`
- `0x143f0`

## pseudocode

```c

```

## disassembly

```asm
0x142c0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x142c5  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x142ca  ldarg.0
0x142cb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x142d0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x142d5  call     class [mscorlib]System.Tuple`2<string, bool> [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Utility.UploadFailure::GetErrorMessage(class [mscorlib]System.Collections.IDictionary, class [System]System.Collections.Specialized.NameValueCollection)
0x142da  stloc.0
0x142db  ldarg.0
0x142dc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::tdMessage
0x142e1  ldloc.0
0x142e2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, bool>::get_Item1()
0x142e7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x142ec  ldarg.0
0x142ed  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::SerializedException
0x142f2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x142f7  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x142fc  call     string Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::GetSerializedException(class [mscorlib]System.Collections.IDictionary contextItems)
0x14301  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x14306  ldloc.0
0x14307  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, bool>::get_Item2()
0x1430c  brfalse.s loc_14370
0x1430e  ldarg.0
0x1430f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14314  ldstr    aObjecttype_0// "_objectType"
0x14319  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1431e  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x14323  ldstr    aAttachmenttype// "AttachmentType"
0x14328  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1432d  callvirt instance string [mscorlib]System.Object::ToString()
0x14332  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x14337  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1433c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x14341  ldstr    aRedirecturl// "RedirectURL"
0x14346  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1434b  brfalse  loc_143D5
0x14350  ldarg.0
0x14351  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14356  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1435b  ldstr    aRedirecturl// "RedirectURL"
0x14360  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x14365  callvirt instance string [mscorlib]System.Object::ToString()
0x1436a  stfld    string Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::redirectUrl
0x1436f  ret
0x14370  ldarg.0
0x14371  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14376  ldstr    aObjecttype_0// "_objectType"
0x1437b  ldarg.0
0x1437c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14381  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14386  ldstr    aAttachmenttype// "AttachmentType"
0x1438b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14390  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x14395  ldarg.0
0x14396  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1439b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x143a0  ldstr    aRedirecturl// "RedirectURL"
0x143a5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x143aa  ldc.i4.0
0x143ab  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::IsValidRedirectUrl(string, valuetype [System]System.UriKind)
0x143b0  brfalse.s loc_143CE
0x143b2  ldarg.0
0x143b3  ldarg.0
0x143b4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x143b9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x143be  ldstr    aRedirecturl// "RedirectURL"
0x143c3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x143c8  stfld    string Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::redirectUrl
0x143cd  ret
0x143ce  ldarg.0
0x143cf  ldnull
0x143d0  stfld    string Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::redirectUrl
0x143d5  ret
```
