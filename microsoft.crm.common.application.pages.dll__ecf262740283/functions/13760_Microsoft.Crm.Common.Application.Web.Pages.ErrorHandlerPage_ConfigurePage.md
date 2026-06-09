# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePage

- ea: `0x13760`
- end: `0x13803`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePage`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x13570`
- `0x13590`
- `0x13760`
- `0x13810`

## string_xrefs

- `0x13770`: `Error page loaded: OriginalRequestUri={0}, BackUri={1}`

## pseudocode

```c

```

## disassembly

```asm
0x13760  ldarg.0
0x13761  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigurePage()
0x13766  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x1376b  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x13770  ldstr    aErrorPageLoade// "Error page loaded: OriginalRequestUri={"...
0x13775  ldc.i4.2
0x13776  newarr   [mscorlib]System.Object
0x1377b  dup
0x1377c  ldc.i4.0
0x1377d  ldarg.0
0x1377e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri()
0x13783  stelem.ref
0x13784  dup
0x13785  ldc.i4.1
0x13786  ldarg.0
0x13787  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri()
0x1378c  stelem.ref
0x1378d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13792  ldarg.0
0x13793  call     instance void Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ConfigurePageContent()
0x13798  ldarg.0
0x13799  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri()
0x1379e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x137a3  brfalse.s loc_137B1
0x137a5  ldarg.0
0x137a6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ButtonTryAgain
0x137ab  ldc.i4.0
0x137ac  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x137b1  leave.s  loc_137C2
0x137b3  stloc.0
0x137b4  ldarg.0
0x137b5  ldloc.0
0x137b6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x137bb  stfld    string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_extraInfo
0x137c0  leave.s  loc_137C2
0x137c2  ldarg.0
0x137c3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::TableRowInfo
0x137c8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookFatClient()
0x137cd  brfalse.s loc_137E6
0x137cf  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x137d4  brfalse.s loc_137E6
0x137d6  ldarg.0
0x137d7  ldfld    string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_extraInfo
0x137dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x137e1  ldc.i4.0
0x137e2  ceq
0x137e4  br.s     loc_137E7
0x137e6  ldc.i4.0
0x137e7  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x137ec  ldarg.0
0x137ed  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x137f2  ldstr    aErrortextstrin// "_errorTextString"
0x137f7  ldarg.0
0x137f8  ldfld    string Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_errorTextString
0x137fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x13802  ret
```
