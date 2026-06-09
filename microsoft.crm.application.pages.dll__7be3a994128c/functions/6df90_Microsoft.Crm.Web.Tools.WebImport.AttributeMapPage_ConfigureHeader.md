# Microsoft.Crm.Web.Tools.WebImport.AttributeMapPage::ConfigureHeader

- ea: `0x6df90`
- end: `0x6e528`
- name: `Microsoft.Crm.Web.Tools.WebImport.AttributeMapPage::ConfigureHeader`
- size: `1432`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x6e002`: `/_static/_common/scripts/main.js`
- `0x6e012`: `ImportWebService`
- `0x6e0aa`: `LOCID_IW_INFO_COMPLETE`
- `0x6e0b5`: `ImportWizard.AttributeMapPage.InfoBalloon.CompletedText`
- `0x6e0ec`: `LOCID_IW_CREATENEWLEGEND`

## pseudocode

```c

```

## disassembly

```asm
0x6df90  ldarg.0
0x6df91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6df96  ldc.i4.1
0x6df97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x6df9c  ldarg.0
0x6df9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dfa2  ldstr    aStaticToolsImp// "/_static/tools/importwizard/scripts/imp"...
0x6dfa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dfac  ldarg.0
0x6dfad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dfb2  ldstr    aStaticControls_24// "/_static/_controls/multiselect/multisel"...
0x6dfb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dfbc  ldarg.0
0x6dfbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dfc2  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x6dfc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dfcc  ldarg.0
0x6dfcd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dfd2  ldstr    aStaticFormsChe_0// "/_static/_forms/checkbox.js"
0x6dfd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dfdc  ldarg.0
0x6dfdd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dfe2  ldstr    aStaticToolsImp_0// "/_static/tools/importwizard/scripts/att"...
0x6dfe7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dfec  ldarg.0
0x6dfed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6dff2  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x6dff7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6dffc  ldarg.0
0x6dffd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e002  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/main.js"
0x6e007  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6e00c  ldarg.0
0x6e00d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e012  ldstr    aImportwebservi// "ImportWebService"
0x6e017  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6e01c  ldarg.0
0x6e01d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e022  ldstr    aToolsImportwiz_2// "/tools/importwizard/importwizard.css.as"...
0x6e027  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6e02c  ldarg.0
0x6e02d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e032  ldstr    aImportwizardon// "ImportWizardOnLoad"
0x6e037  ldstr    aImportwizardpa// "ImportWizardPage_OnLoad();"
0x6e03c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x6e041  ldarg.0
0x6e042  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e047  ldstr    aLocidIwWarning// "LOCID_IW_WARNINGIMAGE_ALTTEXT"
0x6e04c  ldarg.0
0x6e04d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e052  ldstr    aImportwizardAt// "ImportWizard.AttributeMapPage.InfoBallo"...
0x6e057  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e05c  ldc.i4.0
0x6e05d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e062  ldarg.0
0x6e063  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e068  ldstr    aLocidIwTickima// "LOCID_IW_TICKIMAGE_ALTTEXT"
0x6e06d  ldarg.0
0x6e06e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e073  ldstr    aImportwizardAt_0// "ImportWizard.AttributeMapPage.InfoBallo"...
0x6e078  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e07d  ldc.i4.0
0x6e07e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e083  ldarg.0
0x6e084  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e089  ldstr    aLocidIwInfoWar// "LOCID_IW_INFO_WARNING"
0x6e08e  ldarg.0
0x6e08f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e094  ldstr    aImportwizardAt_1// "ImportWizard.AttributeMapPage.InfoBallo"...
0x6e099  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e09e  ldc.i4.0
0x6e09f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e0a4  ldarg.0
0x6e0a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e0aa  ldstr    aLocidIwInfoCom// "LOCID_IW_INFO_COMPLETE"
0x6e0af  ldarg.0
0x6e0b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e0b5  ldstr    aImportwizardAt_2// "ImportWizard.AttributeMapPage.InfoBallo"...
0x6e0ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e0bf  ldc.i4.0
0x6e0c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e0c5  ldarg.0
0x6e0c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e0cb  ldstr    aLocidIwWarning_0// "LOCID_IW_WARNINGLEGEND"
0x6e0d0  ldarg.0
0x6e0d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e0d6  ldstr    aImportwizardAt_3// "ImportWizard.AttributeMapPage.UnmappedI"...
0x6e0db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e0e0  ldc.i4.0
0x6e0e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e0e6  ldarg.0
0x6e0e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e0ec  ldstr    aLocidIwCreaten// "LOCID_IW_CREATENEWLEGEND"
0x6e0f1  ldarg.0
0x6e0f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e0f7  ldstr    aImportwizardAt_4// "ImportWizard.AttributeMapPage.NewAttrib"...
0x6e0fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e101  ldc.i4.0
0x6e102  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e107  ldarg.0
0x6e108  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e10d  ldstr    aLocidIwLookupl// "LOCID_IW_LOOKUPLEGEND"
0x6e112  ldarg.0
0x6e113  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e118  ldstr    aImportwizardAt_5// "ImportWizard.AttributeMapPage.LookupIma"...
0x6e11d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e122  ldc.i4.0
0x6e123  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e128  ldarg.0
0x6e129  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e12e  ldstr    aLocidIwPicklis// "LOCID_IW_PICKLISTLEGEND"
0x6e133  ldarg.0
0x6e134  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e139  ldstr    aImportwizardAt_6// "ImportWizard.AttributeMapPage.PicklistI"...
0x6e13e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e143  ldc.i4.0
0x6e144  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e149  ldarg.0
0x6e14a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e14f  ldstr    aLocidMappingWi// "LOCID_MAPPING_WILLBE_LOST"
0x6e154  ldarg.0
0x6e155  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e15a  ldstr    aImportwizardGe// "ImportWizard.Generic.AllMappingsWillBeL"...
0x6e15f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e164  ldc.i4.0
0x6e165  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e16a  ldarg.0
0x6e16b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e170  ldstr    aLocidIwMappedi// "LOCID_IW_MAPPEDIMAGE_ALTTEXT"
0x6e175  ldarg.0
0x6e176  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e17b  ldstr    aImportwizardEn_6// "ImportWizard.EntityMapPage.MappedImage."...
0x6e180  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e185  ldc.i4.0
0x6e186  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e18b  ldarg.0
0x6e18c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e191  ldstr    aLocidIwUnmappe// "LOCID_IW_UNMAPPEDIMAGE_ALTTEXT"
0x6e196  ldarg.0
0x6e197  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e19c  ldstr    aImportwizardEn_7// "ImportWizard.EntityMapPage.UnmappedImag"...
0x6e1a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e1a6  ldc.i4.0
0x6e1a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e1ac  ldarg.0
0x6e1ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e1b2  ldstr    aLocidIwEmptydi// "LOCID_IW_EMPTYDISPLAYNAME"
0x6e1b7  ldarg.0
0x6e1b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e1bd  ldstr    aImportwizardAt_7// "ImportWizard.AttributeMapPage.CustomAtt"...
0x6e1c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e1c7  ldc.i4.0
0x6e1c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e1cd  ldarg.0
0x6e1ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e1d3  ldstr    aLocidOptgroupN// "LOCID_OPTGROUP_NEWENTITIES"
0x6e1d8  ldarg.0
0x6e1d9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e1de  ldstr    aImportwizardEn_9// "ImportWizard.EntityMapPage.SelectGroup."...
0x6e1e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e1e8  ldc.i4.0
0x6e1e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e1ee  ldarg.0
0x6e1ef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e1f4  ldstr    aLocidOptgroupA_0// "LOCID_OPTGROUP_ATTRIBUTES"
0x6e1f9  ldarg.0
0x6e1fa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e1ff  ldstr    aImportwizardAt_8// "ImportWizard.AttributeMapPage.Attribute"...
0x6e204  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e209  ldc.i4.0
0x6e20a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e20f  ldarg.0
0x6e210  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e215  ldstr    aLocidOptgroupN_0// "LOCID_OPTGROUP_NEWATTRIBUTES"
0x6e21a  ldarg.0
0x6e21b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e220  ldstr    aImportwizardAt_9// "ImportWizard.AttributeMapPage.Attribute"...
0x6e225  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e22a  ldc.i4.0
0x6e22b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e230  ldarg.0
0x6e231  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e236  ldstr    aLocidUnmappedM// "LOCID_UNMAPPED_MANDATORY_ATTRIB"
0x6e23b  ldarg.0
0x6e23c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e241  ldstr    aImportwizardAt_10// "ImportWizard.AttributeMapPage.Mandatory"...
0x6e246  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e24b  ldc.i4.0
0x6e24c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e251  ldarg.0
0x6e252  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e257  ldstr    aLocidSkipUnmap// "LOCID_SKIP_UNMAPPED_ATTRIB1"
0x6e25c  ldarg.0
0x6e25d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e262  ldstr    aImportwizardAt_11// "ImportWizard.AttributeMapPage.SkipUnmap"...
0x6e267  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e26c  ldc.i4.0
0x6e26d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e272  ldarg.0
0x6e273  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e278  ldstr    aLocidSkipUnmap_0// "LOCID_SKIP_UNMAPPED_ATTRIB2"
0x6e27d  ldarg.0
0x6e27e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e283  ldstr    aImportwizardAt_12// "ImportWizard.AttributeMapPage.SkipUnmap"...
0x6e288  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e28d  ldc.i4.0
0x6e28e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e293  ldarg.0
0x6e294  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e299  ldstr    aLocidWarnManda// "LOCID_WARN_MANDATORY_ATTRIB"
0x6e29e  ldarg.0
0x6e29f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e2a4  ldstr    aImportwizardAt_13// "ImportWizard.AttributeMapPage.WarnManda"...
0x6e2a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e2ae  ldc.i4.0
0x6e2af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e2b4  ldarg.0
0x6e2b5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e2ba  ldstr    aLocidIwLkupatt// "LOCID_IW_LKUPATTR_SLCT_TITLE"
0x6e2bf  ldarg.0
0x6e2c0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e2c5  ldstr    aImportwizardAt_14// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e2ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e2cf  ldc.i4.0
0x6e2d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e2d5  ldarg.0
0x6e2d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e2db  ldstr    aLocidIwLkupatt_0// "LOCID_IW_LKUPATTR_SLCT_TOOLTIP"
0x6e2e0  ldarg.0
0x6e2e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e2e6  ldstr    aImportwizardAt_15// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e2eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e2f0  ldc.i4.0
0x6e2f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e2f6  ldarg.0
0x6e2f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e2fc  ldstr    aLocidIwLookupR// "LOCID_IW_LOOKUP_REFER_ERROR"
0x6e301  ldarg.0
0x6e302  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e307  ldstr    aImportwizardAt_16// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e30c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e311  ldc.i4.0
0x6e312  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e317  ldarg.0
0x6e318  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e31d  ldstr    aLocidIwLookupP// "LOCID_IW_LOOKUP_POPUP_TITLE"
0x6e322  ldarg.0
0x6e323  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e328  ldstr    aImportwizardAt_17// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e32d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e332  ldc.i4.0
0x6e333  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e338  ldarg.0
0x6e339  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e33e  ldstr    aLocidIwPicklis_0// "LOCID_IW_PICKLIST_POPUP_TITLE"
0x6e343  ldarg.0
0x6e344  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e349  ldstr    aImportwizardAt_18// "ImportWizard.AttributeMapPage.PicklistA"...
0x6e34e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e353  ldc.i4.0
0x6e354  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e359  ldarg.0
0x6e35a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e35f  ldstr    aLocidIwNewattr// "LOCID_IW_NEWATTRIB_POPUP_TITLE"
0x6e364  ldarg.0
0x6e365  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e36a  ldstr    aImportwizardAt_19// "ImportWizard.AttributeMapPage.CustomAtt"...
0x6e36f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e374  ldc.i4.0
0x6e375  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e37a  ldarg.0
0x6e37b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e380  ldstr    aLocidIwLookupN// "LOCID_IW_LOOKUP_NO_SOURCE"
0x6e385  ldarg.0
0x6e386  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e38b  ldstr    aImportwizardAt_20// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e390  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e395  ldc.i4.0
0x6e396  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e39b  ldarg.0
0x6e39c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e3a1  ldstr    aLocidIwLookupI// "LOCID_IW_LOOKUP_INTERNALMAPPING"
0x6e3a6  ldarg.0
0x6e3a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e3ac  ldstr    aImportwizardAt_21// "ImportWizard.AttributeMapPage.LookupAtt"...
0x6e3b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e3b6  ldc.i4.0
0x6e3b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e3bc  ldarg.0
0x6e3bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e3c2  ldstr    aLocidIwPicklis_1// "LOCID_IW_PICKLIST_NO_SOURCE"
0x6e3c7  ldarg.0
0x6e3c8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6e3cd  ldstr    aImportwizardAt_22// "ImportWizard.AttributeMapPage.PicklistA"...
0x6e3d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e3d7  ldc.i4.0
0x6e3d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6e3dd  ldarg.0
0x6e3de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6e3e3  ldstr    aLocidIwPicklis_2// "LOCID_IW_PICKLIST_ACTIONS"
  ... truncated ...
```
