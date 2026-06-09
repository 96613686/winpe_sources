# Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigurePage

- ea: `0x870`
- end: `0xa70`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigurePage`
- size: `512`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xa65`: `KnowledgeManagementWebService`

## pseudocode

```c

```

## disassembly

```asm
0x870  ldarg.0
0x871  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x876  ldstr    aLocidDocmSavee// "LOCID_DOCM_SAVEERROR"
0x87b  ldarg.0
0x87c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x881  ldstr    aWebToolsKnowle_12// "Web.Tools.KnowledgeManagement.SettingsP"...
0x886  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88b  ldc.i4.0
0x88c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x891  ldarg.0
0x892  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x897  ldstr    aLocidDocmUrler// "LOCID_DOCM_URLERROR"
0x89c  ldarg.0
0x89d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8a2  ldstr    aSearchwidgetSe// "SearchWidget.SetupWizard.Parature.Login"...
0x8a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ac  ldc.i4.0
0x8ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8b2  ldarg.0
0x8b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8b8  ldstr    aLocidKmInvalid// "LOCID_KM_INVALIDSUPPORTURL"
0x8bd  ldarg.0
0x8be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c3  ldstr    aWebToolsKmSett// "Web.Tools.KM.SettingsPage.WarningMessag"...
0x8c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cd  ldc.i4.0
0x8ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8d3  ldarg.0
0x8d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d9  ldstr    aLocidWrongSupp// "LOCID_WRONG_SUPPORTURLFORMAT"
0x8de  ldarg.0
0x8df  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e4  ldstr    aWebToolsKmSett_0// "Web.Tools.KM.SettingsPage.WarningMessag"...
0x8e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ee  ldc.i4.0
0x8ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8f4  ldarg.0
0x8f5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8fa  ldstr    aLocidKmInvalid_0// "LOCID_KM_INVALIDNATIVECRMURL"
0x8ff  ldarg.0
0x900  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x905  ldstr    aWebToolsKmSett_1// "Web.Tools.KM.SettingsPage.WarningMessag"...
0x90a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90f  ldc.i4.0
0x910  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x915  ldarg.0
0x916  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x91b  ldstr    aLocidWrongNati// "LOCID_WRONG_NATIVECRMURLFORMAT"
0x920  ldarg.0
0x921  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x926  ldstr    aWebToolsKmSett_2// "Web.Tools.KM.SettingsPage.WarningMessag"...
0x92b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x930  ldc.i4.0
0x931  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x936  ldarg.0
0x937  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x93c  ldstr    aLocidWrongNati_0// "LOCID_WRONG_NATIVECRMURLNOKBNO"
0x941  ldarg.0
0x942  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x947  ldstr    aWebToolsKmSett_3// "Web.Tools.KM.SettingsPage.WarningMessag"...
0x94c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x951  ldc.i4.0
0x952  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x957  ldarg.0
0x958  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95d  ldstr    aLocidKmwallPar// "LOCID_KMWALL_PARATURE_403_C6001"
0x962  ldarg.0
0x963  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x968  ldstr    aSearchwidgetSe// "SearchWidget.SetupWizard.Parature.Login"...
0x96d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x972  ldc.i4.0
0x973  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x978  ldarg.0
0x979  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e  ldstr    aLocidKmwallPar_0// "LOCID_KMWALL_PARATURE_403_C6002"
0x983  ldarg.0
0x984  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x989  ldstr    aSearchwidgetSe_0// "SearchWidget.SetupWizard.Parature.Inval"...
0x98e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x993  ldc.i4.0
0x994  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x999  ldarg.0
0x99a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99f  ldstr    aLocidKmwallPar_1// "LOCID_KMWALL_PARATURE_403_C6003"
0x9a4  ldarg.0
0x9a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9aa  ldstr    aSearchwidgetPa// "SearchWidget.Parature.InvalidDeptId.403"...
0x9af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9b4  ldc.i4.0
0x9b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ba  ldarg.0
0x9bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9c0  ldstr    aLocidKmwallPar_2// "LOCID_KMWALL_PARATURE_403_C6004"
0x9c5  ldarg.0
0x9c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cb  ldstr    aSearchwidgetPa_0// "SearchWidget.Parature.InvalidAccountId."...
0x9d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d5  ldc.i4.0
0x9d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9db  ldarg.0
0x9dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e1  ldstr    aLocidKmwallPar_3// "LOCID_KMWALL_PARATURE_403_C6009"
0x9e6  ldarg.0
0x9e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ec  ldstr    aSearchwidgetSe_1// "SearchWidget.SetupWizard.NonWhiteListed"...
0x9f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9f6  ldc.i4.0
0x9f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9fc  ldarg.0
0x9fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa02  ldstr    aLocidKmwallPar_4// "LOCID_KMWALL_PARATURE_400_B6007"
0xa07  ldarg.0
0xa08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa0d  ldstr    aSearchwidgetPa_1// "SearchWidget.Parature.PerminssionError."...
0xa12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa17  ldc.i4.0
0xa18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa1d  ldarg.0
0xa1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa23  ldstr    aLocidKmwallPar_5// "LOCID_KMWALL_PARATURE_500_C5000"
0xa28  ldarg.0
0xa29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa2e  ldstr    aSearchwidgetSe_2// "SearchWidget.SetupWizard.Parature.Inter"...
0xa33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa38  ldc.i4.0
0xa39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa3e  ldarg.0
0xa3f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa44  ldstr    aLocidKmwallPar_6// "LOCID_KMWALL_PARATURE_501_D6007"
0xa49  ldarg.0
0xa4a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa4f  ldstr    aSearchwidgetPa_2// "SearchWidget.Parature.NotImplemented.50"...
0xa54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa59  ldc.i4.0
0xa5a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa5f  ldarg.0
0xa60  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa65  ldstr    aKnowledgemanag// "KnowledgeManagementWebService"
0xa6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xa6f  ret
```
