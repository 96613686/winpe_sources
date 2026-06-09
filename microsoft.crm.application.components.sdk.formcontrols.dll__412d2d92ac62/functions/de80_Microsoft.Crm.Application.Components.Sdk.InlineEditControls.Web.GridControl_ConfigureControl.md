# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigureControl

- ea: `0xde80`
- end: `0xe39d`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigureControl`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0xde80`
- `0xe430`
- `0xe490`
- `0x1cb30`
- `0x1cde0`
- `0x1d030`
- `0x1d330`
- `0x1dda0`

## string_xrefs

- `0xdfb2`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xe049`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xdfc2`: `/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0xdea4`: `IsQuickCreateEnabled`
- `0xdf20`: `IsQuickCreateEnabled`
- `0xdf72`: `/_common/styles/global.css.aspx`
- `0xdf92`: `/_forms/styles/read.css.aspx`
- `0xe2fd`: `_bCanDelete`
- `0xe31c`: `_bCanWrite`

## pseudocode

```c

```

## disassembly

```asm
0xde80  ldarg.0
0xde81  ldc.i4.1
0xde82  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_IsLiteSubGrid(bool value)
0xde87  ldarg.0
0xde88  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureControl()
0xde8d  ldarg.0
0xde8e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::IsCardControl()
0xde93  brfalse.s loc_DE96
0xde95  ret
0xde96  ldarg.0
0xde97  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::get_ShowGlobalQuickCreate()
0xde9c  brfalse.s loc_DF1A
0xde9e  ldarg.0
0xde9f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0xdea4  ldstr    aIsquickcreatee// "IsQuickCreateEnabled"
0xdea9  ldstr    a1_0// "1"
0xdeae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xdeb3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdeb8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdebd  ldarg.0
0xdebe  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xdec3  ldc.i4.1
0xdec4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xdec9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xdece  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xded3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.GlobalQuickCreateTimestampProvider::GetTimestampsForQuickCreate(int32, class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx)
0xded8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0xdedd  stloc.0
0xdede  br.s     loc_DF01
0xdee0  ldloca.s 0
0xdee2  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0xdee7  stloc.1
0xdee8  ldarg.0
0xdee9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0xdeee  ldloca.s 1
0xdef0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xdef5  ldloca.s 1
0xdef7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xdefc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xdf01  ldloca.s 0
0xdf03  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0xdf08  brtrue.s loc_DEE0
0xdf0a  leave.s  loc_DF2F
0xdf0c  ldloca.s 0
0xdf0e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0xdf14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf19  endfinally
0xdf1a  ldarg.0
0xdf1b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0xdf20  ldstr    aIsquickcreatee// "IsQuickCreateEnabled"
0xdf25  ldstr    a0// "0"
0xdf2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xdf2f  ldarg.0
0xdf30  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xdf35  ldstr    aActivitypointe_1// "activitypointer"
0xdf3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdf3f  brfalse  loc_DFD6
0xdf44  ldarg.0
0xdf45  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf4a  ldc.i4.1
0xdf4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xdf50  ldarg.0
0xdf51  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf56  ldc.i4.1
0xdf57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0xdf5c  ldarg.0
0xdf5d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf62  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xdf67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdf6c  ldarg.0
0xdf6d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf72  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0xdf77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdf7c  ldarg.0
0xdf7d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf82  ldstr    aStaticControls_2// "/_static/_controls/activitycontainer/ac"...
0xdf87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdf8c  ldarg.0
0xdf8d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdf92  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0xdf97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdf9c  ldarg.0
0xdf9d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdfa2  ldstr    aStaticControls_9// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xdfa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdfac  ldarg.0
0xdfad  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdfb2  ldstr    aStaticCommonSc// "/_static/_common/scripts/jquery_ui_1.8."...
0xdfb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdfbc  ldarg.0
0xdfbd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdfc2  ldstr    aStaticControls_1// "/_static/_controls/ActivityContainer/Ac"...
0xdfc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdfcc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdfd1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xdfd6  ldarg.0
0xdfd7  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xdfdc  ldstr    aBulkoperation// "bulkoperation"
0xdfe1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfe6  brfalse.s loc_E002
0xdfe8  ldarg.0
0xdfe9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xdfee  ldstr    aStaticMaListsL// "/_static/ma/lists/list.js"
0xdff3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdff8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdffd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xe002  ldarg.0
0xe003  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xe008  ldstr    aKbarticle// "kbarticle"
0xe00d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe012  brfalse  loc_E391
0xe017  ldarg.0
0xe018  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe01d  ldc.i4.1
0xe01e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xe023  ldarg.0
0xe024  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe029  ldstr    aStaticCsArticl// "/_static/CS/ArticleSearchRibbon/Article"...
0xe02e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe033  ldarg.0
0xe034  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe039  ldstr    aStaticControls_9// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xe03e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe043  ldarg.0
0xe044  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe049  ldstr    aStaticCommonSc// "/_static/_common/scripts/jquery_ui_1.8."...
0xe04e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe053  ldarg.0
0xe054  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe059  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xe05e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe063  ldarg.0
0xe064  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe069  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0xe06e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe073  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0xe078  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe07d  ldc.i4.0
0xe07e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe083  ldarg.0
0xe084  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe089  ldstr    aLocidFullTextS// "LOCID_FULL_TEXT_SEACRH_LABEL"
0xe08e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe093  ldstr    aRibbonArticles// "Ribbon.ArticleSearchTab.SearchOption.Fu"...
0xe098  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe09d  ldc.i4.0
0xe09e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe0a3  ldarg.0
0xe0a4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe0a9  ldstr    aLocidFullTextS_0// "LOCID_FULL_TEXT_SEACRH_TOOLTIP"
0xe0ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe0b3  ldstr    aRibbonArticles_0// "Ribbon.ArticleSearchTab.SearchOption.Fu"...
0xe0b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe0bd  ldc.i4.0
0xe0be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe0c3  ldarg.0
0xe0c4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe0c9  ldstr    aLocidKeywordSe// "LOCID_KEYWORD_SEACRH_LABEL"
0xe0ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe0d3  ldstr    aRibbonArticles_1// "Ribbon.ArticleSearchTab.SearchOption.Ke"...
0xe0d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe0dd  ldc.i4.0
0xe0de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe0e3  ldarg.0
0xe0e4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe0e9  ldstr    aLocidKeywordSe_0// "LOCID_KEYWORD_SEACRH_TOOLTIP"
0xe0ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe0f3  ldstr    aRibbonArticles_2// "Ribbon.ArticleSearchTab.SearchOption.Ke"...
0xe0f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe0fd  ldc.i4.0
0xe0fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe103  ldarg.0
0xe104  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe109  ldstr    aLocidTitleSeac// "LOCID_TITLE_SEACRH_LABEL"
0xe10e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe113  ldstr    aRibbonArticles_3// "Ribbon.ArticleSearchTab.SearchOption.Ti"...
0xe118  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe11d  ldc.i4.0
0xe11e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe123  ldarg.0
0xe124  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe129  ldstr    aLocidTitleSeac_0// "LOCID_TITLE_SEACRH_TOOLTIP"
0xe12e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe133  ldstr    aRibbonArticles_4// "Ribbon.ArticleSearchTab.SearchOption.Ti"...
0xe138  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe13d  ldc.i4.0
0xe13e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe143  ldarg.0
0xe144  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe149  ldstr    aLocidSubjectSe// "LOCID_SUBJECT_SEACRH_LABEL"
0xe14e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe153  ldstr    aRibbonArticles_5// "Ribbon.ArticleSearchTab.SearchOption.Su"...
0xe158  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe15d  ldc.i4.0
0xe15e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe163  ldarg.0
0xe164  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe169  ldstr    aLocidSubjectSe_0// "LOCID_SUBJECT_SEACRH_TOOLTIP"
0xe16e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe173  ldstr    aRibbonArticles_6// "Ribbon.ArticleSearchTab.SearchOption.Su"...
0xe178  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe17d  ldc.i4.0
0xe17e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe183  ldarg.0
0xe184  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe189  ldstr    aLocidArtNumber// "LOCID_ART_NUMBER_SEACRH_LABEL"
0xe18e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe193  ldstr    aRibbonArticles_7// "Ribbon.ArticleSearchTab.SearchOption.Ar"...
0xe198  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe19d  ldc.i4.0
0xe19e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe1a3  ldarg.0
0xe1a4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe1a9  ldstr    aLocidArtNumber_0// "LOCID_ART_NUMBER_SEACRH_TOOLTIP"
0xe1ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe1b3  ldstr    aRibbonArticles_8// "Ribbon.ArticleSearchTab.SearchOption.Ar"...
0xe1b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe1bd  ldc.i4.0
0xe1be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe1c3  ldarg.0
0xe1c4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe1c9  ldstr    aLocidSubjectVa// "LOCID_SUBJECT_VALUE_LABEL"
0xe1ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe1d3  ldstr    aRibbonArticles_9// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xe1d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe1dd  ldc.i4.0
0xe1de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe1e3  ldarg.0
0xe1e4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe1e9  ldstr    aLocidSubjectVa_0// "LOCID_SUBJECT_VALUE_NONE"
0xe1ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe1f3  ldstr    aRibbonArticles_10// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xe1f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe1fd  ldc.i4.0
0xe1fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe203  ldarg.0
0xe204  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe209  ldstr    aLocidSubjectVa_1// "LOCID_SUBJECT_VALUE_TOOLTIP"
0xe20e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe213  ldstr    aRibbonArticles_11// "Ribbon.ArticleSearchTab.SubjectValue.Su"...
0xe218  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe21d  ldc.i4.0
0xe21e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe223  ldarg.0
0xe224  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe229  ldstr    aLocidExactWord// "LOCID_EXACT_WORDS_LABEL"
0xe22e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe233  ldstr    aRibbonArticles_12// "Ribbon.ArticleSearchTab.SearchType.Exac"...
0xe238  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe23d  ldc.i4.0
0xe23e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe243  ldarg.0
0xe244  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe249  ldstr    aLocidExactWord_0// "LOCID_EXACT_WORDS_TOOLTIP"
0xe24e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe253  ldstr    aRibbonArticles_13// "Ribbon.ArticleSearchTab.SearchType.Exac"...
0xe258  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe25d  ldc.i4.0
0xe25e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe263  ldarg.0
0xe264  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe269  ldstr    aLocidUseLikeWo// "LOCID_USE_LIKE_WORDS_LABEL"
0xe26e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe273  ldstr    aRibbonArticles_14// "Ribbon.ArticleSearchTab.SearchType.UseL"...
0xe278  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe27d  ldc.i4.0
0xe27e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe283  ldarg.0
0xe284  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe289  ldstr    aLocidUseLikeWo_0// "LOCID_USE_LIKE_WORDS_TOOLTIP"
0xe28e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe293  ldstr    aRibbonArticles_15// "Ribbon.ArticleSearchTab.SearchType.UseL"...
0xe298  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe29d  ldc.i4.0
0xe29e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe2a3  ldarg.0
0xe2a4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe2a9  ldc.i4   0x400
0xe2ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xe2b3  ldarg.0
0xe2b4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe2b9  ldc.i4   0x800
0xe2be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xe2c3  ldarg.0
0xe2c4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe2c9  ldstr    aKbIsoffline// "KB_ISOFFLINE"
0xe2ce  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xe2d3  brfalse.s loc_E2DC
0xe2d5  ldstr    aKeywordsearch// "KeywordSearch"
0xe2da  br.s     loc_E2E1
0xe2dc  ldstr    aFulltextsearch// "FullTextSearch"
0xe2e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe2e6  ldarg.0
0xe2e7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe2ec  ldstr    aShowArticleSea// "SHOW_ARTICLE_SEACRH_MENU"
0xe2f1  ldc.i4.1
0xe2f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe2f7  ldarg.0
0xe2f8  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe2fd  ldstr    aBcandelete// "_bCanDelete"
  ... truncated ...
```
