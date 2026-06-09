# Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::ConfigurePage

- ea: `0xe800`
- end: `0xee08`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::ConfigurePage`
- size: `1544`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe800`
- `0xefc0`
- `0xf000`
- `0xf050`
- `0xf0d0`

## string_xrefs

- `0xeaf8`: `activities/act_dlgs/dlg_seriesaction.aspx_titleUpdateSeries`
- `0xeaff`: `activities/act_dlgs/dlg_seriesaction.aspx_headerTitleUpdateSeries`
- `0xeb06`: `activities/act_dlgs/dlg_seriesaction.aspx_headerUpdateSeries`
- `0xeb1e`: `activities/act_dlgs/dlg_seriesaction.aspx_textUpdateSeries1`
- `0xeb31`: `activities/act_dlgs/dlg_seriesaction.aspx_textUpdateSeries2`
- `0xeb87`: `activities/act_dlgs/dlg_seriesaction.aspx_titleOpenSeries`
- `0xeb9f`: `activities/act_dlgs/dlg_seriesaction.aspx_textOpenSeries`
- `0xebce`: `activities/act_dlgs/dlg_seriesaction.aspx_OpenSeriesOption1`
- `0xebd6`: `activities/act_dlgs/dlg_seriesaction.aspx_OpenSeriesOption2`
- `0xebf6`: `activities/act_dlgs/dlg_seriesaction.aspx_titleDeleteInstance`
- `0xec0e`: `activities/act_dlgs/dlg_seriesaction.aspx_textDeleteInstance`
- `0xec3d`: `activities/act_dlgs/dlg_seriesaction.aspx_DeleteInstanceOption1`
- `0xec45`: `activities/act_dlgs/dlg_seriesaction.aspx_DeleteInstanceOption2`
- `0xec4d`: `activities/act_dlgs/dlg_seriesaction.aspx_DeleteInstanceOption3`
- `0xec60`: `activities/act_dlgs/dlg_seriesaction.aspx_titleDeleteSeries`
- `0xec78`: `activities/act_dlgs/dlg_seriesaction.aspx_textDeleteSeries`
- `0xec93`: `activities/act_dlgs/dlg_seriesaction.aspx_DeleteSeriesOption1`
- `0xec9b`: `activities/act_dlgs/dlg_seriesaction.aspx_DeleteSeriesOption2`

## pseudocode

```c

```

## disassembly

```asm
0xe800  ldarg.0
0xe801  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe806  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe80b  ldstr    aActiontype// "actionType"
0xe810  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe815  stloc.0
0xe816  ldarg.0
0xe817  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe81c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe821  ldstr    aItotal// "iTotal"
0xe826  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe82b  stloc.1
0xe82c  ldarg.0
0xe82d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe832  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe837  ldstr    aEid// "eId"
0xe83c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe841  stloc.2
0xe842  ldarg.0
0xe843  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe848  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe84d  ldstr    aInsdel// "insDel"
0xe852  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe857  stloc.3
0xe858  ldarg.0
0xe859  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe85e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_appointmentId
0xe863  ldarg.0
0xe864  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xe869  ldarg.0
0xe86a  ldc.i4.1
0xe86b  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe870  ldloc.0
0xe871  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe876  brtrue.s loc_E8AA
0xe878  ldarg.0
0xe879  ldloc.0
0xe87a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe87f  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xe884  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe889  ldarg.0
0xe88a  ldarg.0
0xe88b  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe890  ldc.i4.1
0xe891  blt.s    loc_E8A4
0xe893  ldarg.0
0xe894  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe899  ldc.i4.6
0xe89a  bgt.s    loc_E8A4
0xe89c  ldarg.0
0xe89d  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe8a2  br.s     loc_E8A5
0xe8a4  ldc.i4.1
0xe8a5  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe8aa  ldarg.0
0xe8ab  ldc.i4.0
0xe8ac  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xe8b1  ldloc.1
0xe8b2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe8b7  brtrue.s loc_E8E2
0xe8b9  ldarg.0
0xe8ba  ldloc.1
0xe8bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe8c0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xe8c5  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xe8ca  ldarg.0
0xe8cb  ldarg.0
0xe8cc  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xe8d1  ldc.i4.0
0xe8d2  bgt.s    loc_E8D7
0xe8d4  ldc.i4.0
0xe8d5  br.s     loc_E8DD
0xe8d7  ldarg.0
0xe8d8  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xe8dd  stfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xe8e2  ldloc.2
0xe8e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe8e8  brtrue.s loc_E8F6
0xe8ea  ldarg.0
0xe8eb  ldloc.2
0xe8ec  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xe8f1  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_appointmentId
0xe8f6  ldarg.0
0xe8f7  ldc.i4.1
0xe8f8  stfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_allowInstanceDeletion
0xe8fd  ldloc.3
0xe8fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe903  brtrue.s loc_E911
0xe905  ldarg.0
0xe906  ldloc.3
0xe907  call     bool [mscorlib]System.Boolean::Parse(string)
0xe90c  stfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_allowInstanceDeletion
0xe911  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0xe916  stloc.s  4
0xe918  ldloc.s  4
0xe91a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe91f  ldstr    aStyle_0// "style"
0xe924  ldstr    aTableLayoutFix// "table-layout:fixed"
0xe929  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xe92e  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0xe933  stloc.s  5
0xe935  ldc.i4.0
0xe936  stloc.s  6
0xe938  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0xe93d  stloc.s  7
0xe93f  ldstr    asc_1F1DE// ""
0xe944  stloc.s  8
0xe946  ldstr    asc_1F1DE// ""
0xe94b  stloc.s  9
0xe94d  ldstr    asc_1F1DE// ""
0xe952  stloc.s  0xA
0xe954  ldarg.0
0xe955  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::actionType
0xe95a  stloc.s  0xC
0xe95c  ldloc.s  0xC
0xe95e  ldc.i4.1
0xe95f  sub
0xe960  switch   loc_E982, loc_EAF8, loc_EB46, loc_EB7A, loc_EBE9, loc_EC60
0xe97d  br       loc_ED40
0xe982  ldstr    aActivitiesActD_4// "activities/act_dlgs/dlg_seriesaction.as"...
0xe987  stloc.s  8
0xe989  ldstr    aActivitiesActD_5// "activities/act_dlgs/dlg_seriesaction.as"...
0xe98e  stloc.s  9
0xe990  ldstr    aActivitiesActD_6// "activities/act_dlgs/dlg_seriesaction.as"...
0xe995  stloc.s  0xA
0xe997  newobj   instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::.ctor()
0xe99c  stloc.s  0xD
0xe99e  ldloc.s  0xD
0xe9a0  ldstr    aEndseriesdate// "endSeriesDate"
0xe9a5  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xe9aa  ldloc.s  0xD
0xe9ac  ldstr    aDate// "date"
0xe9b1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_DisplayFormat(string)
0xe9b6  ldloc.s  0xD
0xe9b8  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0xe9bd  box      [mscorlib]System.DateTime
0xe9c2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xe9c7  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::.ctor()
0xe9cc  stloc.s  0xE
0xe9ce  ldloc.s  0xE
0xe9d0  ldarg.0
0xe9d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe9d6  ldstr    aActivitiesActD_7// "activities/act_dlgs/dlg_seriesaction.as"...
0xe9db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe9e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xe9e5  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::.ctor()
0xe9ea  stloc.s  0xF
0xe9ec  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0xe9f1  stloc.s  0x10
0xe9f3  ldarg.0
0xe9f4  ldloc.s  0x10
0xe9f6  ldc.i4.3
0xe9f7  newarr   [System.Web]System.Web.UI.Control
0xe9fc  dup
0xe9fd  ldc.i4.0
0xe9fe  ldloc.s  0xE
0xea00  stelem.ref
0xea01  dup
0xea02  ldc.i4.1
0xea03  ldloc.s  0xF
0xea05  stelem.ref
0xea06  dup
0xea07  ldc.i4.2
0xea08  ldloc.s  0xD
0xea0a  stelem.ref
0xea0b  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddControlsToTable(class [System.Web]System.Web.UI.HtmlControls.HtmlTable table, class [System.Web]System.Web.UI.Control[] controls)
0xea10  ldloc.s  0x10
0xea12  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0xea17  ldc.i4.0
0xea18  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::get_Item(int32)
0xea1d  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0xea22  ldc.i4.1
0xea23  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::get_Item(int32)
0xea28  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xea2d  ldstr    aClass// "class"
0xea32  ldstr    aSpacer// "Spacer"
0xea37  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xea3c  ldloc.s  0x10
0xea3e  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0xea43  ldc.i4.0
0xea44  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::get_Item(int32)
0xea49  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0xea4e  ldc.i4.2
0xea4f  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::get_Item(int32)
0xea54  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xea59  ldstr    aClass// "class"
0xea5e  ldstr    aMsCrmRecurrenc_1// "ms-crm-recurrence-dialog-datecontrol"
0xea63  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xea68  ldarg.0
0xea69  ldloc.s  7
0xea6b  ldc.i4.1
0xea6c  newarr   [System.Web]System.Web.UI.Control
0xea71  dup
0xea72  ldc.i4.0
0xea73  ldloc.s  0x10
0xea75  stelem.ref
0xea76  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddControlsToTable(class [System.Web]System.Web.UI.HtmlControls.HtmlTable table, class [System.Web]System.Web.UI.Control[] controls)
0xea7b  ldarg.0
0xea7c  ldloc.s  7
0xea7e  ldc.i4.1
0xea7f  newarr   [mscorlib]System.String
0xea84  dup
0xea85  ldc.i4.0
0xea86  ldarg.0
0xea87  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xea8c  ldstr    aActivitiesActD_8// "activities/act_dlgs/dlg_seriesaction.as"...
0xea91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xea96  stelem.ref
0xea97  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddLabelsToTable(class [System.Web]System.Web.UI.HtmlControls.HtmlTable table, string[] labels)
0xea9c  ldarg.0
0xea9d  ldloc.s  5
0xea9f  ldc.i4.3
0xeaa0  newarr   [mscorlib]System.String
0xeaa5  dup
0xeaa6  ldc.i4.0
0xeaa7  ldstr    aActivitiesActD_9// "activities/act_dlgs/dlg_seriesaction.as"...
0xeaac  stelem.ref
0xeaad  dup
0xeaae  ldc.i4.1
0xeaaf  ldstr    aActivitiesActD_10// "activities/act_dlgs/dlg_seriesaction.as"...
0xeab4  stelem.ref
0xeab5  dup
0xeab6  ldc.i4.2
0xeab7  ldstr    aActivitiesActD_11// "activities/act_dlgs/dlg_seriesaction.as"...
0xeabc  stelem.ref
0xeabd  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddOptions(class [System.Web]System.Web.UI.HtmlControls.HtmlTable optionsTable, string[] resourceStrings)
0xeac2  ldloc.s  5
0xeac4  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0xeac9  ldc.i4.2
0xeaca  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::get_Item(int32)
0xeacf  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0xead4  ldc.i4.0
0xead5  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::get_Item(int32)
0xeada  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xeadf  ldc.i4.0
0xeae0  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xeae5  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.RadioOption
0xeaea  ldc.i4.1
0xeaeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.RadioOption::set_Checked(bool)
0xeaf0  ldc.i4.1
0xeaf1  stloc.s  6
0xeaf3  br       loc_ED68
0xeaf8  ldstr    aActivitiesActD_12// "activities/act_dlgs/dlg_seriesaction.as"...
0xeafd  stloc.s  8
0xeaff  ldstr    aActivitiesActD_13// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb04  stloc.s  9
0xeb06  ldstr    aActivitiesActD_14// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb0b  stloc.s  0xA
0xeb0d  ldarg.0
0xeb0e  ldloc.s  7
0xeb10  ldc.i4.2
0xeb11  newarr   [mscorlib]System.String
0xeb16  dup
0xeb17  ldc.i4.0
0xeb18  ldarg.0
0xeb19  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeb1e  ldstr    aActivitiesActD_15// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb28  stelem.ref
0xeb29  dup
0xeb2a  ldc.i4.1
0xeb2b  ldarg.0
0xeb2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeb31  ldstr    aActivitiesActD_16// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb3b  stelem.ref
0xeb3c  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddLabelsToTable(class [System.Web]System.Web.UI.HtmlControls.HtmlTable table, string[] labels)
0xeb41  br       loc_ED68
0xeb46  ldstr    aActivitiesActD_17// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb4b  stloc.s  9
0xeb4d  ldstr    aActivitiesActD_18// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb52  stloc.s  0xA
0xeb54  ldarg.0
0xeb55  ldloc.s  7
0xeb57  ldc.i4.1
0xeb58  newarr   [mscorlib]System.String
0xeb5d  dup
0xeb5e  ldc.i4.0
0xeb5f  ldarg.0
0xeb60  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeb65  ldstr    aActivitiesActD_19// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb6f  stelem.ref
0xeb70  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::AddLabelsToTable(class [System.Web]System.Web.UI.HtmlControls.HtmlTable table, string[] labels)
0xeb75  br       loc_ED68
0xeb7a  ldarg.0
0xeb7b  ldarg.0
0xeb7c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_appointmentId
0xeb81  ldc.i4.1
0xeb82  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::RetrieveInstanceDetails(valuetype [mscorlib]System.Guid entityId, bool getSubject)
0xeb87  ldstr    aActivitiesActD_20// "activities/act_dlgs/dlg_seriesaction.as"...
0xeb8c  stloc.s  9
0xeb8e  ldarg.0
0xeb8f  ldloc.s  7
0xeb91  ldc.i4.1
0xeb92  newarr   [mscorlib]System.String
0xeb97  dup
0xeb98  ldc.i4.0
0xeb99  ldarg.0
0xeb9a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
  ... truncated ...
```
