# Microsoft.Crm.Web.Pages.ExternalSearchPage::ConfigureHeader

- ea: `0x39850`
- end: `0x39ab3`
- name: `Microsoft.Crm.Web.Pages.ExternalSearchPage::ConfigureHeader`
- size: `611`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x3999e`: `Button_Create`
- `0x398af`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0x398b9`: `QuickCreateSaveButtonText`
- `0x398cf`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0x398d9`: `QuickCreateCancelButtonText`
- `0x3988f`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0x39899`: `RefreshForm_CloseGlobalQuickCreate`
- `0x398ef`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0x398f9`: `QuickCreate_TitlePrefix`
- `0x39930`: `LOCID_QUICKCREATE_VIEWRECORD`
- `0x39951`: `LOCID_QUICKCREATE_CREATEANOTHER`
- `0x3995c`: `Web.NavBar.QC_CreateAnother`
- `0x39993`: `LOCID_QUICKCREATE`
- `0x39a01`: `Search_QuickCreate_AddButton_Meqf`
- `0x39a22`: `ExternalSearch_Service_Unavailable`
- `0x39a7a`: `LOCID_ES_ERROR_DURING_PAGING`

## pseudocode

```c

```

## disassembly

```asm
0x39850  ldarg.0
0x39851  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39856  ldc.i4.1
0x39857  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x3985c  ldarg.0
0x3985d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39862  ldc.i4.1
0x39863  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x39868  ldarg.0
0x39869  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3986e  ldstr    aLocidMeqfMinCh// "LOCID_MEQF_MIN_CHARACTER_SEARCH"
0x39873  ldarg.0
0x39874  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39879  ldstr    aSearchNoresult// "Search_Noresults_Message"
0x3987e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39883  ldc.i4.0
0x39884  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39889  ldarg.0
0x3988a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3988f  ldstr    aLocidCloseGlob// "LOCID_CLOSE_GLOBAL_QUICKCREATE"
0x39894  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x39899  ldstr    aRefreshformClo// "RefreshForm_CloseGlobalQuickCreate"
0x3989e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x398a3  ldc.i4.0
0x398a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x398a9  ldarg.0
0x398aa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x398af  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0x398b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398b9  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0x398be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x398c3  ldc.i4.0
0x398c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x398c9  ldarg.0
0x398ca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x398cf  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0x398d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398d9  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0x398de  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x398e3  ldc.i4.0
0x398e4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x398e9  ldarg.0
0x398ea  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x398ef  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0x398f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398f9  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0x398fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39903  ldc.i4.0
0x39904  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39909  ldarg.0
0x3990a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3990f  ldstr    aLocidMeqfAttri// "LOCID_MEQF_ATTRIBUTE_DEFAULT"
0x39914  ldarg.0
0x39915  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3991a  ldstr    aNullattributed// "NullAttributeDefaultValue"
0x3991f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39924  ldc.i4.0
0x39925  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3992a  ldarg.0
0x3992b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39930  ldstr    aLocidQuickcrea// "LOCID_QUICKCREATE_VIEWRECORD"
0x39935  ldarg.0
0x39936  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3993b  ldstr    aWebNavbarQcVie// "Web.NavBar.QC_ViewRecord"
0x39940  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39945  ldc.i4.0
0x39946  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3994b  ldarg.0
0x3994c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39951  ldstr    aLocidQuickcrea_0// "LOCID_QUICKCREATE_CREATEANOTHER"
0x39956  ldarg.0
0x39957  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3995c  ldstr    aWebNavbarQcCre// "Web.NavBar.QC_CreateAnother"
0x39961  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39966  ldc.i4.0
0x39967  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3996c  ldarg.0
0x3996d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39972  ldstr    aLocidSuccessSa// "LOCID_SUCCESS_SAVE_QUICKFORM"
0x39977  ldarg.0
0x39978  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3997d  ldstr    aSuccessSaveQui// "Success_Save_QuickForm"
0x39982  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39987  ldc.i4.0
0x39988  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3998d  ldarg.0
0x3998e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39993  ldstr    aLocidQuickcrea_1// "LOCID_QUICKCREATE"
0x39998  ldarg.0
0x39999  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3999e  ldstr    aButtonCreate// "Button_Create"
0x399a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x399a8  ldc.i4.0
0x399a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x399ae  ldarg.0
0x399af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x399b4  ldstr    aLocidMeqfMaxre// "LOCID_MEQF_MAXRECORD_EXCEED"
0x399b9  ldarg.0
0x399ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x399bf  ldstr    aSearchMaxcount// "Search_MaxCountExceedResult_Label_Meqf"
0x399c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x399c9  ldc.i4.0
0x399ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x399cf  ldarg.0
0x399d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x399d5  ldstr    aLocidMeqfAdd// "LOCID_MEQF_ADD"
0x399da  ldarg.0
0x399db  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x399e0  ldstr    aFormLibrariesA// "Form_Libraries_And_Event_Handler_Contro"...
0x399e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x399ea  ldc.i4.0
0x399eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x399f0  ldarg.0
0x399f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x399f6  ldstr    aLocidMeqfRecor// "LOCID_MEQF_RECORD"
0x399fb  ldarg.0
0x399fc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39a01  ldstr    aSearchQuickcre// "Search_QuickCreate_AddButton_Meqf"
0x39a06  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39a0b  ldc.i4.0
0x39a0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39a11  ldarg.0
0x39a12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39a17  ldstr    aLocidEsServerU// "LOCID_ES_SERVER_UNAVAILABLE"
0x39a1c  ldarg.0
0x39a1d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39a22  ldstr    aExternalsearch_2// "ExternalSearch_Service_Unavailable"
0x39a27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39a2c  ldc.i4.0
0x39a2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39a32  ldarg.0
0x39a33  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39a38  ldstr    aLocidEsServerU_0// "LOCID_ES_SERVER_UNEXPECTEDERROR"
0x39a3d  ldarg.0
0x39a3e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39a43  ldstr    aExternalsearch_3// "ExternalSearch_Unexpected_Error"
0x39a48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39a4d  ldc.i4.0
0x39a4e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39a53  ldarg.0
0x39a54  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39a59  ldstr    aLocidEsMoreRec// "LOCID_ES_MORE_RECORDS"
0x39a5e  ldarg.0
0x39a5f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39a64  ldstr    aExternalsearch_4// "ExternalSearch_More_Results"
0x39a69  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39a6e  ldc.i4.0
0x39a6f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39a74  ldarg.0
0x39a75  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39a7a  ldstr    aLocidEsErrorDu// "LOCID_ES_ERROR_DURING_PAGING"
0x39a7f  ldarg.0
0x39a80  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39a85  ldstr    aExternalsearch_5// "ExternalSearch_Exception_While_Paging"
0x39a8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39a8f  ldc.i4.0
0x39a90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x39a95  ldarg.0
0x39a96  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39a9b  ldstr    aHighcontrasten_0// "HighContrastEnabled"
0x39aa0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x39aa5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x39aaa  ldc.i4.0
0x39aab  ceq
0x39aad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x39ab2  ret
```
