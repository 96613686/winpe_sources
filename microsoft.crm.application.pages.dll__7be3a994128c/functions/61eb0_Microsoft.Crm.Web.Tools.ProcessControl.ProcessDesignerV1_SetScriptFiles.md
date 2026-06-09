# Microsoft.Crm.Web.Tools.ProcessControl.ProcessDesignerV1::SetScriptFiles

- ea: `0x61eb0`
- end: `0x621c1`
- name: `Microsoft.Crm.Web.Tools.ProcessControl.ProcessDesignerV1::SetScriptFiles`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5e1c0`

## callees

- `0x61eb0`

## string_xrefs

- `0x61ee2`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x61ef2`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x61f02`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x61ec2`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x61ed2`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x6201b`: `/_static/_common/scripts/`
- `0x62056`: `/_static/_common/scripts/`
- `0x62071`: `/_static/_common/scripts/`
- `0x6208c`: `/_static/_common/scripts/`
- `0x620a7`: `/_static/_common/scripts/`
- `0x620c2`: `/_static/_common/scripts/`
- `0x620fd`: `/_static/_common/scripts/`
- `0x62118`: `/_static/_common/scripts/`
- `0x62133`: `/_static/_common/scripts/`
- `0x6214e`: `/_static/_common/scripts/`
- `0x62169`: `/_static/_common/scripts/`
- `0x62184`: `/_static/_common/scripts/`
- `0x6219f`: `/_static/_common/scripts/`
- `0x62036`: `/_static/_common/scripts/underscore.js`
- `0x62046`: `/_static/_common/scripts/backbone.js`

## pseudocode

```c

```

## disassembly

```asm
0x61eb0  ldarg.0
0x61eb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61eb6  ldc.i4.0
0x61eb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x61ebc  ldarg.0
0x61ebd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61ec2  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0x61ec7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61ecc  ldarg.0
0x61ecd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61ed2  ldstr    aStaticCommonSc_30// "/_static/_common/scripts/SalesCommonFra"...
0x61ed7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61edc  ldarg.0
0x61edd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61ee2  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0x61ee7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61eec  ldarg.0
0x61eed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61ef2  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0x61ef7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61efc  ldarg.0
0x61efd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f02  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x61f07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f0c  ldarg.0
0x61f0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f12  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x61f17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f1c  ldarg.0
0x61f1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f22  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0x61f27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f2c  ldarg.0
0x61f2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f32  ldstr    aStaticFormsLoo_0// "/_static/_forms/LookupBehavior.js"
0x61f37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f3c  ldarg.0
0x61f3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f42  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0x61f47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f4c  ldarg.0
0x61f4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f52  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0x61f57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f5c  ldarg.0
0x61f5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f62  ldstr    aStaticFormsChe// "/_static/_forms/Checkbox.js"
0x61f67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f6c  ldarg.0
0x61f6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f72  ldstr    aStaticFormsTab// "/_static/_forms/tabs.js"
0x61f77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f7c  ldarg.0
0x61f7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f82  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x61f87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f8c  ldarg.0
0x61f8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61f92  ldstr    aStaticControls_21// "/_static/_controls/editableselect/edita"...
0x61f97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61f9c  ldarg.0
0x61f9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61fa2  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x61fa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61fac  ldarg.0
0x61fad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61fb2  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0x61fb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61fbc  ldarg.0
0x61fbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61fc2  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x61fc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61fcc  ldarg.0
0x61fcd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x61fd2  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x61fd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x61fdc  ldsfld   string [mscorlib]System.String::Empty
0x61fe1  stloc.0
0x61fe2  ldsfld   string [mscorlib]System.String::Empty
0x61fe7  stloc.1
0x61fe8  ldarg.0
0x61fe9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IProcessConfigurationViewModel Microsoft.Crm.Web.Tools.ProcessControl.ProcessDesignerV1::processConfigurationViewModel
0x61fee  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IProcessConfigurationViewModel::get_ProcessDefinition()
0x61ff3  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowBusinessProcessType()
0x61ff8  ldc.i4.1
0x61ff9  bne.un.s loc_62009
0x61ffb  ldstr    aTbxdesignercon// "TBXDesignerControl/"
0x62000  stloc.0
0x62001  ldstr    aTbxdesignercon_0// "TBXDesignerControl.js"
0x62006  stloc.1
0x62007  br.s     loc_62030
0x62009  ldstr    aProcesscontrol_30// "processcontrol/"
0x6200e  stloc.0
0x6200f  ldstr    aProcessdesigne_332// "ProcessDesignerControl.js"
0x62014  stloc.1
0x62015  ldarg.0
0x62016  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6201b  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62020  ldloc.0
0x62021  ldstr    aSdkRestJs// "SDK.REST.js"
0x62026  call     string [mscorlib]System.String::Concat(string, string, string)
0x6202b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62030  ldarg.0
0x62031  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62036  ldstr    aStaticCommonSc_32// "/_static/_common/scripts/underscore.js"
0x6203b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62040  ldarg.0
0x62041  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62046  ldstr    aStaticCommonSc_33// "/_static/_common/scripts/backbone.js"
0x6204b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62050  ldarg.0
0x62051  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62056  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x6205b  ldloc.0
0x6205c  ldstr    aMsglobalJs// "msglobal.js"
0x62061  call     string [mscorlib]System.String::Concat(string, string, string)
0x62066  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6206b  ldarg.0
0x6206c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62071  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62076  ldloc.0
0x62077  ldstr    aJqueryUiJs// "jquery-ui.js"
0x6207c  call     string [mscorlib]System.String::Concat(string, string, string)
0x62081  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62086  ldarg.0
0x62087  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6208c  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62091  ldloc.0
0x62092  ldstr    aJqueryFracs015// "jquery.fracs-0.15.0.js"
0x62097  call     string [mscorlib]System.String::Concat(string, string, string)
0x6209c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620a1  ldarg.0
0x620a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620a7  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x620ac  ldloc.0
0x620ad  ldstr    aJqueryOutline0// "jquery.outline-0.15.0.js"
0x620b2  call     string [mscorlib]System.String::Concat(string, string, string)
0x620b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620bc  ldarg.0
0x620bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620c2  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x620c7  ldloc.0
0x620c8  ldstr    aGenericworkflo_15// "GenericWorkflowDesigner.js"
0x620cd  call     string [mscorlib]System.String::Concat(string, string, string)
0x620d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620d7  ldarg.0
0x620d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620dd  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0x620e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620e7  ldarg.0
0x620e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620ed  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0x620f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x620f7  ldarg.0
0x620f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x620fd  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62102  ldloc.0
0x62103  ldstr    aTelemetrylibra// "TelemetryLibrary.js"
0x62108  call     string [mscorlib]System.String::Concat(string, string, string)
0x6210d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62112  ldarg.0
0x62113  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62118  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x6211d  ldloc.0
0x6211e  ldstr    aESmartZoomJque// "e-smart-zoom-jquery.js"
0x62123  call     string [mscorlib]System.String::Concat(string, string, string)
0x62128  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6212d  ldarg.0
0x6212e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62133  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62138  ldloc.0
0x62139  ldstr    aHtml2canvasJs// "html2canvas.js"
0x6213e  call     string [mscorlib]System.String::Concat(string, string, string)
0x62143  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62148  ldarg.0
0x62149  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6214e  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62153  ldloc.0
0x62154  ldstr    aGenericworkflo_16// "GenericWorkflowDesigner.css"
0x62159  call     string [mscorlib]System.String::Concat(string, string, string)
0x6215e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x62163  ldarg.0
0x62164  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62169  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x6216e  ldloc.0
0x6216f  ldstr    aStyleCss// "style.css"
0x62174  call     string [mscorlib]System.String::Concat(string, string, string)
0x62179  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6217e  ldarg.0
0x6217f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62184  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x62189  ldloc.0
0x6218a  ldstr    aProcessdesigne_333// "ProcessDesigner.css"
0x6218f  call     string [mscorlib]System.String::Concat(string, string, string)
0x62194  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x62199  ldarg.0
0x6219a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6219f  ldstr    aStaticCommonSc_31// "/_static/_common/scripts/"
0x621a4  ldloc.0
0x621a5  ldloc.1
0x621a6  call     string [mscorlib]System.String::Concat(string, string, string)
0x621ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x621b0  ldarg.0
0x621b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x621b6  ldstr    aStaticToolsSys_2// "/_static/tools/systemcustomization/busi"...
0x621bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x621c0  ret
```
