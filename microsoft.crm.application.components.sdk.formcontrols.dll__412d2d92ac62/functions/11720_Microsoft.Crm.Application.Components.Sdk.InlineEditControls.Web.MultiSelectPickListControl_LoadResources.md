# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.MultiSelectPickListControl::LoadResources

- ea: `0x11720`
- end: `0x119f6`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.MultiSelectPickListControl::LoadResources`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x11710`

## string_xrefs

- `0x11825`: `MultiSelectPicklistControl.Screenreader.FieldText`
- `0x1183b`: `LOCID_MULTIPICKLIST_VAL_DELETE`
- `0x11845`: `MultiSelectPicklistControl.Screenreader.Delete.Selection`
- `0x1185b`: `LOCID_MULTIPICKLIST_VAL_DELETED`
- `0x11865`: `MultiSelectPicklistControl.Screenreader.Deleted.Selection`
- `0x11885`: `MultiSelectPicklistControl.Screenreader.Add.Selection`
- `0x118a5`: `MultiSelectPicklistControl.Screenreader.OptionSetItem.AriaLabel`
- `0x118c5`: `MultiSelectPicklistControl.Screenreader.TypeSomethingInput.AriaLabel`
- `0x118e5`: `MultiSelectPicklistControl.Screenreader.SelectedItemsList.Navigation`
- `0x118fb`: `LOCID_MSO_ITEMS_REMOVED`
- `0x11905`: `MultiSelectPicklistControl.Screenreader.DisplayItems.Removed`
- `0x1191b`: `LOCID_MSO_MORELINK_TITLE`
- `0x11925`: `MultiSelectPicklistControl.Screenreader.More.Title`
- `0x1193b`: `LOCID_MSO_LESSLINK_TITLE`
- `0x11945`: `MultiSelectPicklistControl.Screenreader.Less.Title`
- `0x11965`: `MultiSelectPicklistControl.Screenreader.SelectAll.Title`
- `0x11985`: `MultiSelectPicklistControl.Screenreader.SelectAll.Deselect`
- `0x119a5`: `MultiSelectPicklistControl.Screenreader.SelectAll.Select`
- `0x119c5`: `MultiSelectPicklistControl.Screenreader.TotalItems`
- `0x119db`: `LOCID_MSO_DELETE_TITLE`
- `0x119e5`: `MultiSelectPicklistControl.DeleteItem.Title`

## pseudocode

```c

```

## disassembly

```asm
0x11720  ldarg.0
0x11721  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x11726  ldstr    aMaxselectionsa// "MaxSelectionsAllowed"
0x1172b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11730  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x11735  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MultiSelectOptionValueConstants::GetMaxSelectionsAllowedForAttribute(valuetype [mscorlib]System.Guid)
0x1173a  conv.i8
0x1173b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x11740  ldarg.0
0x11741  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x11746  ldstr    aOptionsetlabel// "OptionSetLabelSeparator"
0x1174b  ldstr    asc_40F36// "; "
0x11750  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x11755  ldarg.0
0x11756  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1175b  ldstr    aLocidMsoMaxsel// "LOCID_MSO_MAXSELECTIONS"
0x11760  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11765  ldstr    aMultiselectpic// "MultiSelectPicklistControl.MaxSelection"...
0x1176a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1176f  ldc.i4.0
0x11770  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11775  ldarg.0
0x11776  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1177b  ldstr    aLocidMultipick// "LOCID_MULTIPICKLIST_TYPEAHEAD"
0x11780  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11785  ldstr    aMultiselectpic_0// "MultiSelectPicklistControl.TypeAheadSea"...
0x1178a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1178f  ldc.i4.0
0x11790  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11795  ldarg.0
0x11796  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1179b  ldstr    aLocidMultipick_0// "LOCID_MULTIPICKLIST_MORE"
0x117a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x117a5  ldstr    aMultiselectpic_1// "MultiSelectPicklistControl.More"
0x117aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x117af  ldc.i4.0
0x117b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x117b5  ldarg.0
0x117b6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x117bb  ldstr    aLocidMultipick_1// "LOCID_MULTIPICKLIST_LESS"
0x117c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x117c5  ldstr    aMultiselectpic_2// "MultiSelectPicklistControl.Less"
0x117ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x117cf  ldc.i4.0
0x117d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x117d5  ldarg.0
0x117d6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x117db  ldstr    aLocidMultipick_2// "LOCID_MULTIPICKLIST_SELECT_ALL"
0x117e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x117e5  ldstr    aMultiselectpic_3// "MultiSelectPicklistControl.SelectAll"
0x117ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x117ef  ldc.i4.0
0x117f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x117f5  ldarg.0
0x117f6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x117fb  ldstr    aLocidMultipick_3// "LOCID_MULTIPICKLIST_NOITEMS"
0x11800  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11805  ldstr    aMultiselectpic_4// "MultiSelectPicklistControl.NotItemsAvai"...
0x1180a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1180f  ldc.i4.0
0x11810  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11815  ldarg.0
0x11816  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1181b  ldstr    aLocidMultipick_4// "LOCID_MULTIPICKLIST_FIELD_TEXT"
0x11820  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11825  ldstr    aMultiselectpic_5// "MultiSelectPicklistControl.Screenreader"...
0x1182a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1182f  ldc.i4.0
0x11830  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11835  ldarg.0
0x11836  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1183b  ldstr    aLocidMultipick_5// "LOCID_MULTIPICKLIST_VAL_DELETE"
0x11840  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11845  ldstr    aMultiselectpic_6// "MultiSelectPicklistControl.Screenreader"...
0x1184a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1184f  ldc.i4.0
0x11850  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11855  ldarg.0
0x11856  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1185b  ldstr    aLocidMultipick_6// "LOCID_MULTIPICKLIST_VAL_DELETED"
0x11860  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11865  ldstr    aMultiselectpic_7// "MultiSelectPicklistControl.Screenreader"...
0x1186a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1186f  ldc.i4.0
0x11870  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11875  ldarg.0
0x11876  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1187b  ldstr    aLocidMultipick_7// "LOCID_MULTIPICKLIST_VAL_ADD"
0x11880  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11885  ldstr    aMultiselectpic_8// "MultiSelectPicklistControl.Screenreader"...
0x1188a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1188f  ldc.i4.0
0x11890  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11895  ldarg.0
0x11896  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1189b  ldstr    aLocidMsoItemAr// "LOCID_MSO_ITEM_ARIALABEL"
0x118a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x118a5  ldstr    aMultiselectpic_9// "MultiSelectPicklistControl.Screenreader"...
0x118aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x118af  ldc.i4.0
0x118b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x118b5  ldarg.0
0x118b6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x118bb  ldstr    aLocidMsoInputA// "LOCID_MSO_INPUT_ARIALABEL"
0x118c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x118c5  ldstr    aMultiselectpic_10// "MultiSelectPicklistControl.Screenreader"...
0x118ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x118cf  ldc.i4.0
0x118d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x118d5  ldarg.0
0x118d6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x118db  ldstr    aLocidMsoListNa// "LOCID_MSO_LIST_NAVIGATION"
0x118e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x118e5  ldstr    aMultiselectpic_11// "MultiSelectPicklistControl.Screenreader"...
0x118ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x118ef  ldc.i4.0
0x118f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x118f5  ldarg.0
0x118f6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x118fb  ldstr    aLocidMsoItemsR// "LOCID_MSO_ITEMS_REMOVED"
0x11900  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11905  ldstr    aMultiselectpic_12// "MultiSelectPicklistControl.Screenreader"...
0x1190a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1190f  ldc.i4.0
0x11910  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11915  ldarg.0
0x11916  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1191b  ldstr    aLocidMsoMoreli// "LOCID_MSO_MORELINK_TITLE"
0x11920  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11925  ldstr    aMultiselectpic_13// "MultiSelectPicklistControl.Screenreader"...
0x1192a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1192f  ldc.i4.0
0x11930  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11935  ldarg.0
0x11936  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1193b  ldstr    aLocidMsoLessli// "LOCID_MSO_LESSLINK_TITLE"
0x11940  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11945  ldstr    aMultiselectpic_14// "MultiSelectPicklistControl.Screenreader"...
0x1194a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1194f  ldc.i4.0
0x11950  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11955  ldarg.0
0x11956  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1195b  ldstr    aLocidMsoSelect// "LOCID_MSO_SELECTALL_FOCUSTITLE"
0x11960  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11965  ldstr    aMultiselectpic_15// "MultiSelectPicklistControl.Screenreader"...
0x1196a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1196f  ldc.i4.0
0x11970  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11975  ldarg.0
0x11976  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1197b  ldstr    aLocidMsoSelect_0// "LOCID_MSO_SELECTALL_DESELECT"
0x11980  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11985  ldstr    aMultiselectpic_16// "MultiSelectPicklistControl.Screenreader"...
0x1198a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1198f  ldc.i4.0
0x11990  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x11995  ldarg.0
0x11996  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1199b  ldstr    aLocidMsoSelect_1// "LOCID_MSO_SELECTALL_SELECT"
0x119a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x119a5  ldstr    aMultiselectpic_17// "MultiSelectPicklistControl.Screenreader"...
0x119aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x119af  ldc.i4.0
0x119b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x119b5  ldarg.0
0x119b6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x119bb  ldstr    aLocidMsoTotalI// "LOCID_MSO_TOTAL_ITEMS"
0x119c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x119c5  ldstr    aMultiselectpic_18// "MultiSelectPicklistControl.Screenreader"...
0x119ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x119cf  ldc.i4.0
0x119d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x119d5  ldarg.0
0x119d6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x119db  ldstr    aLocidMsoDelete// "LOCID_MSO_DELETE_TITLE"
0x119e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x119e5  ldstr    aMultiselectpic_19// "MultiSelectPicklistControl.DeleteItem.T"...
0x119ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x119ef  ldc.i4.0
0x119f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x119f5  ret
```
