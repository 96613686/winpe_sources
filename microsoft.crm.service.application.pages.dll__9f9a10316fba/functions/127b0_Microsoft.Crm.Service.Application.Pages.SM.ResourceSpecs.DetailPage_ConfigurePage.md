# Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::ConfigurePage

- ea: `0x127b0`
- end: `0x12de8`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::ConfigurePage`
- size: `1592`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x127b0`
- `0x12e20`

## string_xrefs

- `0x12c62`: `readonly`
- `0x127c6`: `/_nav/taskbox.css.aspx`
- `0x1293f`: `LOCID_RESSPEC_HLPLINKRES`
- `0x1294a`: `Resource_Spec_Helper_Link_Resources`
- `0x12960`: `LOCID_RESSPEC_HLPLINKRG`
- `0x1296b`: `Resource_Spec_Helper_Link_ResourceGroups`
- `0x12981`: `LOCID_RESSPEC_HLPLINKRULE`
- `0x1298c`: `Resource_Spec_Helper_Link_Rule`
- `0x129a2`: `LOCID_RESSPEC_HLPLINKFMT`
- `0x129ad`: `Resource_Spec_Helper_Link_Format`
- `0x12a73`: `Resource_Spec_Not_Selected_To_Delete`
- `0x12a94`: `Resource_Spec_Do_Not_Delete_Root`
- `0x12ab5`: `Resource_Spec_Delete_Confirmation`
- `0x12aca`: `Resource_Spec_Delete_Confirmation_Note`
- `0x12c9f`: `DetailPage_ConfigurePage_textbox`
- `0x12ce2`: `Task_Bar_Resource_Spec_Add_Rule`
- `0x12cf2`: `Task_Bar_Resource_Spec_Add_Rule_Tip`
- `0x12d12`: `Task_Bar_Resource_Spec_Add_Resources`
- `0x12d22`: `Task_Bar_Resource_Spec_Add_Resources_Tip`
- `0x12d42`: `Task_Bar_Resource_Spec_Add_ResourceGroups`
- `0x12d52`: `Task_Bar_Resource_Spec_Add_ResourceGroups_Tip`
- `0x12d7d`: `Task_Bar_Resource_Spec_Edit_Selected_Item`
- `0x12d8d`: `Task_Bar_Resource_Spec_Edit_Selected_Item_Tip`
- `0x12dbe`: `Task_Bar_Resource_Spec_Remove_Selected_Item`
- `0x12dce`: `Task_Bar_Resource_Spec_Remove_Selected_Item_Tip`
- `0x12dd8`: `<img alt="" src="/_imgs/ico/16_l_remove.gif">`
- `0x12ddd`: `DeleteSelectedItem();`

## pseudocode

```c

```

## disassembly

```asm
0x127b0  ldarg.0
0x127b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x127b6  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x127bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x127c0  ldarg.0
0x127c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x127c6  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0x127cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x127d0  ldarg.0
0x127d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x127d6  ldstr    aTreeFulltreeCs// "/_tree/fulltree.css.aspx"
0x127db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x127e0  ldarg.0
0x127e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x127e6  ldstr    aSmResourcespec// "/sm/resourcespecs/resourceruledialog.cs"...
0x127eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x127f0  ldarg.0
0x127f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x127f6  ldstr    aStaticSmResour// "/_static/sm/resourcespecs/resourcespecu"...
0x127fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x12800  ldarg.0
0x12801  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12806  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0x1280b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x12810  ldarg.0
0x12811  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12816  ldstr    aLocidResspecNo// "LOCID_RESSPEC_NORESOURCES"
0x1281b  ldarg.0
0x1281c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12821  ldstr    aResourceSelect_5// "Resource_Selection_Notification"
0x12826  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1282b  ldc.i4.0
0x1282c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12831  ldarg.0
0x12832  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12837  ldstr    aLocidResspecLe// "LOCID_RESSPEC_LEAST_BUSY"
0x1283c  ldarg.0
0x1283d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12842  ldstr    aResourceSelect_3// "Resource_Selection_Criteria_Least_Busy"
0x12847  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1284c  ldc.i4.0
0x1284d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12852  ldarg.0
0x12853  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12858  ldstr    aLocidResspecMo// "LOCID_RESSPEC_MOST_BUSY"
0x1285d  ldarg.0
0x1285e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12863  ldstr    aResourceSelect_4// "Resource_Selection_Criteria_Most_Busy"
0x12868  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1286d  ldc.i4.0
0x1286e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12873  ldarg.0
0x12874  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12879  ldstr    aLocidResspecCu// "LOCID_RESSPEC_CUSTOM"
0x1287e  ldarg.0
0x1287f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12884  ldstr    aResourceSelect// "Resource_Selection_Criteria_Custom"
0x12889  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1288e  ldc.i4.0
0x1288f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12894  ldarg.0
0x12895  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1289a  ldstr    aLocidResspecNa// "LOCID_RESSPEC_NAMEFMTGRP"
0x1289f  ldarg.0
0x128a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x128a5  ldstr    aResourceSpecNa// "Resource_Spec_Name_Format_Group"
0x128aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x128af  ldc.i4.0
0x128b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x128b5  ldarg.0
0x128b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x128bb  ldstr    aLocidResspecNa_0// "LOCID_RESSPEC_NAMEIMPL"
0x128c0  ldarg.0
0x128c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x128c6  ldstr    aResourceSpecNa_0// "Resource_Spec_Name_Implicit_Node_Name"
0x128cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x128d0  ldc.i4.0
0x128d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x128d6  ldarg.0
0x128d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x128dc  ldstr    aLocidResspecTr// "LOCID_RESSPEC_TREENOTLOADED"
0x128e1  ldarg.0
0x128e2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x128e7  ldstr    aWebSmResources_1// "Web.SM.ResourceSpecs.edit.aspx_115"
0x128ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x128f1  ldc.i4.0
0x128f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x128f7  ldarg.0
0x128f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x128fd  ldstr    aLocidResspecNo_0// "LOCID_RESSPEC_NOPARENTSEL"
0x12902  ldarg.0
0x12903  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12908  ldstr    aWebSmResources_2// "Web.SM.ResourceSpecs.edit.aspx_123"
0x1290d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12912  ldc.i4.0
0x12913  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12918  ldarg.0
0x12919  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1291e  ldstr    aLocidResspecNo_1// "LOCID_RESSPEC_NORULESEL"
0x12923  ldarg.0
0x12924  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12929  ldstr    aWebSmResources_3// "Web.SM.ResourceSpecs.edit.aspx_137"
0x1292e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12933  ldc.i4.0
0x12934  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12939  ldarg.0
0x1293a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1293f  ldstr    aLocidResspecHl// "LOCID_RESSPEC_HLPLINKRES"
0x12944  ldarg.0
0x12945  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1294a  ldstr    aResourceSpecHe// "Resource_Spec_Helper_Link_Resources"
0x1294f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12954  ldc.i4.0
0x12955  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1295a  ldarg.0
0x1295b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12960  ldstr    aLocidResspecHl_0// "LOCID_RESSPEC_HLPLINKRG"
0x12965  ldarg.0
0x12966  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1296b  ldstr    aResourceSpecHe_0// "Resource_Spec_Helper_Link_ResourceGroup"...
0x12970  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12975  ldc.i4.0
0x12976  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1297b  ldarg.0
0x1297c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12981  ldstr    aLocidResspecHl_1// "LOCID_RESSPEC_HLPLINKRULE"
0x12986  ldarg.0
0x12987  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1298c  ldstr    aResourceSpecHe_1// "Resource_Spec_Helper_Link_Rule"
0x12991  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12996  ldc.i4.0
0x12997  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1299c  ldarg.0
0x1299d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x129a2  ldstr    aLocidResspecHl_2// "LOCID_RESSPEC_HLPLINKFMT"
0x129a7  ldarg.0
0x129a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x129ad  ldstr    aResourceSpecHe_2// "Resource_Spec_Helper_Link_Format"
0x129b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x129b7  ldc.i4.0
0x129b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x129bd  ldarg.0
0x129be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x129c3  ldstr    aLocidResspecAl// "LOCID_RESSPEC_ALL"
0x129c8  ldarg.0
0x129c9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x129ce  ldstr    aDialogEditReso// "Dialog_Edit_Resource_Selection_All"
0x129d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x129d8  ldc.i4.0
0x129d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x129de  ldarg.0
0x129df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x129e4  ldstr    aLocidResspecSi// "LOCID_RESSPEC_SITESAME"
0x129e9  ldarg.0
0x129ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x129ef  ldstr    aResourceSelect_0// "Resource_Selection_Site_Same"
0x129f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x129f9  ldc.i4.0
0x129fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x129ff  ldarg.0
0x12a00  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12a05  ldstr    aLocidResspecSi_0// "LOCID_RESSPEC_SITEANY"
0x12a0a  ldarg.0
0x12a0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a10  ldstr    aResourceSelect_1// "Resource_Selection_Site_Any"
0x12a15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a1a  ldc.i4.0
0x12a1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12a20  ldarg.0
0x12a21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12a26  ldstr    aLocidResspecFm// "LOCID_RESSPEC_FMTQTY"
0x12a2b  ldarg.0
0x12a2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a31  ldstr    aResourceSpecNa_1// "Resource_Spec_Name_Format_Quantity"
0x12a36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a3b  ldc.i4.0
0x12a3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12a41  ldarg.0
0x12a42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12a47  ldstr    aLocidResspecFm_0// "LOCID_RESSPEC_FMTLBL"
0x12a4c  ldarg.0
0x12a4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a52  ldstr    aResourceSpecNa_2// "Resource_Spec_Name_Format_Label"
0x12a57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a5c  ldc.i4.0
0x12a5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12a62  ldarg.0
0x12a63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12a68  ldstr    aLocidResspecDe// "LOCID_RESSPEC_DELNOTSEL"
0x12a6d  ldarg.0
0x12a6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a73  ldstr    aResourceSpecNo// "Resource_Spec_Not_Selected_To_Delete"
0x12a78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a7d  ldc.i4.0
0x12a7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12a83  ldarg.0
0x12a84  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12a89  ldstr    aLocidResspecNo_2// "LOCID_RESSPEC_NODELROOT"
0x12a8e  ldarg.0
0x12a8f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12a94  ldstr    aResourceSpecDo// "Resource_Spec_Do_Not_Delete_Root"
0x12a99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a9e  ldc.i4.0
0x12a9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12aa4  ldarg.0
0x12aa5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12aaa  ldstr    aLocidResspecDe_0// "LOCID_RESSPEC_DELCONFIRM"
0x12aaf  ldarg.0
0x12ab0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12ab5  ldstr    aResourceSpecDe// "Resource_Spec_Delete_Confirmation"
0x12aba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12abf  ldstr    asc_2681A// "\n"
0x12ac4  ldarg.0
0x12ac5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12aca  ldstr    aResourceSpecDe_0// "Resource_Spec_Delete_Confirmation_Note"
0x12acf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12ad4  call     string [mscorlib]System.String::Concat(string, string, string)
0x12ad9  ldc.i4.0
0x12ada  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12adf  ldarg.0
0x12ae0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12ae5  ldstr    aLocidResspecNo_3// "LOCID_RESSPEC_NOSEL"
0x12aea  ldarg.0
0x12aeb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12af0  ldstr    aWebSmResources_4// "Web.SM.ResourceSpecs.Edit.aspx_269"
0x12af5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12afa  ldc.i4.0
0x12afb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12b00  ldarg.0
0x12b01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b06  ldstr    aLocidResspecNo_4// "LOCID_RESSPEC_NOIDTYPE"
0x12b0b  ldarg.0
0x12b0c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b11  ldstr    aWebSmResources_5// "Web.SM.ResourceSpecs.Edit.aspx_339"
0x12b16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b1b  ldc.i4.0
0x12b1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12b21  ldarg.0
0x12b22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b27  ldstr    aLocidResspecFm_1// "LOCID_RESSPEC_FMTNMCS"
0x12b2c  ldarg.0
0x12b2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b32  ldstr    aResourceSpecNa_3// "Resource_Spec_Name_Format_Name_Criteria"...
0x12b37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b3c  ldc.i4.0
0x12b3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12b42  ldarg.0
0x12b43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b48  ldstr    aLocidResspecFm_2// "LOCID_RESSPEC_FMTNM_S"
0x12b4d  ldarg.0
0x12b4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b53  ldstr    aResourceSpecNa_4// "Resource_Spec_Name_Format_Name_Site"
0x12b58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b5d  ldc.i4.0
0x12b5e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12b63  ldarg.0
0x12b64  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b69  ldstr    aLocidResspecFm_3// "LOCID_RESSPEC_FMTNMC_"
0x12b6e  ldarg.0
0x12b6f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b74  ldstr    aResourceSpecNa_5// "Resource_Spec_Name_Format_Name_Criteria"
0x12b79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b7e  ldc.i4.0
0x12b7f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12b84  ldarg.0
0x12b85  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b8a  ldstr    aLocidResspecFm_4// "LOCID_RESSPEC_FMTNM__"
0x12b8f  ldarg.0
0x12b90  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b95  ldstr    aResourceSpecNa_6// "Resource_Spec_Name_Format_Name"
0x12b9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12b9f  ldc.i4.0
0x12ba0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12ba5  ldarg.0
0x12ba6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12bab  ldstr    aLocidScheddlgD// "LOCID_SCHEDDLG_DISABLED_RES"
0x12bb0  ldarg.0
0x12bb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12bb6  ldstr    aResourceSelect_6// "Resource_Selection_Disabled_Resource_Fo"...
0x12bbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12bc0  ldc.i4.0
0x12bc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12bc6  ldarg.0
0x12bc7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12bcc  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0x12bd1  ldarg.0
0x12bd2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12bd7  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x12bdc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12be1  ldc.i4.0
0x12be2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12be7  ldarg.0
0x12be8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12bed  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0x12bf2  ldarg.0
0x12bf3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12bf8  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x12bfd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12c02  ldc.i4.0
0x12c03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
  ... truncated ...
```
