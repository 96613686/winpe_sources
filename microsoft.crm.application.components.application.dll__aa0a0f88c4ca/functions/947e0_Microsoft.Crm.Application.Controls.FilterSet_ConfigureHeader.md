# Microsoft.Crm.Application.Controls.FilterSet::ConfigureHeader

- ea: `0x947e0`
- end: `0x94d1b`
- name: `Microsoft.Crm.Application.Controls.FilterSet::ConfigureHeader`
- size: `1339`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x94d20`
- `0x953d0`

## string_xrefs

- `0x94856`: `SavedQuerySelectorWebService`
- `0x94873`: `LOCID_GF_COMPLEXCRITERIA`
- `0x94879`: `MenuItem_Label_ComplexFilterCriteria`
- `0x9488f`: `LOCID_GF_COMPLEXMESSAGE`
- `0x94895`: `MenuItem_Label_ComplexFilterMessage`
- `0x948ab`: `LOCID_GF_COMPLEXINFO`
- `0x949a7`: `LOCID_GF_TOOLTIPTEMPLATE`
- `0x949ad`: `GridFilters_TooltipTemplate`
- `0x94c66`: `LOCID_GF_COMPLEXFILTERNAMES`
- `0x94c6c`: `GridFilters_ComplexFilterWarningColumnName`

## pseudocode

```c

```

## disassembly

```asm
0x947e0  ldarg.0
0x947e1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x947e6  ldarg.0
0x947e7  ldarg.0
0x947e8  call     instance string Microsoft.Crm.Application.Controls.FilterSet::FilterSetId()
0x947ed  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x947f2  ldarg.0
0x947f3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x947f8  ldstr    aStaticControls_21// "/_static/_controls/GridFilters/GridFilt"...
0x947fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94802  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94807  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9480c  ldarg.0
0x9480d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94812  ldstr    aStaticControls_6// "/_static/_controls/MenuSelector/MenuSel"...
0x94817  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9481c  ldarg.0
0x9481d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94822  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x94827  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9482c  ldarg.0
0x9482d  ldstr    aMscrmFilterset// "Mscrm.FilterSet"
0x94832  ldnull
0x94833  ldnull
0x94834  ldnull
0x94835  ldarg.0
0x94836  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9483b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x94840  ldarg.0
0x94841  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94846  ldstr    aAdvancedfind// "AdvancedFind"
0x9484b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x94850  ldarg.0
0x94851  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94856  ldstr    aSavedquerysele_1// "SavedQuerySelectorWebService"
0x9485b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x94860  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x94865  stloc.0
0x94866  ldarg.0
0x94867  ldloc.0
0x94868  call     instance void Microsoft.Crm.Application.Controls.FilterSet::SetAdvancedFindResources(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager resourceManager)
0x9486d  ldarg.0
0x9486e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94873  ldstr    aLocidGfComplex// "LOCID_GF_COMPLEXCRITERIA"
0x94878  ldloc.0
0x94879  ldstr    aMenuitemLabelC_9// "MenuItem_Label_ComplexFilterCriteria"
0x9487e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94883  ldc.i4.0
0x94884  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94889  ldarg.0
0x9488a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9488f  ldstr    aLocidGfComplex_0// "LOCID_GF_COMPLEXMESSAGE"
0x94894  ldloc.0
0x94895  ldstr    aMenuitemLabelC_10// "MenuItem_Label_ComplexFilterMessage"
0x9489a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9489f  ldc.i4.0
0x948a0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x948a5  ldarg.0
0x948a6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x948ab  ldstr    aLocidGfComplex_1// "LOCID_GF_COMPLEXINFO"
0x948b0  ldloc.0
0x948b1  ldstr    aErroriconaltin// "ErrorIconAltInformation"
0x948b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x948bb  ldc.i4.0
0x948bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x948c1  ldarg.0
0x948c2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x948c7  ldstr    aLocidGfSavedcr// "LOCID_GF_SAVEDCRITERION"
0x948cc  ldloc.0
0x948cd  ldstr    aGridfiltersSav_0// "GridFilters_SavedFilterCriterion"
0x948d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x948d7  ldc.i4.0
0x948d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x948dd  ldarg.0
0x948de  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x948e3  ldstr    aLocidGfUnsaved// "LOCID_GF_UNSAVEDCRITERION"
0x948e8  ldloc.0
0x948e9  ldstr    aGridfiltersUns// "GridFilters_UnsavedFilterCriterion"
0x948ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x948f3  ldc.i4.0
0x948f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x948f9  ldarg.0
0x948fa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x948ff  ldstr    aLocidGfJumpbar// "LOCID_GF_JUMPBARMESSAGE"
0x94904  ldloc.0
0x94905  ldstr    aGridfiltersJum// "GridFilters_JumpBarWarningConfirmation"
0x9490a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9490f  ldc.i4.0
0x94910  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94915  ldarg.0
0x94916  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9491b  ldstr    aLocidGfLookupm// "LOCID_GF_LOOKUPMAXLIMIT"
0x94920  ldloc.0
0x94921  ldstr    aGridfiltersAle// "GridFilters_AlertLookupMaxRecords"
0x94926  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9492b  ldc.i4.0
0x9492c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94931  ldarg.0
0x94932  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94937  ldstr    aLocidGfPicklis// "LOCID_GF_PICKLISTMAXLIMIT"
0x9493c  ldloc.0
0x9493d  ldstr    aGridfiltersAle_0// "GridFilters_AlertPicklistMaxRecords"
0x94942  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94947  ldc.i4.0
0x94948  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9494d  ldarg.0
0x9494e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94953  ldstr    aLocidGfAnd// "LOCID_GF_AND"
0x94958  ldloc.0
0x94959  ldstr    aGridfiltersAnd// "GridFilters_AND"
0x9495e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94963  ldc.i4.0
0x94964  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94969  ldarg.0
0x9496a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9496f  ldstr    aLocidGfOr// "LOCID_GF_OR"
0x94974  ldloc.0
0x94975  ldstr    aGridfiltersOr// "GridFilters_OR"
0x9497a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9497f  ldc.i4.0
0x94980  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94985  ldarg.0
0x94986  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9498b  ldstr    aLocidGfBinaryc// "LOCID_GF_BINARYCONDITIONFORMAT"
0x94990  ldloc.0
0x94991  ldstr    aGridfiltersBin// "GridFilters_BinaryConditionTextForToolt"...
0x94996  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9499b  ldc.i4.0
0x9499c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x949a1  ldarg.0
0x949a2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x949a7  ldstr    aLocidGfTooltip// "LOCID_GF_TOOLTIPTEMPLATE"
0x949ac  ldloc.0
0x949ad  ldstr    aGridfiltersToo// "GridFilters_TooltipTemplate"
0x949b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x949b7  ldc.i4.0
0x949b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x949bd  ldarg.0
0x949be  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x949c3  ldstr    aLocidGfNofilte// "LOCID_GF_NOFILTERAPPLIEDTEXT"
0x949c8  ldloc.0
0x949c9  ldstr    aGridfiltersNof// "GridFilters_NoFilterAppliedTextForToolt"...
0x949ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x949d3  ldc.i4.0
0x949d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x949d9  ldarg.0
0x949da  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x949df  ldstr    aLocidGfLastxho// "LOCID_GF_LASTXHOURS"
0x949e4  ldloc.0
0x949e5  ldstr    aGridfiltersOpt// "GridFilters_Option_LastXHours"
0x949ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x949ef  ldc.i4.0
0x949f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x949f5  ldarg.0
0x949f6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x949fb  ldstr    aLocidGfNextxho// "LOCID_GF_NEXTXHOURS"
0x94a00  ldloc.0
0x94a01  ldstr    aGridfiltersOpt_0// "GridFilters_Option_NextXHours"
0x94a06  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a0b  ldc.i4.0
0x94a0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a11  ldarg.0
0x94a12  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94a17  ldstr    aLocidGfLastxda// "LOCID_GF_LASTXDAYS"
0x94a1c  ldloc.0
0x94a1d  ldstr    aGridfiltersOpt_1// "GridFilters_Option_LastXDays"
0x94a22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a27  ldc.i4.0
0x94a28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a2d  ldarg.0
0x94a2e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94a33  ldstr    aLocidGfNextxda// "LOCID_GF_NEXTXDAYS"
0x94a38  ldloc.0
0x94a39  ldstr    aGridfiltersOpt_2// "GridFilters_Option_NextXDays"
0x94a3e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a43  ldc.i4.0
0x94a44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a49  ldarg.0
0x94a4a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94a4f  ldstr    aLocidGfLastxwe// "LOCID_GF_LASTXWEEKS"
0x94a54  ldloc.0
0x94a55  ldstr    aGridfiltersOpt_3// "GridFilters_Option_LastXWeeks"
0x94a5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a5f  ldc.i4.0
0x94a60  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a65  ldarg.0
0x94a66  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94a6b  ldstr    aLocidGfNextxwe// "LOCID_GF_NEXTXWEEKS"
0x94a70  ldloc.0
0x94a71  ldstr    aGridfiltersOpt_4// "GridFilters_Option_NextXWeeks"
0x94a76  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a7b  ldc.i4.0
0x94a7c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a81  ldarg.0
0x94a82  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94a87  ldstr    aLocidGfLastxmo// "LOCID_GF_LASTXMONTHS"
0x94a8c  ldloc.0
0x94a8d  ldstr    aGridfiltersOpt_5// "GridFilters_Option_LastXMonths"
0x94a92  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94a97  ldc.i4.0
0x94a98  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94a9d  ldarg.0
0x94a9e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94aa3  ldstr    aLocidGfNextxmo// "LOCID_GF_NEXTXMONTHS"
0x94aa8  ldloc.0
0x94aa9  ldstr    aGridfiltersOpt_6// "GridFilters_Option_NextXMonths"
0x94aae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94ab3  ldc.i4.0
0x94ab4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94ab9  ldarg.0
0x94aba  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94abf  ldstr    aLocidGfLastxye// "LOCID_GF_LASTXYEARS"
0x94ac4  ldloc.0
0x94ac5  ldstr    aGridfiltersOpt_7// "GridFilters_Option_LastXYears"
0x94aca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94acf  ldc.i4.0
0x94ad0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94ad5  ldarg.0
0x94ad6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94adb  ldstr    aLocidGfNextxye// "LOCID_GF_NEXTXYEARS"
0x94ae0  ldloc.0
0x94ae1  ldstr    aGridfiltersOpt_8// "GridFilters_Option_NextXYears"
0x94ae6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94aeb  ldc.i4.0
0x94aec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94af1  ldarg.0
0x94af2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94af7  ldstr    aLocidGfOlderth// "LOCID_GF_OLDERTHANXMONTHS"
0x94afc  ldloc.0
0x94afd  ldstr    aGridfiltersOpt_9// "GridFilters_Option_OlderThanXMonths"
0x94b02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b07  ldc.i4.0
0x94b08  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b0d  ldarg.0
0x94b0e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b13  ldstr    aLocidGfOlderth_0// "LOCID_GF_OLDERTHANXYEARS"
0x94b18  ldloc.0
0x94b19  ldstr    aGridfiltersOpt_10// "GridFilters_Option_OlderThanXYears"
0x94b1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b23  ldc.i4.0
0x94b24  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b29  ldarg.0
0x94b2a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b2f  ldstr    aLocidGfOlderth_1// "LOCID_GF_OLDERTHANXWEEKS"
0x94b34  ldloc.0
0x94b35  ldstr    aGridfiltersOpt_11// "GridFilters_Option_OlderThanXWeeks"
0x94b3a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b3f  ldc.i4.0
0x94b40  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b45  ldarg.0
0x94b46  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b4b  ldstr    aLocidGfOlderth_2// "LOCID_GF_OLDERTHANXDAYS"
0x94b50  ldloc.0
0x94b51  ldstr    aGridfiltersOpt_12// "GridFilters_Option_OlderThanXDays"
0x94b56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b5b  ldc.i4.0
0x94b5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b61  ldarg.0
0x94b62  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b67  ldstr    aLocidGfOlderth_3// "LOCID_GF_OLDERTHANXHOURS"
0x94b6c  ldloc.0
0x94b6d  ldstr    aGridfiltersOpt_13// "GridFilters_Option_OlderThanXHours"
0x94b72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b77  ldc.i4.0
0x94b78  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b7d  ldarg.0
0x94b7e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b83  ldstr    aLocidGfOlderth_4// "LOCID_GF_OLDERTHANXMINUTES"
0x94b88  ldloc.0
0x94b89  ldstr    aGridfiltersOpt_14// "GridFilters_Option_OlderThanXMinutes"
0x94b8e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94b93  ldc.i4.0
0x94b94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94b99  ldarg.0
0x94b9a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94b9f  ldstr    aLocidGfLastxfi// "LOCID_GF_LASTXFISCALYEARS"
0x94ba4  ldloc.0
0x94ba5  ldstr    aGridfiltersOpt_15// "GridFilters_Option_LastXFiscalYears"
0x94baa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94baf  ldc.i4.0
0x94bb0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94bb5  ldarg.0
0x94bb6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94bbb  ldstr    aLocidGfNextxfi// "LOCID_GF_NEXTXFISCALYEARS"
0x94bc0  ldloc.0
0x94bc1  ldstr    aGridfiltersOpt_16// "GridFilters_Option_NextXFiscalYears"
0x94bc6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94bcb  ldc.i4.0
0x94bcc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94bd1  ldarg.0
0x94bd2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94bd7  ldstr    aLocidGfLastxfi_0// "LOCID_GF_LASTXFISCALPERIODS"
0x94bdc  ldloc.0
0x94bdd  ldstr    aGridfiltersOpt_17// "GridFilters_Option_LastXFiscalPeriods"
0x94be2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x94be7  ldc.i4.0
0x94be8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x94bed  ldarg.0
0x94bee  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x94bf3  ldstr    aLocidGfNextxfi_0// "LOCID_GF_NEXTXFISCALPERIODS"
  ... truncated ...
```
