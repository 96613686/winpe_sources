# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticlesEntityPageHandler::ConfigurePageHandler

- ea: `0xdcd0`
- end: `0xe10d`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticlesEntityPageHandler::ConfigurePageHandler`
- size: `1085`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xdcd0`

## string_xrefs

- `0xdd4e`: `/_static/_common/scripts/stage.js`
- `0xdcfe`: `/_common/styles/select.css.aspx`
- `0xdd8e`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xdd0e`: `/_common/styles/griddock.css.aspx`
- `0xe085`: `_bCanDelete`
- `0xe0a4`: `_bCanWrite`

## pseudocode

```c

```

## disassembly

```asm
0xdcd0  ldarg.0
0xdcd1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdcd6  ldc.i4.1
0xdcd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xdcdc  ldarg.0
0xdcdd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdce2  ldc.i4.1
0xdce3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0xdce8  ldarg.0
0xdce9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdcee  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xdcf3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdcf8  ldarg.0
0xdcf9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdcfe  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xdd03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdd08  ldarg.0
0xdd09  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd0e  ldstr    aCommonStylesGr// "/_common/styles/griddock.css.aspx"
0xdd13  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdd18  ldarg.0
0xdd19  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd1e  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0xdd23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdd28  ldarg.0
0xdd29  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd2e  ldstr    aStaticCsFolder// "/_static/cs/folders.js"
0xdd33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd38  ldarg.0
0xdd39  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd3e  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0xdd43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd48  ldarg.0
0xdd49  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd4e  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0xdd53  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd58  ldarg.0
0xdd59  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd5e  ldstr    aStaticCsKbarti// "/_static/cs/kbarticles/KbArticles.js"
0xdd63  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd68  ldarg.0
0xdd69  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd6e  ldstr    aStaticCsArticl// "/_static/CS/ArticleSearchRibbon/Article"...
0xdd73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd78  ldarg.0
0xdd79  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd7e  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xdd83  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd88  ldarg.0
0xdd89  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd8e  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/jquery_ui_1.8."...
0xdd93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdd98  ldarg.0
0xdd99  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdd9e  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xdda3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdda8  ldarg.0
0xdda9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xddae  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0xddb3  ldarg.0
0xddb4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xddb9  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0xddbe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xddc3  ldc.i4.0
0xddc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xddc9  ldarg.0
0xddca  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xddcf  ldstr    aLocidFullTextS// "LOCID_FULL_TEXT_SEACRH_LABEL"
0xddd4  ldarg.0
0xddd5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xddda  ldstr    aRibbonArticles// "Ribbon.ArticleSearchTab.SearchOption.Fu"...
0xdddf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdde4  ldc.i4.0
0xdde5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xddea  ldarg.0
0xddeb  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xddf0  ldstr    aLocidFullTextS_0// "LOCID_FULL_TEXT_SEACRH_TOOLTIP"
0xddf5  ldarg.0
0xddf6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xddfb  ldstr    aRibbonArticles_0// "Ribbon.ArticleSearchTab.SearchOption.Fu"...
0xde00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde05  ldc.i4.0
0xde06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xde0b  ldarg.0
0xde0c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xde11  ldstr    aLocidKeywordSe// "LOCID_KEYWORD_SEACRH_LABEL"
0xde16  ldarg.0
0xde17  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xde1c  ldstr    aRibbonArticles_1// "Ribbon.ArticleSearchTab.SearchOption.Ke"...
0xde21  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde26  ldc.i4.0
0xde27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xde2c  ldarg.0
0xde2d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xde32  ldstr    aLocidKeywordSe_0// "LOCID_KEYWORD_SEACRH_TOOLTIP"
0xde37  ldarg.0
0xde38  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xde3d  ldstr    aRibbonArticles_2// "Ribbon.ArticleSearchTab.SearchOption.Ke"...
0xde42  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde47  ldc.i4.0
0xde48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xde4d  ldarg.0
0xde4e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xde53  ldstr    aLocidTitleSeac// "LOCID_TITLE_SEACRH_LABEL"
0xde58  ldarg.0
0xde59  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xde5e  ldstr    aRibbonArticles_3// "Ribbon.ArticleSearchTab.SearchOption.Ti"...
0xde63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde68  ldc.i4.0
0xde69  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xde6e  ldarg.0
0xde6f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xde74  ldstr    aLocidTitleSeac_0// "LOCID_TITLE_SEACRH_TOOLTIP"
0xde79  ldarg.0
0xde7a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xde7f  ldstr    aRibbonArticles_4// "Ribbon.ArticleSearchTab.SearchOption.Ti"...
0xde84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde89  ldc.i4.0
0xde8a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xde8f  ldarg.0
0xde90  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xde95  ldstr    aLocidSubjectSe// "LOCID_SUBJECT_SEACRH_LABEL"
0xde9a  ldarg.0
0xde9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdea0  ldstr    aRibbonArticles_5// "Ribbon.ArticleSearchTab.SearchOption.Su"...
0xdea5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdeaa  ldc.i4.0
0xdeab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdeb0  ldarg.0
0xdeb1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdeb6  ldstr    aLocidSubjectSe_0// "LOCID_SUBJECT_SEACRH_TOOLTIP"
0xdebb  ldarg.0
0xdebc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdec1  ldstr    aRibbonArticles_6// "Ribbon.ArticleSearchTab.SearchOption.Su"...
0xdec6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdecb  ldc.i4.0
0xdecc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xded1  ldarg.0
0xded2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xded7  ldstr    aLocidArtNumber// "LOCID_ART_NUMBER_SEACRH_LABEL"
0xdedc  ldarg.0
0xdedd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdee2  ldstr    aRibbonArticles_7// "Ribbon.ArticleSearchTab.SearchOption.Ar"...
0xdee7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdeec  ldc.i4.0
0xdeed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdef2  ldarg.0
0xdef3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdef8  ldstr    aLocidArtNumber_0// "LOCID_ART_NUMBER_SEACRH_TOOLTIP"
0xdefd  ldarg.0
0xdefe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdf03  ldstr    aRibbonArticles_8// "Ribbon.ArticleSearchTab.SearchOption.Ar"...
0xdf08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf0d  ldc.i4.0
0xdf0e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdf13  ldarg.0
0xdf14  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdf19  ldstr    aLocidSubjectVa// "LOCID_SUBJECT_VALUE_LABEL"
0xdf1e  ldarg.0
0xdf1f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdf24  ldstr    aRibbonArticles_9// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xdf29  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf2e  ldc.i4.0
0xdf2f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdf34  ldarg.0
0xdf35  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdf3a  ldstr    aLocidSubjectVa_0// "LOCID_SUBJECT_VALUE_NONE"
0xdf3f  ldarg.0
0xdf40  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdf45  ldstr    aRibbonArticles_10// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xdf4a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf4f  ldc.i4.0
0xdf50  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdf55  ldarg.0
0xdf56  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdf5b  ldstr    aLocidSubjectVa_1// "LOCID_SUBJECT_VALUE_TOOLTIP"
0xdf60  ldarg.0
0xdf61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdf66  ldstr    aRibbonArticles_11// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xdf6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf70  ldc.i4.0
0xdf71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdf76  ldarg.0
0xdf77  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdf7c  ldstr    aLocidExactWord// "LOCID_EXACT_WORDS_LABEL"
0xdf81  ldarg.0
0xdf82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdf87  ldstr    aRibbonArticles_12// "Ribbon.ArticleSearchTab.SearchType.Exac"...
0xdf8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf91  ldc.i4.0
0xdf92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdf97  ldarg.0
0xdf98  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdf9d  ldstr    aLocidExactWord_0// "LOCID_EXACT_WORDS_TOOLTIP"
0xdfa2  ldarg.0
0xdfa3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdfa8  ldstr    aRibbonArticles_13// "Ribbon.ArticleSearchTab.SearchType.Exac"...
0xdfad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdfb2  ldc.i4.0
0xdfb3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdfb8  ldarg.0
0xdfb9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdfbe  ldstr    aLocidUseLikeWo// "LOCID_USE_LIKE_WORDS_LABEL"
0xdfc3  ldarg.0
0xdfc4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdfc9  ldstr    aRibbonArticles_14// "Ribbon.ArticleSearchTab.SearchType.UseL"...
0xdfce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdfd3  ldc.i4.0
0xdfd4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdfd9  ldarg.0
0xdfda  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xdfdf  ldstr    aLocidUseLikeWo_0// "LOCID_USE_LIKE_WORDS_TOOLTIP"
0xdfe4  ldarg.0
0xdfe5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0xdfea  ldstr    aRibbonArticles_15// "Ribbon.ArticleSearchTab.SearchType.UseL"...
0xdfef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdff4  ldc.i4.0
0xdff5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdffa  ldarg.0
0xdffb  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe000  ldstr    aKbIsoffline// "KB_ISOFFLINE"
0xe005  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xe00a  brfalse.s loc_E013
0xe00c  ldstr    aKeywordsearch// "KeywordSearch"
0xe011  br.s     loc_E018
0xe013  ldstr    aFulltextsearch// "FullTextSearch"
0xe018  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe01d  ldarg.0
0xe01e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe023  ldstr    aShowArticleSea// "SHOW_ARTICLE_SEACRH_MENU"
0xe028  ldc.i4.1
0xe029  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe02e  ldarg.0
0xe02f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe034  ldc.i4   0x400
0xe039  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xe03e  ldarg.0
0xe03f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe044  ldc.i4   0x800
0xe049  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xe04e  ldarg.0
0xe04f  ldstr    aKbarticle// "kbarticle"
0xe054  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe059  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe05e  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xe063  ldarg.0
0xe064  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe069  ldstr    aIobjtype_0// "_iObjType"
0xe06e  ldarg.0
0xe06f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentType()
0xe074  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xe079  conv.i8
0xe07a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xe07f  ldarg.0
0xe080  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe085  ldstr    aBcandelete// "_bCanDelete"
0xe08a  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteArticle()
0xe08f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe094  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe099  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe09e  ldarg.0
0xe09f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe0a4  ldstr    aBcanwrite// "_bCanWrite"
0xe0a9  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteArticle()
0xe0ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe0b3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe0b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe0bd  ldarg.0
0xe0be  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe0c3  ldstr    aBcanpublish// "_bCanPublish"
0xe0c8  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_PublishArticle()
0xe0cd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe0d2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe0d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe0dc  ldarg.0
0xe0dd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe0e2  ldstr    aCurrenttypecod// "_currentTypeCode"
0xe0e7  ldstr    aManagekb// "managekb"
0xe0ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe0f1  ldarg.0
0xe0f2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentHeader()
0xe0f7  ldstr    aIndexedarticle// "IndexedArticleViewID"
0xe0fc  ldstr    a7ad58fad40af4e// "{7AD58FAD-40AF-4E72-AC4E-DB8C82E1E62D}"
0xe101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe106  ldarg.0
0xe107  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::ConfigurePageHandler()
0xe10c  ret
```
