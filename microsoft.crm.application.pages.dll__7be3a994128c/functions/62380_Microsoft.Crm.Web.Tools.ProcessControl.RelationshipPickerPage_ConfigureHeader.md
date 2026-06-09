# Microsoft.Crm.Web.Tools.ProcessControl.RelationshipPickerPage::ConfigureHeader

- ea: `0x62380`
- end: `0x625d3`
- name: `Microsoft.Crm.Web.Tools.ProcessControl.RelationshipPickerPage::ConfigureHeader`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x62380`

## string_xrefs

- `0x62497`: `/_common/styles/dialogs.css.aspx`
- `0x62398`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x623d8`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x62418`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x623a8`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x623b8`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x62582`: `ProcessControl.Configurator.EntityLabel`
- `0x625a2`: `ProcessControl.Configurator.RelationshipLabel`
- `0x623c8`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x624e8`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x624d8`: `/tools/processcontrol/configuration.css.aspx`
- `0x62508`: `/_static/tools/ProcessConfiguration/ProcessConfiguration.js`
- `0x62522`: `ProcessControl.Configurator.InvalidRelationships`
- `0x62542`: `ProcessControl.Configurator.NoRelationshipsToSelect`
- `0x62562`: `ProcessControl.Configurator.PreviousStageLabel`
- `0x625c2`: `ProcessControl.Configurator.None`

## pseudocode

```c

```

## disassembly

```asm
0x62380  ldarg.0
0x62381  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x62386  ldarg.0
0x62387  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6238c  ldc.i4.1
0x6238d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x62392  ldarg.0
0x62393  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62398  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0x6239d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623a2  ldarg.0
0x623a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623a8  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0x623ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623b2  ldarg.0
0x623b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623b8  ldstr    aStaticCommonSc_30// "/_static/_common/scripts/SalesCommonFra"...
0x623bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623c2  ldarg.0
0x623c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623c8  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0x623cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623d2  ldarg.0
0x623d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623d8  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x623dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623e2  ldarg.0
0x623e3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623e8  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x623ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x623f2  ldarg.0
0x623f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x623f8  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x623fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62402  ldarg.0
0x62403  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62408  ldstr    aStaticFormsTab// "/_static/_forms/tabs.js"
0x6240d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62412  ldarg.0
0x62413  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62418  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x6241d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62422  ldarg.0
0x62423  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62428  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x6242d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62432  ldarg.0
0x62433  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62438  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0x6243d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62442  ldarg.0
0x62443  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62448  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x6244d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62452  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::.ctor()
0x62457  callvirt instance class [System]System.Collections.Generic.Queue`1<string> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::get_RequiredScriptReferencesQueue()
0x6245c  callvirt instance valuetype [System]System.Collections.Generic.Queue`1/Enumerator<var<u1>> class [System]System.Collections.Generic.Queue`1<string>::GetEnumerator()
0x62461  stloc.0
0x62462  br.s     loc_62478
0x62464  ldloca.s 0
0x62466  call     instance var<u1> valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>::get_Current()
0x6246b  stloc.1
0x6246c  ldarg.0
0x6246d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62472  ldloc.1
0x62473  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62478  ldloca.s 0
0x6247a  call     instance bool valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>::MoveNext()
0x6247f  brtrue.s loc_62464
0x62481  leave.s  loc_62491
0x62483  ldloca.s 0
0x62485  constrained. valuetype [System]System.Collections.Generic.Queue`1/Enumerator<string>
0x6248b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62490  endfinally
0x62491  ldarg.0
0x62492  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62497  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x6249c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x624a1  ldarg.0
0x624a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624a7  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x624ac  ldnull
0x624ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x624b2  ldarg.0
0x624b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624b8  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x624bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x624c2  ldarg.0
0x624c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624c8  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x624cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x624d2  ldarg.0
0x624d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624d8  ldstr    aToolsProcessco_3// "/tools/processcontrol/configuration.css"...
0x624dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x624e2  ldarg.0
0x624e3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624e8  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0x624ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x624f2  ldarg.0
0x624f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x624f8  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0x624fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62502  ldarg.0
0x62503  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62508  ldstr    aStaticToolsPro// "/_static/tools/ProcessConfiguration/Pro"...
0x6250d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62512  ldarg.0
0x62513  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62518  ldstr    aLocidProcessDi// "LOCID_PROCESS_DIALOG_INVALID"
0x6251d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x62522  ldstr    aProcesscontrol_31// "ProcessControl.Configurator.InvalidRela"...
0x62527  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6252c  ldc.i4.0
0x6252d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62532  ldarg.0
0x62533  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62538  ldstr    aLocidProcessDi_0// "LOCID_PROCESS_DIALOG_NO_RELATION"
0x6253d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x62542  ldstr    aProcesscontrol_32// "ProcessControl.Configurator.NoRelations"...
0x62547  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6254c  ldc.i4.0
0x6254d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62552  ldarg.0
0x62553  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62558  ldstr    aLocidProcessDi_1// "LOCID_PROCESS_DIALOG_PREV_STAGE"
0x6255d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x62562  ldstr    aProcesscontrol_33// "ProcessControl.Configurator.PreviousSta"...
0x62567  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6256c  ldc.i4.0
0x6256d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62572  ldarg.0
0x62573  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62578  ldstr    aLocidProcessDi_2// "LOCID_PROCESS_DIALOG_ENTITY"
0x6257d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x62582  ldstr    aProcesscontrol_9// "ProcessControl.Configurator.EntityLabel"
0x62587  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6258c  ldc.i4.0
0x6258d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62592  ldarg.0
0x62593  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62598  ldstr    aLocidProcessDi_3// "LOCID_PROCESS_DIALOG_RELATION"
0x6259d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x625a2  ldstr    aProcesscontrol_15// "ProcessControl.Configurator.Relationshi"...
0x625a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x625ac  ldc.i4.0
0x625ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x625b2  ldarg.0
0x625b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x625b8  ldstr    aLocidProcessDi_4// "LOCID_PROCESS_DIALOG_NONE"
0x625bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x625c2  ldstr    aProcesscontrol_34// "ProcessControl.Configurator.None"
0x625c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x625cc  ldc.i4.0
0x625cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x625d2  ret
```
