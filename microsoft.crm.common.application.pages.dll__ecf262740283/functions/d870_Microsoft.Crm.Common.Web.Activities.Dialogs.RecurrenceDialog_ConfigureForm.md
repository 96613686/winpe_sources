# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::ConfigureForm

- ea: `0xd870`
- end: `0xda76`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::ConfigureForm`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd870`
- `0xda80`
- `0xdb30`
- `0xdbc0`
- `0xdd50`
- `0xdf40`
- `0xdfb0`
- `0xe120`
- `0xe6b0`
- `0xe7e0`

## pseudocode

```c

```

## disassembly

```asm
0xd870  ldarg.0
0xd871  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xd876  ldarg.0
0xd877  ldarg.0
0xd878  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xd87d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xd882  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd887  ldarg.0
0xd888  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd88d  ldarg.0
0xd88e  ldfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::enableEndSeries
0xd893  brtrue.s loc_D8A7
0xd895  ldarg.0
0xd896  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::entityId
0xd89b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd8a0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd8a5  br.s     loc_D8A8
0xd8a7  ldc.i4.0
0xd8a8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ReadOnly(bool)
0xd8ad  ldarg.0
0xd8ae  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::entityId
0xd8b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd8b8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd8bd  brfalse  loc_D962
0xd8c2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0xd8c7  stloc.0
0xd8c8  ldloc.0
0xd8c9  ldstr    aStatecode// "statecode"
0xd8ce  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xd8d3  ldloc.0
0xd8d4  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0xd8d9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xd8de  ldstr    aRecurringappoi// "recurringappointmentmaster"
0xd8e3  ldarg.0
0xd8e4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::entityId
0xd8e9  ldloc.0
0xd8ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd8ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd8f4  dup
0xd8f5  ldstr    aStatecode// "statecode"
0xd8fa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd8ff  castclass [mscorlib]System.String
0xd904  ldstr    aCanceled// "Canceled"
0xd909  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd90e  brtrue.s loc_D932
0xd910  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteActivity()
0xd915  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd91a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd91f  brtrue.s loc_D93E
0xd921  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xd926  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd92b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd930  brtrue.s loc_D93E
0xd932  ldarg.0
0xd933  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd938  ldc.i4.1
0xd939  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ReadOnly(bool)
0xd93e  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0xd943  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd948  unbox.any [mscorlib]System.Int32
0xd94d  stloc.1
0xd94e  ldarg.0
0xd94f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd954  ldstr    aSeriestimezone// "_seriesTimeZoneCode"
0xd959  ldloc.1
0xd95a  conv.i8
0xd95b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd960  br.s     loc_D97D
0xd962  ldarg.0
0xd963  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd968  ldstr    aSeriestimezone// "_seriesTimeZoneCode"
0xd96d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xd972  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZoneCode()
0xd977  conv.i8
0xd978  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd97d  ldarg.0
0xd97e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xd983  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZoneCode()
0xd988  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::LoadTimeZone(int32 timeZoneCode)
0xd98d  ldarg.0
0xd98e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd993  ldc.i4.1
0xd994  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0xd999  ldarg.0
0xd99a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd99f  ldarg.0
0xd9a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd9a5  ldstr    aRecurrencerule// "RecurrenceRule.Dialog.Title"
0xd9aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd9af  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xd9b4  ldarg.0
0xd9b5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd9ba  ldarg.0
0xd9bb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd9c0  ldstr    aRecurrencerule_12// "RecurrenceRule.Dialog.Description"
0xd9c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd9ca  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xd9cf  ldarg.0
0xd9d0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd9d5  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0xd9da  brfalse.s loc_D9E2
0xd9dc  ldarg.0
0xd9dd  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::DisableChildControls()
0xd9e2  ldarg.0
0xd9e3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xd9e8  ldstr    aRecurrencepatt// "recurrencePatternType"
0xd9ed  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd9f2  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl
0xd9f7  dup
0xd9f8  ldstr    aRecurrencerule_13// "recurrencerule"
0xd9fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda02  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0xda0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xda11  ldstr    aRecurrencepatt_0// "recurrencepatterntype"
0xda16  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xda1b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xda20  dup
0xda21  ldarg.0
0xda22  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_recurrenceDialogForm
0xda27  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0xda2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xda31  ldstr    aTitle// "title"
0xda36  ldarg.0
0xda37  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda3c  ldstr    aRecurrencerule_14// "RecurrenceRule.RecurrencePatternSection"...
0xda41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda46  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xda4b  ldarg.0
0xda4c  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeDaily()
0xda51  ldarg.0
0xda52  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeWeekly()
0xda57  ldarg.0
0xda58  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeMonthly()
0xda5d  ldarg.0
0xda5e  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeYearly()
0xda63  ldarg.0
0xda64  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeRecurrenceRange()
0xda69  ldarg.0
0xda6a  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeStartEndDuractionControls()
0xda6f  ldarg.0
0xda70  call     instance void Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::AddDialogButtons()
0xda75  ret
```
