# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePageContent

- ea: `0x13810`
- end: `0x1391c`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePageContent`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x13390`
- `0x13760`

## callees

- `0x13530`
- `0x13810`
- `0x13920`

## string_xrefs

- `0x13866`: `/_imgs/error/notif_SecurityBadgeWarning32.png`

## pseudocode

```c

```

## disassembly

```asm
0x13810  ldarg.0
0x13811  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x13816  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorSeverity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Severity()
0x1381b  stloc.1
0x1381c  ldloc.1
0x1381d  switch   loc_13872, loc_1383C, loc_1384E, loc_13860, loc_13872, loc_13872
0x1383a  br.s     loc_13872
0x1383c  ldarg.0
0x1383d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ImageErrorIcon
0x13842  ldstr    aImgsErrorNotif_0// "/_imgs/error/notif_icn_info.png"
0x13847  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x1384c  br.s     loc_13882
0x1384e  ldarg.0
0x1384f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ImageErrorIcon
0x13854  ldstr    aImgsErrorNotif// "/_imgs/error/notif_icn_warn.png"
0x13859  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x1385e  br.s     loc_13882
0x13860  ldarg.0
0x13861  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ImageErrorIcon
0x13866  ldstr    aImgsErrorNotif_1// "/_imgs/error/notif_SecurityBadgeWarning"...
0x1386b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x13870  br.s     loc_13882
0x13872  ldarg.0
0x13873  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ImageErrorIcon
0x13878  ldstr    aImgsErrorNotif_2// "/_imgs/error/notif_icn_critical.png"
0x1387d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x13882  ldarg.0
0x13883  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ImageErrorIcon
0x13888  ldarg.0
0x13889  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1388e  ldstr    aErroriconalt// "ErrorIconAlt"
0x13893  ldarg.0
0x13894  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x13899  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorSeverity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Severity()
0x1389e  stloc.1
0x1389f  ldloca.s 1
0x138a1  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorSeverity
0x138a7  callvirt instance string [mscorlib]System.Object::ToString()
0x138ac  call     string [mscorlib]System.String::Concat(string, string)
0x138b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x138b6  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x138bb  ldarg.0
0x138bc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorTitle
0x138c1  ldarg.0
0x138c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x138c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Title()
0x138cc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x138d1  ldarg.0
0x138d2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x138d7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x138dc  ldstr    aParm0// "Parm0"
0x138e1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x138e6  stloc.0
0x138e7  ldarg.0
0x138e8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x138ed  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x138f2  ldc.i4   0x80040265
0x138f7  bne.un.s loc_13915
0x138f9  ldloc.0
0x138fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x138ff  brtrue.s loc_13915
0x13901  ldarg.0
0x13902  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorText
0x13907  ldloc.0
0x13908  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x1390d  ldarg.0
0x1390e  ldloc.0
0x1390f  stfld    string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_errorTextString
0x13914  ret
0x13915  ldarg.0
0x13916  callvirt instance void Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::SetErrorMessage()
0x1391b  ret
```
