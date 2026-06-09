# Microsoft.Crm.Web.Pages.MultiEntitySearchPage::ConfigureHeader

- ea: `0x3a030`
- end: `0x3a293`
- name: `Microsoft.Crm.Web.Pages.MultiEntitySearchPage::ConfigureHeader`
- size: `611`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x3a202`: `Button_Create`
- `0x3a08f`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0x3a099`: `QuickCreateSaveButtonText`
- `0x3a0af`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0x3a0b9`: `QuickCreateCancelButtonText`
- `0x3a06f`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0x3a079`: `RefreshForm_CloseGlobalQuickCreate`
- `0x3a0cf`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0x3a0d9`: `QuickCreate_TitlePrefix`
- `0x3a194`: `LOCID_QUICKCREATE_VIEWRECORD`
- `0x3a1b5`: `LOCID_QUICKCREATE_CREATEANOTHER`
- `0x3a1c0`: `Web.NavBar.QC_CreateAnother`
- `0x3a1f7`: `LOCID_QUICKCREATE`
- `0x3a265`: `Search_QuickCreate_AddButton_Meqf`
- `0x3a110`: `LOCID_MEQF_TASK`
- `0x3a11b`: `Web.Tools.personalsettings.dialogs.personalsettings.UseCrmFormForTaskLabel`

## pseudocode

```c

```

## disassembly

```asm
0x3a030  ldarg.0
0x3a031  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a036  ldc.i4.1
0x3a037  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x3a03c  ldarg.0
0x3a03d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a042  ldc.i4.1
0x3a043  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x3a048  ldarg.0
0x3a049  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a04e  ldstr    aLocidMeqfMinCh// "LOCID_MEQF_MIN_CHARACTER_SEARCH"
0x3a053  ldarg.0
0x3a054  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a059  ldstr    aSearchNoresult// "Search_Noresults_Message"
0x3a05e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a063  ldc.i4.0
0x3a064  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a069  ldarg.0
0x3a06a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a06f  ldstr    aLocidCloseGlob// "LOCID_CLOSE_GLOBAL_QUICKCREATE"
0x3a074  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a079  ldstr    aRefreshformClo// "RefreshForm_CloseGlobalQuickCreate"
0x3a07e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a083  ldc.i4.0
0x3a084  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a089  ldarg.0
0x3a08a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a08f  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0x3a094  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a099  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0x3a09e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a0a3  ldc.i4.0
0x3a0a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a0a9  ldarg.0
0x3a0aa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a0af  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0x3a0b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a0b9  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0x3a0be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a0c3  ldc.i4.0
0x3a0c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a0c9  ldarg.0
0x3a0ca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a0cf  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0x3a0d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a0d9  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0x3a0de  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a0e3  ldc.i4.0
0x3a0e4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a0e9  ldarg.0
0x3a0ea  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a0ef  ldstr    aLocidMeqfPhone// "LOCID_MEQF_PHONECALL"
0x3a0f4  ldarg.0
0x3a0f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a0fa  ldstr    aMaMenuitemPhon// "MA_MenuItem_PhoneCall"
0x3a0ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a104  ldc.i4.0
0x3a105  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a10a  ldarg.0
0x3a10b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a110  ldstr    aLocidMeqfTask// "LOCID_MEQF_TASK"
0x3a115  ldarg.0
0x3a116  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a11b  ldstr    aWebToolsPerson// "Web.Tools.personalsettings.dialogs.pers"...
0x3a120  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a125  ldc.i4.0
0x3a126  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a12b  ldarg.0
0x3a12c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a131  ldstr    aLocidMeqfEmail// "LOCID_MEQF_EMAIL"
0x3a136  ldarg.0
0x3a137  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a13c  ldstr    aMaMenuitemEmai// "MA_MenuItem_Email"
0x3a141  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a146  ldc.i4.0
0x3a147  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a14c  ldarg.0
0x3a14d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a152  ldstr    aLocidMeqfAppoi// "LOCID_MEQF_APPOINTMENT"
0x3a157  ldarg.0
0x3a158  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a15d  ldstr    aMaMenuitemAppo// "MA_MenuItem_Appointment"
0x3a162  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a167  ldc.i4.0
0x3a168  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a16d  ldarg.0
0x3a16e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a173  ldstr    aLocidMeqfAttri// "LOCID_MEQF_ATTRIBUTE_DEFAULT"
0x3a178  ldarg.0
0x3a179  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a17e  ldstr    aNullattributed// "NullAttributeDefaultValue"
0x3a183  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a188  ldc.i4.0
0x3a189  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a18e  ldarg.0
0x3a18f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a194  ldstr    aLocidQuickcrea// "LOCID_QUICKCREATE_VIEWRECORD"
0x3a199  ldarg.0
0x3a19a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a19f  ldstr    aWebNavbarQcVie// "Web.NavBar.QC_ViewRecord"
0x3a1a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a1a9  ldc.i4.0
0x3a1aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a1af  ldarg.0
0x3a1b0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a1b5  ldstr    aLocidQuickcrea_0// "LOCID_QUICKCREATE_CREATEANOTHER"
0x3a1ba  ldarg.0
0x3a1bb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a1c0  ldstr    aWebNavbarQcCre// "Web.NavBar.QC_CreateAnother"
0x3a1c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a1ca  ldc.i4.0
0x3a1cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a1d0  ldarg.0
0x3a1d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a1d6  ldstr    aLocidSuccessSa// "LOCID_SUCCESS_SAVE_QUICKFORM"
0x3a1db  ldarg.0
0x3a1dc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a1e1  ldstr    aSuccessSaveQui// "Success_Save_QuickForm"
0x3a1e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a1eb  ldc.i4.0
0x3a1ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a1f1  ldarg.0
0x3a1f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a1f7  ldstr    aLocidQuickcrea_1// "LOCID_QUICKCREATE"
0x3a1fc  ldarg.0
0x3a1fd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a202  ldstr    aButtonCreate// "Button_Create"
0x3a207  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a20c  ldc.i4.0
0x3a20d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a212  ldarg.0
0x3a213  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a218  ldstr    aLocidMeqfMaxre// "LOCID_MEQF_MAXRECORD_EXCEED"
0x3a21d  ldarg.0
0x3a21e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a223  ldstr    aSearchMaxcount// "Search_MaxCountExceedResult_Label_Meqf"
0x3a228  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a22d  ldc.i4.0
0x3a22e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a233  ldarg.0
0x3a234  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a239  ldstr    aLocidMeqfAdd// "LOCID_MEQF_ADD"
0x3a23e  ldarg.0
0x3a23f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a244  ldstr    aFormLibrariesA// "Form_Libraries_And_Event_Handler_Contro"...
0x3a249  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a24e  ldc.i4.0
0x3a24f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a254  ldarg.0
0x3a255  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a25a  ldstr    aLocidMeqfRecor// "LOCID_MEQF_RECORD"
0x3a25f  ldarg.0
0x3a260  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a265  ldstr    aSearchQuickcre// "Search_QuickCreate_AddButton_Meqf"
0x3a26a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a26f  ldc.i4.0
0x3a270  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3a275  ldarg.0
0x3a276  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3a27b  ldstr    aHighcontrasten_0// "HighContrastEnabled"
0x3a280  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3a285  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x3a28a  ldc.i4.0
0x3a28b  ceq
0x3a28d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x3a292  ret
```
