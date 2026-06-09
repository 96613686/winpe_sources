# Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigurePage

- ea: `0x80`
- end: `0x24f`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigurePage`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## string_xrefs

- `0x136`: `Web.Tools.DocumentManagement.SettingsPage.WarningMessage.PageExtension`

## pseudocode

```c

```

## disassembly

```asm
0x80  ldarg.0
0x81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x86  ldstr    aLocidDocmNoent// "LOCID_DOCM_NOENTITY_SELECTED"
0x8b  ldarg.0
0x8c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91  ldstr    aWebToolsKnowle// "Web.Tools.KnowledgeManagement.SettingsP"...
0x96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9b  ldc.i4.0
0x9c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa1  ldarg.0
0xa2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa7  ldstr    aLocidKmSiteurl// "LOCID_KM_SITEURL_GRAYTEXT"
0xac  ldarg.0
0xad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb2  ldstr    aWebToolsKnowle_0// "Web.Tools.KnowledgeManagement.SettingsP"...
0xb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbc  ldc.i4.0
0xbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc2  ldarg.0
0xc3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc8  ldstr    aLocidKmAccount// "LOCID_KM_ACCOUNT_GRAYTEXT"
0xcd  ldarg.0
0xce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd3  ldstr    aWebToolsKnowle_1// "Web.Tools.KnowledgeManagement.SettingsP"...
0xd8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdd  ldc.i4.0
0xde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3  ldarg.0
0xe4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe9  ldstr    aLocidKmDepartm// "LOCID_KM_DEPARTMENT_GRAYTEXT"
0xee  ldarg.0
0xef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf4  ldstr    aWebToolsKnowle_2// "Web.Tools.KnowledgeManagement.SettingsP"...
0xf9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfe  ldc.i4.0
0xff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x104  ldarg.0
0x105  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10a  ldstr    aLocidDocmCrmht// "LOCID_DOCM_CRMHTTPS_SPHTTP"
0x10f  ldarg.0
0x110  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x115  ldstr    aWebToolsDocume// "Web.Tools.DocumentManagement.SettingsPa"...
0x11a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11f  ldc.i4.0
0x120  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x125  ldarg.0
0x126  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12b  ldstr    aLocidDocmUrlca// "LOCID_DOCM_URLCANNOTBEPAGE"
0x130  ldarg.0
0x131  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x136  ldstr    aWebToolsDocume_0// "Web.Tools.DocumentManagement.SettingsPa"...
0x13b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x140  ldc.i4.0
0x141  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x146  ldarg.0
0x147  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14c  ldstr    aLocidDocmLocal// "LOCID_DOCM_LOCALHOST_URL"
0x151  ldarg.0
0x152  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x157  ldstr    aWebToolsDocume_1// "Web.Tools.DocumentManagement.SettingsPa"...
0x15c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x161  ldc.i4.0
0x162  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x167  ldarg.0
0x168  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16d  ldstr    aLocidKmAccount_0// "LOCID_KM_ACCOUNT_ALPHANUM"
0x172  ldarg.0
0x173  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x178  ldstr    aWebToolsKnowle_3// "Web.Tools.KnowledgeManagement.SettingsP"...
0x17d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x182  ldc.i4.0
0x183  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x188  ldarg.0
0x189  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x18e  ldstr    aLocidKmDepartm_0// "LOCID_KM_DEPARTMENT_ALPHANUM"
0x193  ldarg.0
0x194  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x199  ldstr    aWebToolsKnowle_4// "Web.Tools.KnowledgeManagement.SettingsP"...
0x19e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a3  ldc.i4.0
0x1a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1a9  ldarg.0
0x1aa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1af  ldstr    aLocidKmSupport// "LOCID_KM_SUPPORTURL_GRAYTEXT"
0x1b4  ldarg.0
0x1b5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1ba  ldstr    aWebToolsKnowle_5// "Web.Tools.KnowledgeManagement.SettingsP"...
0x1bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c4  ldc.i4.0
0x1c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1ca  ldarg.0
0x1cb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1d0  ldstr    aLocidKmNativec// "LOCID_KM_NATIVECRMURL_GRAYTEXT"
0x1d5  ldarg.0
0x1d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1db  ldstr    aWebToolsKnowle_6// "Web.Tools.KnowledgeManagement.SettingsP"...
0x1e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e5  ldc.i4.0
0x1e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1eb  ldarg.0
0x1ec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1f1  ldstr    aLocidParaturei// "LOCID_PARATUREINSTANCE_ERROR"
0x1f6  ldarg.0
0x1f7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fc  ldstr    aWebToolsKnowle_7// "Web.Tools.KnowledgeManagement.SettingsP"...
0x201  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x206  ldc.i4.0
0x207  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x20c  ldarg.0
0x20d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x212  ldstr    aLocidResetConf// "LOCID_RESET_CONFORMATIONTEXT"
0x217  ldarg.0
0x218  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x21d  ldstr    aWebToolsKnowle_8// "Web.Tools.KnowledgeManagement.SettingsP"...
0x222  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x227  ldc.i4.0
0x228  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x22d  ldarg.0
0x22e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x233  ldstr    aLocidDocmReset// "LOCID_DOCM_RESETERROR"
0x238  ldarg.0
0x239  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23e  ldstr    aWebToolsKnowle_9// "Web.Tools.KnowledgeManagement.SettingsP"...
0x243  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x248  ldc.i4.0
0x249  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x24e  ret
```
