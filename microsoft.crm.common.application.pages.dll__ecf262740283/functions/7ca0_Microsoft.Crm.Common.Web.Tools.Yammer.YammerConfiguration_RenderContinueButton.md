# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::RenderContinueButton

- ea: `0x7ca0`
- end: `0x7d0f`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::RenderContinueButton`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7c50`

## callees

- `0x7ca0`

## string_xrefs

- `0x7ca5`: `Web.Tools.Yammer.Config.ContinueButton`
- `0x7cb8`: `$P_CRM('#disclaimerPart').hide();  $P_CRM('#disclaimerTitle').hide();  $P_CRM('#configPart').css('display','inline'); $P_CRM('#configPart').show();  $P_CRM('#configTitle').css('display','inline');`

## pseudocode

```c

```

## disassembly

```asm
0x7ca0  ldstr    aButtoncontinue// "buttonContinue"
0x7ca5  ldstr    aWebToolsYammer_3// "Web.Tools.Yammer.Config.ContinueButton"
0x7caa  stloc.0
0x7cab  ldarg.0
0x7cac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7cb1  ldloc.0
0x7cb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cb7  stloc.1
0x7cb8  ldstr    aPCrmDisclaimer// "$P_CRM('#disclaimerPart').hide();  $P_C"...
0x7cbd  stloc.2
0x7cbe  ldnull
0x7cbf  ldloc.2
0x7cc0  ldc.i4.0
0x7cc1  ldstr    aMsCrmFooterbut// "ms-crm-FooterButton"
0x7cc6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string, bool, string)
0x7ccb  stloc.3
0x7ccc  ldloc.3
0x7ccd  ldloc.1
0x7cce  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x7cd3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x7cd8  ldloc.3
0x7cd9  ldloc.1
0x7cda  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x7cdf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x7ce4  ldloc.3
0x7ce5  ldarg.0
0x7ce6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ceb  ldloc.0
0x7cec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cf1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x7cf6  ldarg.1
0x7cf7  ldloc.3
0x7cf8  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_OuterHtml()
0x7cfd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7d02  leave.s  loc_7D0E
0x7d04  ldloc.3
0x7d05  brfalse.s loc_7D0D
0x7d07  ldloc.3
0x7d08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d0d  endfinally
0x7d0e  ret
```
