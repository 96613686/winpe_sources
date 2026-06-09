# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeRecurrenceRange

- ea: `0xdfb0`
- end: `0xe11a`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeRecurrenceRange`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xd870`

## callees

- `0xe3f0`
- `0xe650`

## pseudocode

```c

```

## disassembly

```asm
0xdfb0  ldarg.0
0xdfb1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdfb6  ldstr    aRecurrencerang// "recurrenceRange"
0xdfbb  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0xdfc0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer
0xdfc5  stloc.0
0xdfc6  ldarg.0
0xdfc7  ldarg.0
0xdfc8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdfcd  ldstr    aRangeoption1Pa// "rangeOption1_patternstartdate"
0xdfd2  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xdfd7  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xdfdc  dup
0xdfdd  ldc.i4.0
0xdfde  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllowBlankDate(bool)
0xdfe3  ldstr    aMscrmRecurrenc_0// "Mscrm.RecurrenceDialog.dateChanged"
0xdfe8  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_OnChangeScript(string)
0xdfed  ldarg.0
0xdfee  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdff3  ldstr    aRecurrencerule_24// "RecurrenceRule.RangeOfRecurrence.NoEndD"...
0xdff8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdffd  stloc.1
0xdffe  ldc.i4.1
0xdfff  ldloc.1
0xe000  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xe005  stloc.2
0xe006  ldarg.0
0xe007  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe00c  ldstr    aRecurrencerule_25// "RecurrenceRule.RecurrencePatternSection"...
0xe011  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe016  stloc.3
0xe017  ldc.i4.2
0xe018  ldloc.3
0xe019  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xe01e  stloc.s  4
0xe020  ldarg.0
0xe021  ldstr    aRangeoption2Oc// "rangeOption2_occurrences"
0xe026  ldc.i4.1
0xe027  ldc.i4   0x3E7
0xe02c  ldc.i4.0
0xe02d  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xe032  stloc.s  5
0xe034  ldloc.s  5
0xe036  ldstr    aTitle// "title"
0xe03b  ldarg.0
0xe03c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe041  ldstr    aRegionalOption// "Regional_Option_Dlg_Number_Tab"
0xe046  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe04b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xe050  ldloc.s  4
0xe052  ldloc.s  5
0xe054  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xe059  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xe05e  ldarg.0
0xe05f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe064  ldstr    aRecurrencerule_26// "RecurrenceRule.RecurrencePatternSection"...
0xe069  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe06e  stloc.s  6
0xe070  ldc.i4.3
0xe071  ldloc.s  6
0xe073  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xe078  stloc.s  7
0xe07a  newobj   instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::.ctor()
0xe07f  stloc.s  8
0xe081  ldloc.s  8
0xe083  ldstr    aRangeoption3Pa// "rangeOption3_patternenddate"
0xe088  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xe08d  ldloc.s  8
0xe08f  ldstr    aRecurrencerule_13// "recurrencerule"
0xe094  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe099  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe09e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0xe0a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xe0a8  ldstr    aPatternenddate// "patternenddate"
0xe0ad  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xe0b2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xe0b7  ldloc.s  8
0xe0b9  ldstr    aDate// "date"
0xe0be  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_DisplayFormat(string)
0xe0c3  ldloc.s  8
0xe0c5  ldc.i4.0
0xe0c6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_ShowTime(bool)
0xe0cb  ldloc.s  8
0xe0cd  ldc.i4.0
0xe0ce  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllowBlankDate(bool)
0xe0d3  ldloc.s  8
0xe0d5  ldstr    aMscrmRecurrenc_0// "Mscrm.RecurrenceDialog.dateChanged"
0xe0da  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_OnChangeScript(string)
0xe0df  ldloc.s  7
0xe0e1  ldloc.s  8
0xe0e3  ldstr    aMsCrmRecurrenc_1// "ms-crm-recurrence-dialog-datecontrol"
0xe0e8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xe0ed  ldloc.0
0xe0ee  ldc.i4.1
0xe0ef  ldloc.2
0xe0f0  ldc.i4.0
0xe0f1  newarr   [System.Web]System.Web.UI.Control
0xe0f6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xe0fb  ldloc.0
0xe0fc  ldc.i4.2
0xe0fd  ldloc.s  4
0xe0ff  ldc.i4.0
0xe100  newarr   [System.Web]System.Web.UI.Control
0xe105  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xe10a  ldloc.0
0xe10b  ldc.i4.3
0xe10c  ldloc.s  7
0xe10e  ldc.i4.0
0xe10f  newarr   [System.Web]System.Web.UI.Control
0xe114  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xe119  ret
```
