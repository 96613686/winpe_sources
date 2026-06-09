# Microsoft.Crm.Application.Controls.DataSetControl::LoadStaticResources

- ea: `0x52f30`
- end: `0x53cbd`
- name: `Microsoft.Crm.Application.Controls.DataSetControl::LoadStaticResources`
- size: `3469`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x527b0`

## callees

- `0x53cc0`

## string_xrefs

- `0x52fcf`: `Command_Bar_Sort_Icon_Text`
- `0x52ff4`: `Command_Bar_Sort_Tool_Tip_Text`
- `0x53019`: `Command_Bar_Select_Icon_Text`
- `0x5303e`: `Command_Bar_Select_Tool_Tip_Text`
- `0x53059`: `LOCID_EGC_ARIA_CELL_TEMPLATE`
- `0x53063`: `CustomControl_Grid_Aria_Cell_Template`
- `0x53318`: `LOCID_EGC_ROLLUP_LAST_UPDATE`
- `0x53322`: `RollupFieldLastUpdatedLabel`
- `0x537dd`: `LOCID_EGC_ROWDELETE_TOOLTIP`
- `0x537e7`: `CustomControl_Grid_RowDelete_Button_Tooltip`
- `0x538ea`: `MultiSelectPicklistControl.Screenreader.FieldText`
- `0x53905`: `LOCID_EGC_MSO_VAL_DELETE`
- `0x5390f`: `MultiSelectPicklistControl.Screenreader.Delete.Selection`
- `0x5392a`: `LOCID_EGC_MSO_VAL_DELETED`
- `0x53934`: `MultiSelectPicklistControl.Screenreader.Deleted.Selection`
- `0x53959`: `MultiSelectPicklistControl.Screenreader.Add.Selection`
- `0x5397e`: `MultiSelectPicklistControl.Screenreader.OptionSetItem.AriaLabel`
- `0x539a3`: `MultiSelectPicklistControl.Screenreader.TypeSomethingInput.AriaLabel`
- `0x539c8`: `MultiSelectPicklistControl.Screenreader.SelectedItemsList.Navigation`
- `0x539e3`: `LOCID_EGC_MSO_ITEMS_REMOVED`
- `0x539ed`: `MultiSelectPicklistControl.Screenreader.DisplayItems.Removed`
- `0x53a08`: `LOCID_EGC_MSO_MORELINK_TITLE`
- `0x53a12`: `MultiSelectPicklistControl.Screenreader.More.Title`
- `0x53a2d`: `LOCID_EGC_MSO_LESSLINK_TITLE`
- `0x53a37`: `MultiSelectPicklistControl.Screenreader.Less.Title`
- `0x53a5c`: `MultiSelectPicklistControl.Screenreader.SelectAll.Title`
- `0x53a81`: `MultiSelectPicklistControl.Screenreader.SelectAll.Deselect`
- `0x53aa6`: `MultiSelectPicklistControl.Screenreader.SelectAll.Select`
- `0x53acb`: `MultiSelectPicklistControl.Screenreader.TotalItems`
- `0x53ae6`: `LOCID_EGC_MSO_DELETE_TITLE`
- `0x53af0`: `MultiSelectPicklistControl.DeleteItem.Title`
- `0x53b5f`: `Form_Component_Error`
- `0x53c33`: `LOCID_VALIDATION_ERROR_READONLY`

## pseudocode

```c

```

## disassembly

```asm
0x52f30  ldarg.0
0x52f31  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52f36  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52f3b  ldstr    aEnabledlanguag// "EnabledLanguages"
0x52f40  ldarg.0
0x52f41  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Controls.DataSetControl::SerializeEnabledLanguages()
0x52f46  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x52f4b  ldarg.0
0x52f4c  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52f51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52f56  ldstr    aMaxselectionsa// "MaxSelectionsAllowed"
0x52f5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52f60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x52f65  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MultiSelectOptionValueConstants::GetMaxSelectionsAllowedForAttribute(valuetype [mscorlib]System.Guid)
0x52f6a  conv.i8
0x52f6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x52f70  ldarg.0
0x52f71  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52f76  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52f7b  ldstr    aLocidEgcName// "LOCID_EGC_NAME"
0x52f80  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x52f85  ldstr    aCcGridName// "CC_Grid_Name"
0x52f8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52f8f  ldc.i4.0
0x52f90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x52f95  ldarg.0
0x52f96  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52f9b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52fa0  ldstr    aLocidEgcAriaEm// "LOCID_EGC_ARIA_EMPTY_CELL"
0x52fa5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x52faa  ldstr    aCustomcontrolG// "CustomControl_Grid_Aria_Empty_Cell"
0x52faf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52fb4  ldc.i4.0
0x52fb5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x52fba  ldarg.0
0x52fbb  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52fc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52fc5  ldstr    aLocidEgcCbSort// "LOCID_EGC_CB_SORT_ICON_TEXT"
0x52fca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x52fcf  ldstr    aCommandBarSort// "Command_Bar_Sort_Icon_Text"
0x52fd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52fd9  ldc.i4.0
0x52fda  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x52fdf  ldarg.0
0x52fe0  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52fe5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52fea  ldstr    aLocidEgcCbSort_0// "LOCID_EGC_CB_SORT_TOOL_TIP_TEXT"
0x52fef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x52ff4  ldstr    aCommandBarSort_0// "Command_Bar_Sort_Tool_Tip_Text"
0x52ff9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52ffe  ldc.i4.0
0x52fff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53004  ldarg.0
0x53005  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5300a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5300f  ldstr    aLocidEgcCbSele// "LOCID_EGC_CB_SELECT_TEXT"
0x53014  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53019  ldstr    aCommandBarSele// "Command_Bar_Select_Icon_Text"
0x5301e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53023  ldc.i4.0
0x53024  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53029  ldarg.0
0x5302a  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5302f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53034  ldstr    aLocidEgcSelect// "LOCID_EGC_SELECT_TOOL_TIP_TEXT"
0x53039  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5303e  ldstr    aCommandBarSele_0// "Command_Bar_Select_Tool_Tip_Text"
0x53043  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53048  ldc.i4.0
0x53049  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5304e  ldarg.0
0x5304f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53054  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53059  ldstr    aLocidEgcAriaCe// "LOCID_EGC_ARIA_CELL_TEMPLATE"
0x5305e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53063  ldstr    aCustomcontrolG_0// "CustomControl_Grid_Aria_Cell_Template"
0x53068  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5306d  ldc.i4.0
0x5306e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53073  ldarg.0
0x53074  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53079  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5307e  ldstr    aLocidEgcChoose// "LOCID_EGC_CHOOSECOLUMNS_MENUHDR"
0x53083  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53088  ldstr    aCustomcontrolG_1// "CustomControl_Grid_ChooseColumns_MenuHe"...
0x5308d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53092  ldc.i4.0
0x53093  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53098  ldarg.0
0x53099  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5309e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x530a3  ldstr    aLocidEgcDurati// "LOCID_EGC_DURATION_DAY"
0x530a8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x530ad  ldstr    aLDurationscrol// "L_DurationScrollerItem.Day_Text"
0x530b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x530b7  ldc.i4.0
0x530b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x530bd  ldarg.0
0x530be  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x530c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x530c8  ldstr    aLocidEgcDurati_0// "LOCID_EGC_DURATION_DAYS"
0x530cd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x530d2  ldstr    aLDurationscrol_0// "L_DurationScrollerItem.Days_Text"
0x530d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x530dc  ldc.i4.0
0x530dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x530e2  ldarg.0
0x530e3  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x530e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x530ed  ldstr    aLocidEgcDurati_1// "LOCID_EGC_DURATION_HOUR"
0x530f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x530f7  ldstr    aLDurationscrol_1// "L_DurationScrollerItem.Hour_Text"
0x530fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53101  ldc.i4.0
0x53102  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53107  ldarg.0
0x53108  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5310d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53112  ldstr    aLocidEgcDurati_2// "LOCID_EGC_DURATION_HOURS"
0x53117  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5311c  ldstr    aLDurationscrol_2// "L_DurationScrollerItem.Hours_Text"
0x53121  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53126  ldc.i4.0
0x53127  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5312c  ldarg.0
0x5312d  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53132  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53137  ldstr    aLocidEgcDurati_3// "LOCID_EGC_DURATION_MINUTE"
0x5313c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53141  ldstr    aLDurationscrol_3// "L_DurationScrollerItem.Minute_Text"
0x53146  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5314b  ldc.i4.0
0x5314c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53151  ldarg.0
0x53152  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53157  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5315c  ldstr    aLocidEgcDurati_4// "LOCID_EGC_DURATION_MINUTES"
0x53161  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53166  ldstr    aLDurationscrol_4// "L_DurationScrollerItem.Minutes_Text"
0x5316b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53170  ldc.i4.0
0x53171  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53176  ldarg.0
0x53177  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5317c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53181  ldstr    aLocidEgcGroupb// "LOCID_EGC_GROUPBY_ITEMS"
0x53186  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5318b  ldstr    aCustomcontrolG_2// "CustomControl_Grid_GroupBy_Items"
0x53190  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53195  ldc.i4.0
0x53196  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5319b  ldarg.0
0x5319c  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x531a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x531a6  ldstr    aLocidEgcGroupb_0// "LOCID_EGC_GROUPBY_MENUHEADER"
0x531ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x531b0  ldstr    aCustomcontrolG_3// "CustomControl_Grid_GroupBy_MenuHeader"
0x531b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x531ba  ldc.i4.0
0x531bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x531c0  ldarg.0
0x531c1  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x531c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x531cb  ldstr    aLocidEgcLookup// "LOCID_EGC_LOOKUP_DISABLE_FILTER"
0x531d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x531d5  ldstr    aCustomcontrolG_4// "CustomControl_Grid_Lookup_Disable_Filte"...
0x531da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x531df  ldc.i4.0
0x531e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x531e5  ldarg.0
0x531e6  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x531eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x531f0  ldstr    aLocidEgcLookup_0// "LOCID_EGC_LOOKUP_ENABLE_FILTER"
0x531f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x531fa  ldstr    aCustomcontrolG_5// "CustomControl_Grid_Lookup_Enable_Filter"
0x531ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53204  ldc.i4.0
0x53205  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5320a  ldarg.0
0x5320b  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53210  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53215  ldstr    aLocidEgcNoReco// "LOCID_EGC_NO_RECORDS"
0x5321a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5321f  ldstr    aLListNoRecords// "L_List_No_Records_Text"
0x53224  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53229  ldc.i4.0
0x5322a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5322f  ldarg.0
0x53230  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53235  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5323a  ldstr    aLocidEgcNogrou// "LOCID_EGC_NOGROUPING"
0x5323f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53244  ldstr    aCustomcontrolG_6// "CustomControl_Grid_NoGrouping"
0x53249  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5324e  ldc.i4.0
0x5324f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53254  ldarg.0
0x53255  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5325a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5325f  ldstr    aLocidEgcPaging// "LOCID_EGC_PAGING_FIRST"
0x53264  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53269  ldstr    aCustomcontrolG_7// "CustomControl_Grid_Paging_First"
0x5326e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53273  ldc.i4.0
0x53274  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53279  ldarg.0
0x5327a  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5327f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53284  ldstr    aLocidEgcPaging_0// "LOCID_EGC_PAGING_NEXT"
0x53289  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5328e  ldstr    aCustomcontrolG_8// "CustomControl_Grid_Paging_Next"
0x53293  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53298  ldc.i4.0
0x53299  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5329e  ldarg.0
0x5329f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x532a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x532a9  ldstr    aLocidEgcPaging_1// "LOCID_EGC_PAGING_CURRENT"
0x532ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x532b3  ldstr    aCustomcontrolG_9// "CustomControl_Grid_Paging_Current"
0x532b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x532bd  ldc.i4.0
0x532be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x532c3  ldarg.0
0x532c4  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x532c9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x532ce  ldstr    aLocidEgcPaging_2// "LOCID_EGC_PAGING_PREVIOUS"
0x532d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x532d8  ldstr    aCustomcontrolG_10// "CustomControl_Grid_Paging_Previous"
0x532dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x532e2  ldc.i4.0
0x532e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x532e8  ldarg.0
0x532e9  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x532ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x532f3  ldstr    aLocidEgcSelect_0// "LOCID_EGC_SELECTION_ALL"
0x532f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x532fd  ldstr    aGridcontrolSel// "GridControl_SelectAll"
0x53302  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53307  ldc.i4.0
0x53308  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5330d  ldarg.0
0x5330e  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53313  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53318  ldstr    aLocidEgcRollup// "LOCID_EGC_ROLLUP_LAST_UPDATE"
0x5331d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53322  ldstr    aRollupfieldlas// "RollupFieldLastUpdatedLabel"
0x53327  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5332c  ldc.i4.0
0x5332d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53332  ldarg.0
0x53333  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53338  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5333d  ldstr    aLocidEgcSave// "LOCID_EGC_SAVE"
0x53342  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53347  ldstr    aLSaveText// "L_Save_Text"
0x5334c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53351  ldc.i4.0
0x53352  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53357  ldarg.0
0x53358  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5335d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53362  ldstr    aLocidEgcRefres// "LOCID_EGC_REFRESH"
0x53367  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5336c  ldstr    aMenuitemLabelR_7// "MenuItem_Label_Refresh"
0x53371  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53376  ldc.i4.0
0x53377  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5337c  ldarg.0
0x5337d  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x53382  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x53387  ldstr    aLocidEgcUnsave// "LOCID_EGC_UNSAVED_STATUS"
0x5338c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53391  ldstr    aUnsavedchanges// "UnSavedChangesWarning"
0x53396  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5339b  ldc.i4.0
0x5339c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x533a1  ldarg.0
0x533a2  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x533a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x533ac  ldstr    aLocidEgcSaving// "LOCID_EGC_SAVING_STATUS"
0x533b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x533b6  ldstr    aSavinginformat// "SavingInformation"
0x533bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x533c0  ldc.i4.0
0x533c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x533c6  ldarg.0
0x533c7  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x533cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x533d1  ldstr    aLocidEgcRefres_0// "LOCID_EGC_REFRESH_STATUS"
0x533d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x533db  ldstr    aGridLoadingDat// "Grid.Loading.Data.Refresh"
0x533e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x533e5  ldc.i4.0
0x533e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x533eb  ldarg.0
0x533ec  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x533f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x533f6  ldstr    aLocidEgcFilter// "LOCID_EGC_FILTER_ASCENDING"
0x533fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
  ... truncated ...
```
