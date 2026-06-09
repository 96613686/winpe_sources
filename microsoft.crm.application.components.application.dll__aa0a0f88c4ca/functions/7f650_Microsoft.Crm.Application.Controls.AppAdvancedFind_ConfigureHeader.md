# Microsoft.Crm.Application.Controls.AppAdvancedFind::ConfigureHeader

- ea: `0x7f650`
- end: `0x7f897`
- name: `Microsoft.Crm.Application.Controls.AppAdvancedFind::ConfigureHeader`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7d450`
- `0x7e150`
- `0x7e230`
- `0x7e260`
- `0x7f650`

## string_xrefs

- `0x7f7b8`: `XML_LANGUAGE_NAME`
- `0x7f7d2`: `/_static/_common/scripts/af_cnd_common.js`
- `0x7f802`: `/_static/advancedfind/cachemanager.js`

## pseudocode

```c

```

## disassembly

```asm
0x7f650  ldarg.0
0x7f651  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x7f656  ldarg.0
0x7f657  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x7f65c  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Controls.AppAdvancedFind::_textBoxUI
0x7f661  ldarg.0
0x7f662  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::.ctor()
0x7f667  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Controls.AppAdvancedFind::_lookupUI
0x7f66c  ldarg.0
0x7f66d  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI::.ctor()
0x7f672  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppAdvancedFind::_dateTimeUI
0x7f677  ldarg.0
0x7f678  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x7f67d  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppAdvancedFind::_selectUI
0x7f682  ldarg.0
0x7f683  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist::.ctor()
0x7f688  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Application.Controls.AppAdvancedFind::_multiPicklistUI
0x7f68d  ldarg.0
0x7f68e  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI::.ctor()
0x7f693  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI Microsoft.Crm.Application.Controls.AppAdvancedFind::_fiscalPeriodAndYearUI
0x7f698  ldarg.0
0x7f699  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::.ctor()
0x7f69e  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppAdvancedFind::_numberUI
0x7f6a3  ldarg.0
0x7f6a4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppAdvancedFind::_numberUI
0x7f6a9  ldc.i4.0
0x7f6aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x7f6af  ldarg.0
0x7f6b0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AppAdvancedFind::_sharedToolbar
0x7f6b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f6ba  ldarg.0
0x7f6bb  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityListVisible
0x7f6c0  brfalse.s loc_7F6CD
0x7f6c2  ldarg.0
0x7f6c3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppAdvancedFind::get_EntityList()
0x7f6c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f6cd  ldarg.0
0x7f6ce  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_queryListVisible
0x7f6d3  brfalse.s loc_7F6E0
0x7f6d5  ldarg.0
0x7f6d6  call     instance class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppAdvancedFind::get_QueryList()
0x7f6db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f6e0  ldarg.0
0x7f6e1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AppAdvancedFind::_detailedToolBar
0x7f6e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f6eb  ldarg.0
0x7f6ec  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AppAdvancedFind::_simpleToolBar
0x7f6f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f6f6  ldarg.0
0x7f6f7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppAdvancedFind::_selectUI
0x7f6fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f701  ldarg.0
0x7f702  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Controls.AppAdvancedFind::_lookupUI
0x7f707  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f70c  ldarg.0
0x7f70d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppAdvancedFind::_dateTimeUI
0x7f712  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f717  ldarg.0
0x7f718  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Controls.AppAdvancedFind::_textBoxUI
0x7f71d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f722  ldarg.0
0x7f723  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Application.Controls.AppAdvancedFind::_multiPicklistUI
0x7f728  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f72d  ldarg.0
0x7f72e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI Microsoft.Crm.Application.Controls.AppAdvancedFind::_fiscalPeriodAndYearUI
0x7f733  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f738  ldarg.0
0x7f739  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::.ctor()
0x7f73e  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppAdvancedFind::_numberUI
0x7f743  ldarg.0
0x7f744  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppAdvancedFind::_numberUI
0x7f749  ldc.i4.0
0x7f74a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x7f74f  ldarg.0
0x7f750  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppAdvancedFind::_numberUI
0x7f755  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7f75a  ldarg.0
0x7f75b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f760  ldc.i4.1
0x7f761  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x7f766  ldarg.0
0x7f767  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f76c  ldc.i4.8
0x7f76d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x7f772  ldarg.0
0x7f773  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f778  ldstr    aAdvancedfindAd// "/advancedfind/advfind.css.aspx"
0x7f77d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7f782  ldarg.0
0x7f783  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f788  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x7f78d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7f792  ldarg.0
0x7f793  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f798  ldstr    aControlsPopupm// "/_controls/popupmenu/popupmenu.css.aspx"
0x7f79d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7f7a2  ldarg.0
0x7f7a3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f7a8  ldstr    aControlsNotifi// "/_controls/notifications/notifications."...
0x7f7ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7f7b2  ldarg.0
0x7f7b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f7b8  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0x7f7bd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7f7c2  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x7f7c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7f7cc  ldarg.0
0x7f7cd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f7d2  ldstr    aStaticCommonSc_12// "/_static/_common/scripts/af_cnd_common."...
0x7f7d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f7dc  ldarg.0
0x7f7dd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f7e2  ldstr    aStaticAdvanced// "/_static/advancedfind/advfind.js"
0x7f7e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f7ec  ldarg.0
0x7f7ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f7f2  ldstr    aStaticControls_9// "/_static/_controls/popupmenu/popupmenu."...
0x7f7f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f7fc  ldarg.0
0x7f7fd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f802  ldstr    aStaticAdvanced_0// "/_static/advancedfind/cachemanager.js"
0x7f807  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f80c  ldarg.0
0x7f80d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f812  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x7f817  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f81c  ldarg.0
0x7f81d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f822  ldstr    aStaticAdvanced_1// "/_static/advancedfind/advancedfindcontr"...
0x7f827  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7f82c  ldarg.0
0x7f82d  ldstr    aMscrmAdvancedf// "Mscrm.AdvancedFind"
0x7f832  ldnull
0x7f833  ldnull
0x7f834  ldnull
0x7f835  ldarg.0
0x7f836  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x7f83b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x7f840  newobj   instance void Microsoft.Crm.Application.Controls.AdvancedFindResources::.ctor()
0x7f845  ldarg.0
0x7f846  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f84b  ldarg.0
0x7f84c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppAdvancedFind::_rm
0x7f851  callvirt instance void Microsoft.Crm.Application.Controls.AdvancedFindResources::SetStringResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager resourceManager)
0x7f856  ldarg.0
0x7f857  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f85c  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0x7f861  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7f866  ldstr    aButtonLabelClo// "Button_Label_Close"
0x7f86b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f870  ldc.i4.0
0x7f871  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7f876  ldarg.0
0x7f877  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7f87c  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0x7f881  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7f886  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0x7f88b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f890  ldc.i4.0
0x7f891  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7f896  ret
```
