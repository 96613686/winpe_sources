# Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ConfigureForm

- ea: `0x10250`
- end: `0x1046f`
- name: `Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ConfigureForm`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xfdf0`
- `0x10470`
- `0x105d0`

## string_xrefs

- `0x102a8`: `Scheduling_Dialog_Service_Constraints`

## pseudocode

```c

```

## disassembly

```asm
0x10250  ldarg.0
0x10251  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x10256  ldarg.0
0x10257  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::PopulateSelectControls()
0x1025c  ldarg.0
0x1025d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::RequestedTime
0x10262  ldarg.0
0x10263  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10268  ldstr    aSchedulingDial// "Scheduling_Dialog_Requested_Time"
0x1026d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10272  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10277  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl::set_Label(string)
0x1027c  ldarg.0
0x1027d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchResults
0x10282  ldarg.0
0x10283  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10288  ldstr    aSchedulingDial_0// "Scheduling_Dialog_Search_Results"
0x1028d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10292  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10297  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl::set_Label(string)
0x1029c  ldarg.0
0x1029d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ServiceConstraints
0x102a2  ldarg.0
0x102a3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x102a8  ldstr    aSchedulingDial_1// "Scheduling_Dialog_Service_Constraints"
0x102ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x102b2  ldc.i4.1
0x102b3  newarr   [mscorlib]System.Object
0x102b8  dup
0x102b9  ldc.i4.0
0x102ba  ldarg.0
0x102bb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType()
0x102c0  ldc.i4.1
0x102c1  ldnull
0x102c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x102c7  stelem.ref
0x102c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x102cd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPrintDividerControl::set_Label(string)
0x102d2  ldarg.0
0x102d3  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SetCustomizableLabels()
0x102d8  ldarg.0
0x102d9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchDurationMinutes
0x102de  ldc.i4.s 0x3C
0x102e0  box      [mscorlib]System.Int32
0x102e5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x102ea  ldarg.0
0x102eb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x102f0  ldc.i4.1
0x102f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x102f6  ldarg.0
0x102f7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x102fc  ldc.i4.0
0x102fd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x10302  ldarg.0
0x10303  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10308  ldc.i4.1
0x10309  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0x1030e  ldarg.0
0x1030f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10314  ldc.i4.1
0x10315  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnResizing(bool)
0x1031a  ldarg.0
0x1031b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10320  ldc.i4.0
0x10321  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableRefresh(bool)
0x10326  ldarg.0
0x10327  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x1032c  ldc.i4.0
0x1032d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnSorting(bool)
0x10332  ldarg.0
0x10333  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10338  ldc.i4.1
0x10339  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_RefreshAsynchronous(bool)
0x1033e  ldarg.0
0x1033f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10344  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ScheduleSearchDataProvider::.ctor()
0x10349  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x1034e  ldarg.0
0x1034f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10354  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x10359  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x1035e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0x10363  ldarg.0
0x10364  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10369  ldstr    a22520c00350646// "{22520C00-3506-4670-89E8-E51C45D6DBA2}"
0x1036e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x10373  ldarg.0
0x10374  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10379  ldc.i4.0
0x1037a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EnableAutoRefresh(bool)
0x1037f  ldarg.0
0x10380  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x10385  ldstr    aDisabledblclic// "disableDblClick"
0x1038a  ldstr    a1// "1"
0x1038f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x10394  ldarg.0
0x10395  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::crmGrid
0x1039a  ldstr    aAppointmentreq// "AppointmentRequest"
0x1039f  ldsfld   string [mscorlib]System.String::Empty
0x103a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x103a9  ldarg.0
0x103aa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchButton
0x103af  ldarg.0
0x103b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x103b5  ldstr    aButtonLabelSea// "Button_Label_Search"
0x103ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x103bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x103c4  ldarg.0
0x103c5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::CancelSearchButton
0x103ca  ldarg.0
0x103cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x103d0  ldstr    aButtonLabelCan_0// "Button_Label_CancelSearch"
0x103d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x103da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x103df  ldarg.0
0x103e0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::customers
0x103e5  ldc.i4.2
0x103e6  newarr   [mscorlib]System.Int32
0x103eb  dup
0x103ec  ldc.i4.0
0x103ed  ldc.i4.1
0x103ee  stelem.i4
0x103ef  dup
0x103f0  ldc.i4.1
0x103f1  ldc.i4.2
0x103f2  stelem.i4
0x103f3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x103f8  ldarg.0
0x103f9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::serviceid
0x103fe  ldc.i4.1
0x103ff  newarr   [mscorlib]System.Int32
0x10404  dup
0x10405  ldc.i4.0
0x10406  ldc.i4   0xFA1
0x1040b  stelem.i4
0x1040c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x10411  ldarg.0
0x10412  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::resources
0x10417  ldc.i4.2
0x10418  newarr   [mscorlib]System.Int32
0x1041d  dup
0x1041e  ldc.i4.0
0x1041f  ldc.i4.8
0x10420  stelem.i4
0x10421  dup
0x10422  ldc.i4.1
0x10423  ldc.i4   0xFA0
0x10428  stelem.i4
0x10429  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1042e  ldarg.0
0x1042f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::siteid
0x10434  ldc.i4.1
0x10435  newarr   [mscorlib]System.Int32
0x1043a  dup
0x1043b  ldc.i4.0
0x1043c  ldc.i4   0xFA9
0x10441  stelem.i4
0x10442  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x10447  ldarg.0
0x10448  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1044d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0x10452  ldarg.0
0x10453  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType()
0x10458  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1045d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x10462  ldarg.0
0x10463  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SearchDurationMinutes
0x10468  ldc.i4.1
0x10469  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Required(bool)
0x1046e  ret
```
