# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigureHeader

- ea: `0x13630`
- end: `0x13757`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigureHeader`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x13530`
- `0x13570`
- `0x13590`
- `0x13630`
- `0x13fb0`

## string_xrefs

- `0x136a5`: `web._common.error.errorHandler.aspx_title`
- `0x1364e`: `/_common/styles/`
- `0x13655`: `/Help/Common/`
- `0x1374b`: `_removeRecordFromRecentlyViewed`

## pseudocode

```c

```

## disassembly

```asm
0x13630  ldarg.0
0x13631  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigureHeader()
0x13636  ldarg.0
0x13637  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1363c  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x13641  ldstr    aHelp// "/Help/"
0x13646  ldc.i4.5
0x13647  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1364c  brtrue.s loc_13655
0x1364e  ldstr    aCommonStyles// "/_common/styles/"
0x13653  br.s     loc_1365A
0x13655  ldstr    aHelpCommon// "/Help/Common/"
0x1365a  stloc.0
0x1365b  ldarg.0
0x1365c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x13661  ldloc.0
0x13662  ldstr    aFontsCssAspx// "fonts.css.aspx"
0x13667  call     string [mscorlib]System.String::Concat(string, string)
0x1366c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x13671  ldarg.0
0x13672  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x13677  ldloc.0
0x13678  ldstr    aGlobalCssAspx// "global.css.aspx"
0x1367d  call     string [mscorlib]System.String::Concat(string, string)
0x13682  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x13687  ldarg.0
0x13688  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x1368d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13692  ldstr    a01_0// "{0} : {1}"
0x13697  ldc.i4.2
0x13698  newarr   [mscorlib]System.Object
0x1369d  dup
0x1369e  ldc.i4.0
0x1369f  ldarg.0
0x136a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x136a5  ldstr    aWebCommonError_4// "web._common.error.errorHandler.aspx_tit"...
0x136aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x136af  stelem.ref
0x136b0  dup
0x136b1  ldc.i4.1
0x136b2  ldarg.0
0x136b3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorTitle
0x136b8  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerText()
0x136bd  stelem.ref
0x136be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x136c3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x136c8  ldarg.0
0x136c9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x136ce  ldstr    aRequesturl// "_requestUrl"
0x136d3  ldarg.0
0x136d4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri()
0x136d9  callvirt instance string [mscorlib]System.Object::ToString()
0x136de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x136e3  ldarg.0
0x136e4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x136e9  ldstr    aBackurl// "_backUrl"
0x136ee  ldarg.0
0x136ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri()
0x136f4  callvirt instance string [mscorlib]System.Object::ToString()
0x136f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x136fe  ldarg.0
0x136ff  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x13704  ldstr    aBclosemode// "_bCloseMode"
0x13709  ldarg.0
0x1370a  ldfld    bool Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_closeMode
0x1370f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x13714  ldarg.0
0x13715  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x1371a  ldstr    aBdeverrormode// "_bDevErrorMode"
0x1371f  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::get_ShowDevErrors()
0x13724  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x13729  ldarg.0
0x1372a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_ErrorData()
0x1372f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x13734  ldc.i4   0x80040217
0x13739  bne.un.s loc_13756
0x1373b  ldarg.0
0x1373c  call     instance string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::GetOriginalRecordId()
0x13741  stloc.1
0x13742  ldloc.1
0x13743  brfalse.s loc_13756
0x13745  ldarg.0
0x13746  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x1374b  ldstr    aRemoverecordfr// "_removeRecordFromRecentlyViewed"
0x13750  ldloc.1
0x13751  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x13756  ret
```
