# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesDesigner::SetScriptFiles

- ea: `0xb5520`
- end: `0xb562d`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesDesigner::SetScriptFiles`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb2f70`

## string_xrefs

- `0xb5532`: `/_static/_common/scripts/underscore.js`
- `0xb5542`: `/_static/_common/scripts/backbone.js`
- `0xb5552`: `/_static/_common/scripts/BusinessRulesDesigner/mscommonlib-1.0.0.js`
- `0xb5562`: `/_static/_common/scripts/BusinessRulesDesigner/msglobal.js`
- `0xb5572`: `/_static/_common/scripts/BusinessRulesDesigner/jquery-ui.js`
- `0xb5582`: `/_static/_common/scripts/BusinessRulesDesigner/jquery.fracs-0.15.0.js`
- `0xb5592`: `/_static/_common/scripts/BusinessRulesDesigner/jquery.outline-0.15.0.js`
- `0xb55a2`: `/_static/_common/scripts/BusinessRulesDesigner/GenericWorkflowDesigner.js`
- `0xb55c2`: `/_static/_common/scripts/BusinessRulesDesigner/TelemetryLibrary.js`
- `0xb55d2`: `/_static/_common/scripts/BusinessRulesDesigner/e-smart-zoom-jquery.js`
- `0xb55e2`: `/_static/_common/scripts/BusinessRulesDesigner/html2canvas.js`
- `0xb55f2`: `/_static/_common/scripts/BusinessRulesDesigner/GenericWorkflowDesigner.css`
- `0xb5602`: `/_static/_common/scripts/BusinessRulesDesigner/style.css`
- `0xb5612`: `/_static/_common/scripts/BusinessRulesDesigner/ProcessDesigner.css`
- `0xb5622`: `/_static/_common/scripts/BusinessRulesDesigner/PBLDesignerControl.js`

## pseudocode

```c

```

## disassembly

```asm
0xb5520  ldarg.0
0xb5521  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5526  ldc.i4.0
0xb5527  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xb552c  ldarg.0
0xb552d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5532  ldstr    aStaticCommonSc_32// "/_static/_common/scripts/underscore.js"
0xb5537  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb553c  ldarg.0
0xb553d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5542  ldstr    aStaticCommonSc_33// "/_static/_common/scripts/backbone.js"
0xb5547  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb554c  ldarg.0
0xb554d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5552  ldstr    aStaticCommonSc_41// "/_static/_common/scripts/BusinessRulesD"...
0xb5557  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb555c  ldarg.0
0xb555d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5562  ldstr    aStaticCommonSc_42// "/_static/_common/scripts/BusinessRulesD"...
0xb5567  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb556c  ldarg.0
0xb556d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5572  ldstr    aStaticCommonSc_43// "/_static/_common/scripts/BusinessRulesD"...
0xb5577  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb557c  ldarg.0
0xb557d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5582  ldstr    aStaticCommonSc_44// "/_static/_common/scripts/BusinessRulesD"...
0xb5587  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb558c  ldarg.0
0xb558d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5592  ldstr    aStaticCommonSc_45// "/_static/_common/scripts/BusinessRulesD"...
0xb5597  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb559c  ldarg.0
0xb559d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55a2  ldstr    aStaticCommonSc_46// "/_static/_common/scripts/BusinessRulesD"...
0xb55a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb55ac  ldarg.0
0xb55ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55b2  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0xb55b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb55bc  ldarg.0
0xb55bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55c2  ldstr    aStaticCommonSc_47// "/_static/_common/scripts/BusinessRulesD"...
0xb55c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb55cc  ldarg.0
0xb55cd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55d2  ldstr    aStaticCommonSc_48// "/_static/_common/scripts/BusinessRulesD"...
0xb55d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb55dc  ldarg.0
0xb55dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55e2  ldstr    aStaticCommonSc_49// "/_static/_common/scripts/BusinessRulesD"...
0xb55e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb55ec  ldarg.0
0xb55ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb55f2  ldstr    aStaticCommonSc_50// "/_static/_common/scripts/BusinessRulesD"...
0xb55f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb55fc  ldarg.0
0xb55fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5602  ldstr    aStaticCommonSc_51// "/_static/_common/scripts/BusinessRulesD"...
0xb5607  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb560c  ldarg.0
0xb560d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5612  ldstr    aStaticCommonSc_52// "/_static/_common/scripts/BusinessRulesD"...
0xb5617  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb561c  ldarg.0
0xb561d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5622  ldstr    aStaticCommonSc_53// "/_static/_common/scripts/BusinessRulesD"...
0xb5627  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb562c  ret
```
