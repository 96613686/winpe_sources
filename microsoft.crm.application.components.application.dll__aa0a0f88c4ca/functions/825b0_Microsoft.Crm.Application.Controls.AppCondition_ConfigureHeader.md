# Microsoft.Crm.Application.Controls.AppCondition::ConfigureHeader

- ea: `0x825b0`
- end: `0x8287f`
- name: `Microsoft.Crm.Application.Controls.AppCondition::ConfigureHeader`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7d450`
- `0x7e150`
- `0x81da0`

## string_xrefs

- `0x826db`: `XML_LANGUAGE_NAME`
- `0x8276a`: `/_static/_common/scripts/af_cnd_common.js`
- `0x8279a`: `/_static/advancedfind/cachemanager.js`
- `0x8274a`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x8275a`: `/_static/_common/scripts/Mscrm.Caching.js`

## pseudocode

```c

```

## disassembly

```asm
0x825b0  ldarg.0
0x825b1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x825b6  ldarg.0
0x825b7  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::.ctor()
0x825bc  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Controls.AppCondition::_textBoxUI
0x825c1  ldarg.0
0x825c2  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::.ctor()
0x825c7  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Controls.AppCondition::_lookupUI
0x825cc  ldarg.0
0x825cd  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI::.ctor()
0x825d2  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateUI
0x825d7  ldarg.0
0x825d8  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI::.ctor()
0x825dd  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateAndTimeUI
0x825e2  ldarg.0
0x825e3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x825e8  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppCondition::_selectUI
0x825ed  ldarg.0
0x825ee  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist::.ctor()
0x825f3  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Application.Controls.AppCondition::_multiPicklistUI
0x825f8  ldarg.0
0x825f9  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI::.ctor()
0x825fe  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI Microsoft.Crm.Application.Controls.AppCondition::_fiscalPeriodAndYearUI
0x82603  ldarg.0
0x82604  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateUI
0x82609  ldstr    aDate// "date"
0x8260e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0x82613  ldarg.0
0x82614  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateAndTimeUI
0x82619  ldstr    aDatetime// "datetime"
0x8261e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0x82623  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x82628  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8262d  ldarg.0
0x8262e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AppCondition::_toolbar
0x82633  ldarg.0
0x82634  ldstr    aMnubar5// "mnuBar5"
0x82639  call     instance string Microsoft.Crm.Application.Controls.AppCondition::GenerateDynamicID(string staticID)
0x8263e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x82643  ldarg.0
0x82644  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AppCondition::_toolbar
0x82649  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8264e  ldarg.0
0x8264f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.AppCondition::_selectUI
0x82654  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x82659  ldarg.0
0x8265a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Controls.AppCondition::_lookupUI
0x8265f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x82664  ldarg.0
0x82665  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateUI
0x8266a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8266f  ldarg.0
0x82670  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Application.Controls.AppCondition::_dateAndTimeUI
0x82675  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8267a  ldarg.0
0x8267b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Controls.AppCondition::_textBoxUI
0x82680  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x82685  ldarg.0
0x82686  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Application.Controls.AppCondition::_multiPicklistUI
0x8268b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x82690  ldarg.0
0x82691  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.FiscalPeriodAndYearUI Microsoft.Crm.Application.Controls.AppCondition::_fiscalPeriodAndYearUI
0x82696  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8269b  ldarg.0
0x8269c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number::.ctor()
0x826a1  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppCondition::_numberUI
0x826a6  ldarg.0
0x826a7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppCondition::_numberUI
0x826ac  ldc.i4.0
0x826ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x826b2  ldarg.0
0x826b3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Controls.AppCondition::_numberUI
0x826b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x826bd  ldarg.0
0x826be  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x826c3  ldc.i4.1
0x826c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x826c9  ldarg.0
0x826ca  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x826cf  ldc.i4.8
0x826d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x826d5  ldarg.0
0x826d6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x826db  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0x826e0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x826e5  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_Parent()
0x826ea  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_TwoLetterISOLanguageName()
0x826ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x826f4  ldarg.0
0x826f5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x826fa  ldstr    aAdvancedfindAd// "/advancedfind/advfind.css.aspx"
0x826ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x82704  ldarg.0
0x82705  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8270a  ldstr    aConditionCondi// "/condition/condition.css.aspx"
0x8270f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x82714  ldarg.0
0x82715  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8271a  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x8271f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x82724  ldarg.0
0x82725  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8272a  ldstr    aControlsPopupm// "/_controls/popupmenu/popupmenu.css.aspx"
0x8272f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x82734  ldarg.0
0x82735  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8273a  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x8273f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x82744  ldarg.0
0x82745  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8274a  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/CrmInternalUti"...
0x8274f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82754  ldarg.0
0x82755  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8275a  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/Mscrm.Caching."...
0x8275f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82764  ldarg.0
0x82765  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8276a  ldstr    aStaticCommonSc_12// "/_static/_common/scripts/af_cnd_common."...
0x8276f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82774  ldarg.0
0x82775  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8277a  ldstr    aStaticConditio// "/_static/condition/condition.js"
0x8277f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82784  ldarg.0
0x82785  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8278a  ldstr    aStaticControls_9// "/_static/_controls/popupmenu/popupmenu."...
0x8278f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82794  ldarg.0
0x82795  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8279a  ldstr    aStaticAdvanced_0// "/_static/advancedfind/cachemanager.js"
0x8279f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827a4  ldarg.0
0x827a5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827aa  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x827af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827b4  ldarg.0
0x827b5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827ba  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0x827bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827c4  ldarg.0
0x827c5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827ca  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0x827cf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827d4  ldarg.0
0x827d5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827da  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0x827df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827e4  ldarg.0
0x827e5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827ea  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0x827ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x827f4  ldarg.0
0x827f5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x827fa  ldstr    aStaticFormsChe// "/_static/_forms/Checkbox.js"
0x827ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82804  ldarg.0
0x82805  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8280a  ldstr    aStaticConditio_0// "/_static/Condition/ConditionControl.js"
0x8280f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x82814  ldarg.0
0x82815  ldstr    aMscrmCondition// "Mscrm.Condition"
0x8281a  ldnull
0x8281b  ldnull
0x8281c  ldnull
0x8281d  ldarg.0
0x8281e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x82823  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x82828  newobj   instance void Microsoft.Crm.Application.Controls.AdvancedFindResources::.ctor()
0x8282d  ldarg.0
0x8282e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x82833  ldarg.0
0x82834  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppCondition::_rm
0x82839  callvirt instance void Microsoft.Crm.Application.Controls.AdvancedFindResources::SetStringResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager resourceManager)
0x8283e  ldarg.0
0x8283f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x82844  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0x82849  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8284e  ldstr    aButtonLabelClo// "Button_Label_Close"
0x82853  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82858  ldc.i4.0
0x82859  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8285e  ldarg.0
0x8285f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x82864  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0x82869  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8286e  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0x82873  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82878  ldc.i4.0
0x82879  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8287e  ret
```
