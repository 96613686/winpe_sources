# Microsoft.Crm.Application.Controls.FormEditorBase::ConfigureHeader

- ea: `0x95440`
- end: `0x95627`
- name: `Microsoft.Crm.Application.Controls.FormEditorBase::ConfigureHeader`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8d1e0`
- `0x8d7b0`
- `0xab720`

## string_xrefs

- `0x95512`: `XML_LANGUAGE_NAME`
- `0x9560c`: `FormEditorWebService`
- `0x9561c`: `BusinessRulesWebService`

## pseudocode

```c

```

## disassembly

```asm
0x95440  ldarg.0
0x95441  call     instance void Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0x95446  ldarg.0
0x95447  ldarg.0
0x95448  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9544d  ldstr    aTooltipDisplay// "Tooltip_Display_Name"
0x95452  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95457  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::displayNameToolTip
0x9545c  ldarg.0
0x9545d  ldarg.0
0x9545e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95463  ldstr    aTooltipDataTyp// "Tooltip_Data_Type"
0x95468  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9546d  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::dataTypeToolTip
0x95472  ldarg.0
0x95473  ldarg.0
0x95474  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95479  ldstr    aTooltipSchemaN// "Tooltip_Schema_Name"
0x9547e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95483  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::schemaNameToolTip
0x95488  ldarg.0
0x95489  ldarg.0
0x9548a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9548f  ldstr    aSectionPrefix// "Section_Prefix"
0x95494  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95499  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::sectionPrefix
0x9549e  ldarg.0
0x9549f  ldarg.0
0x954a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x954a5  ldstr    aTabPrefix// "Tab_Prefix"
0x954aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x954af  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::tabPrefix
0x954b4  ldarg.0
0x954b5  ldarg.0
0x954b6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x954bb  ldstr    aSpacerCaption// "Spacer_Caption"
0x954c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x954c5  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::spacerCaption
0x954ca  ldarg.0
0x954cb  ldarg.0
0x954cc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x954d1  ldstr    aHeaderCaption// "Header_Caption"
0x954d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x954db  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::headerCaption
0x954e0  ldarg.0
0x954e1  ldarg.0
0x954e2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x954e7  ldstr    aFooterCaption// "Footer_Caption"
0x954ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x954f1  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::footerCaption
0x954f6  ldarg.0
0x954f7  ldarg.0
0x954f8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x954fd  ldstr    aAddcolumnCapti// "AddColumn_Caption"
0x95502  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95507  stfld    string Microsoft.Crm.Application.Controls.FormEditorBase::addColMessage
0x9550c  ldarg.0
0x9550d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95512  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0x95517  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9551c  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x95521  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x95526  ldarg.0
0x95527  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9552c  ldstr    aAddColMessage// "ADD_COL_MESSAGE"
0x95531  ldarg.0
0x95532  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::addColMessage
0x95537  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9553c  ldarg.0
0x9553d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95542  ldstr    aTooltipdisplay// "_toolTipDisplayName"
0x95547  ldarg.0
0x95548  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::displayNameToolTip
0x9554d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x95552  ldarg.0
0x95553  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95558  ldstr    aTooltipscheman// "_toolTipSchemaName"
0x9555d  ldarg.0
0x9555e  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::schemaNameToolTip
0x95563  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x95568  ldarg.0
0x95569  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9556e  ldstr    aTooltipdatatyp// "_toolTipDataType"
0x95573  ldarg.0
0x95574  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::dataTypeToolTip
0x95579  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9557e  ldarg.0
0x9557f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95584  ldstr    aSectionprefix// "_sectionPrefix"
0x95589  ldarg.0
0x9558a  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::sectionPrefix
0x9558f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x95594  ldarg.0
0x95595  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9559a  ldstr    aTabprefix// "_tabPrefix"
0x9559f  ldarg.0
0x955a0  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::tabPrefix
0x955a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x955aa  ldarg.0
0x955ab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x955b0  ldstr    aFootercaption// "_footerCaption"
0x955b5  ldarg.0
0x955b6  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::footerCaption
0x955bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x955c0  ldarg.0
0x955c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x955c6  ldstr    aHeadercaption// "_headerCaption"
0x955cb  ldarg.0
0x955cc  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::headerCaption
0x955d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x955d6  ldarg.0
0x955d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x955dc  ldstr    aSpacercaption// "_spacerCaption"
0x955e1  ldarg.0
0x955e2  ldfld    string Microsoft.Crm.Application.Controls.FormEditorBase::spacerCaption
0x955e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x955ec  ldarg.0
0x955ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x955f2  ldstr    aTwoletterlangu// "_twoletterlanguagename"
0x955f7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x955fc  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_TwoLetterISOLanguageName()
0x95601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x95606  ldarg.0
0x95607  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9560c  ldstr    aFormeditorwebs// "FormEditorWebService"
0x95611  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x95616  ldarg.0
0x95617  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9561c  ldstr    aBusinessrulesw// "BusinessRulesWebService"
0x95621  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x95626  ret
```
