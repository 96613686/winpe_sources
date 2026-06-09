# Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::ConfigurePage

- ea: `0x13390`
- end: `0x134c5`
- name: `Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::ConfigurePage`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x13390`
- `0x13570`
- `0x13590`
- `0x13810`

## string_xrefs

- `0x133cf`: `Mobile Error page loaded: OriginalRequestUri={0}`

## pseudocode

```c

```

## disassembly

```asm
0x13390  ldarg.0
0x13391  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::LogoArea
0x13396  ldnull
0x13397  cgt.un
0x13399  ldstr    aLogoAreaDivNot// "Logo area div not found on aspx page."
0x1339e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x133a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x133a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x133ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x133b2  stloc.0
0x133b3  ldarg.0
0x133b4  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::LogoArea
0x133b9  ldloc.0
0x133ba  ldarg.0
0x133bb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x133c0  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.MobileUtility::AddHeaderMenuToLandingPage(class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager)
0x133c5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x133ca  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x133cf  ldstr    aMobileErrorPag// "Mobile Error page loaded: OriginalReque"...
0x133d4  ldc.i4.1
0x133d5  newarr   [mscorlib]System.Object
0x133da  dup
0x133db  ldc.i4.0
0x133dc  ldarg.0
0x133dd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri()
0x133e2  stelem.ref
0x133e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x133e8  ldarg.0
0x133e9  call     instance void Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePageContent()
0x133ee  ldarg.0
0x133ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri()
0x133f4  brfalse.s loc_13403
0x133f6  ldarg.0
0x133f7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri()
0x133fc  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x13401  brfalse.s loc_13411
0x13403  ldarg.0
0x13404  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::GoBack
0x13409  ldc.i4.0
0x1340a  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1340f  br.s     loc_13466
0x13411  ldarg.0
0x13412  ldarg.0
0x13413  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri()
0x13418  callvirt instance string [mscorlib]System.Object::ToString()
0x1341d  stfld    string Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::goBackLink
0x13422  ldarg.0
0x13423  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::GoBack
0x13428  ldc.i4.1
0x13429  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1342e  ldarg.0
0x1342f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::GoBack
0x13434  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13439  ldstr    aInputTypeSubmi// "<input type=\"submit\" class=\"button e"...
0x1343e  ldc.i4.1
0x1343f  newarr   [mscorlib]System.Object
0x13444  dup
0x13445  ldc.i4.0
0x13446  ldarg.0
0x13447  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1344c  ldstr    aMcButtonBack// "MC_Button_Back"
0x13451  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13456  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1345b  stelem.ref
0x1345c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13461  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x13466  ldarg.0
0x13467  ldstr    aMDefaultAspx// "/m/default.aspx"
0x1346c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13471  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13476  callvirt instance string [mscorlib]System.Object::ToString()
0x1347b  stfld    string Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::goHomeLink
0x13480  ldarg.0
0x13481  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::GoHome
0x13486  ldc.i4.1
0x13487  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1348c  ldarg.0
0x1348d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::GoHome
0x13492  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13497  ldstr    aInputTypeSubmi_0// "<input type=\"submit\" class=\"button e"...
0x1349c  ldc.i4.1
0x1349d  newarr   [mscorlib]System.Object
0x134a2  dup
0x134a3  ldc.i4.0
0x134a4  ldarg.0
0x134a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x134aa  ldstr    aMenuLabelHome// "Menu_Label_Home"
0x134af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x134b4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x134b9  stelem.ref
0x134ba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x134bf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x134c4  ret
```
