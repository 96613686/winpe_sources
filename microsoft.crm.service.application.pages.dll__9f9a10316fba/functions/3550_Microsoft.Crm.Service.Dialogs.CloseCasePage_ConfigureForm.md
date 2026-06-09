# Microsoft.Crm.Service.Dialogs.CloseCasePage::ConfigureForm

- ea: `0x3550`
- end: `0x3a23`
- name: `Microsoft.Crm.Service.Dialogs.CloseCasePage::ConfigureForm`
- size: `1235`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3550`

## string_xrefs

- `0x39d2`: `/_common/error/dlg_error.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3550  ldarg.0
0x3551  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3556  ldstr    aIncident// "incident"
0x355b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3560  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3565  stloc.0
0x3566  ldloc.0
0x3567  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x356c  stloc.1
0x356d  ldarg.0
0x356e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3573  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3578  ldstr    aPid// "pId"
0x357d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3582  stloc.2
0x3583  ldloca.s 3
0x3585  ldarg.0
0x3586  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x358b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3590  ldstr    aPid// "pId"
0x3595  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x359a  call     instance void [mscorlib]System.Guid::.ctor(string)
0x359f  ldarg.0
0x35a0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x35a5  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x35aa  dup
0x35ab  ldarg.0
0x35ac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x35b1  ldstr    aCaseResolveDlg_1// "Case_Resolve_Dlg_Title"
0x35b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35bb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x35c0  dup
0x35c1  ldarg.0
0x35c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x35c7  ldstr    aCaseResolveDlg_2// "Case_Resolve_Dlg_Desc"
0x35cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35d1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x35d6  dup
0x35d7  ldc.i4.0
0x35d8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x35dd  dup
0x35de  ldc.i4.1
0x35df  ldstr    aButtonLabelRes// "Button_Label_Resolve"
0x35e4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x35e9  ldc.i4.2
0x35ea  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x35ef  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x35f4  ldarg.0
0x35f5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x35fa  ldarg.0
0x35fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3600  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0x3605  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x360a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0x360f  ldarg.0
0x3610  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x3615  ldarg.0
0x3616  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x361b  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0x3620  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3625  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0x362a  ldarg.0
0x362b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x3630  ldarg.0
0x3631  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3636  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0x363b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3640  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0x3645  ldarg.0
0x3646  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x364b  ldarg.0
0x364c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3651  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0x3656  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x365b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0x3660  ldarg.0
0x3661  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x3666  ldarg.0
0x3667  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x366c  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0x3671  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3676  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0x367b  ldarg.0
0x367c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x3681  ldarg.0
0x3682  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3687  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0x368c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3691  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0x3696  ldloc.3
0x3697  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x369c  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceCommands.CalculateTotalTimeIncidentCommand::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36a1  call     instance int64 [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceCommands.CalculateTotalTimeIncidentCommand::Execute()
0x36a6  stloc.s  4
0x36a8  ldloc.s  4
0x36aa  ldc.i4.0
0x36ab  conv.i8
0x36ac  clt
0x36ae  ldc.i4.0
0x36af  ceq
0x36b1  ldstr    aTotalTimeIsNeg// "Total time is negative: {0}"
0x36b6  ldc.i4.1
0x36b7  newarr   [mscorlib]System.Object
0x36bc  dup
0x36bd  ldc.i4.0
0x36be  ldloc.s  4
0x36c0  box      [mscorlib]System.Int64
0x36c5  stelem.ref
0x36c6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x36cb  ldarg.0
0x36cc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x36d1  ldloc.s  4
0x36d3  conv.i4
0x36d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0x36d9  ldarg.0
0x36da  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x36df  ldstr    aItotaltime// "_iTotalTime"
0x36e4  ldloc.s  4
0x36e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x36eb  ldarg.0
0x36ec  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Dialogs.CloseCasePage::billabletimespent
0x36f1  ldc.i4.2
0x36f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x36f7  ldstr    aIncident// "incident"
0x36fc  ldc.i4.1
0x36fd  stloc.s  8
0x36ff  ldloca.s 8
0x3701  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.IncidentState
0x3707  callvirt instance string [mscorlib]System.Object::ToString()
0x370c  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x3711  stloc.s  5
0x3713  ldloc.0
0x3714  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x3719  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x371e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3723  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0x3728  brfalse.s loc_3752
0x372a  ldloc.0
0x372b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x3730  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0x3735  brfalse.s loc_3752
0x3737  ldloc.0
0x3738  ldloc.3
0x3739  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x373e  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCurrentStatusCode(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3743  stloc.s  9
0x3745  ldarg.0
0x3746  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CloseCasePage::selResolution
0x374b  ldloc.s  9
0x374d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_CurrentStatus(int32)
0x3752  ldarg.0
0x3753  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CloseCasePage::selResolution
0x3758  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x375d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3762  ldc.i4.s 0x70
0x3764  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3769  ldstr    aStatuscode// "statuscode"
0x376e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3773  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x3778  ldarg.0
0x3779  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CloseCasePage::selResolution
0x377e  ldc.i4.1
0x377f  newarr   [mscorlib]System.Int32
0x3784  dup
0x3785  ldc.i4.0
0x3786  ldloc.s  5
0x3788  stelem.i4
0x3789  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x378e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3793  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x3798  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x379d  stloc.s  6
0x379f  ldloc.s  6
0x37a1  brfalse.s loc_37C8
0x37a3  ldloc.s  6
0x37a5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x37aa  brfalse.s loc_37C8
0x37ac  ldarg.0
0x37ad  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CloseCasePage::selResolution
0x37b2  ldstr    aStyle// "Style"
0x37b7  ldstr    aBackgroundColo// "background-color:"
0x37bc  ldloc.s  6
0x37be  call     string [mscorlib]System.String::Concat(string, string)
0x37c3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x37c8  ldloc.1
0x37c9  ldloc.2
0x37ca  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x37cf  ldloc.1
0x37d0  ldstr    aColumnsetColum// "<columnset><column>contractid</column><"...
0x37d5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x37da  ldloc.1
0x37db  ldstr    aContractid// "contractid"
0x37e0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x37e5  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x37ea  stloc.s  7
0x37ec  ldloc.s  7
0x37ee  brfalse  loc_396C
0x37f3  ldstr    aContract// "contract"
0x37f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3802  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Contract::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3807  stloc.s  0xA
0x3809  ldloc.s  0xA
0x380b  ldloc.s  7
0x380d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x3812  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x3817  ldloc.s  0xA
0x3819  ldstr    aColumnsetColum_0// "<columnset><column>statecode</column><c"...
0x381e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x3823  ldloc.s  0xA
0x3825  ldstr    aStatecode// "statecode"
0x382a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x382f  castclass [mscorlib]System.String
0x3834  ldc.i4.2
0x3835  stloc.s  0xC
0x3837  ldloca.s 0xC
0x3839  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ContractState
0x383f  callvirt instance string [mscorlib]System.Object::ToString()
0x3844  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3849  brfalse.s loc_386C
0x384b  ldarg.0
0x384c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3851  ldstr    aLocidConfirmPa// "LOCID_CONFIRM_PARENT"
0x3856  ldarg.0
0x3857  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x385c  ldstr    aCaseResolveDlg_3// "Case_Resolve_Dlg_Confirm_Parent"
0x3861  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3866  ldc.i4.0
0x3867  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x386c  ldloc.1
0x386d  ldstr    aContractdetail// "contractdetailid"
0x3872  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3877  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x387c  stloc.s  0xB
0x387e  ldloc.s  0xB
0x3880  brfalse  loc_396C
0x3885  ldstr    aContractdetail_0// "contractdetail"
0x388a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x388f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3894  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ContractDetail::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3899  stloc.s  0xD
0x389b  ldloc.s  0xD
0x389d  ldloc.s  0xB
0x389f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x38a4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x38a9  ldloc.s  0xD
0x38ab  ldstr    aColumnsetColum_1// "<columnset><column>allotmentsremaining<"...
0x38b0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x38b5  ldloc.s  0xD
0x38b7  ldstr    aStatecode// "statecode"
0x38bc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x38c1  castclass [mscorlib]System.String
0x38c6  ldc.i4.2
0x38c7  stloc.s  0xE
0x38c9  ldloca.s 0xE
0x38cb  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ContractDetailState
0x38d1  callvirt instance string [mscorlib]System.Object::ToString()
0x38d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38db  brtrue.s loc_3905
0x38dd  ldloc.s  0xD
0x38df  ldstr    aStatecode// "statecode"
0x38e4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x38e9  castclass [mscorlib]System.String
0x38ee  ldc.i4.3
0x38ef  stloc.s  0xE
0x38f1  ldloca.s 0xE
0x38f3  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ContractDetailState
0x38f9  callvirt instance string [mscorlib]System.Object::ToString()
0x38fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3903  brfalse.s loc_3926
0x3905  ldarg.0
0x3906  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x390b  ldstr    aLocidConfirmCo// "LOCID_CONFIRM_CONTRACTDETAILSTAT"
0x3910  ldarg.0
0x3911  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3916  ldstr    aCaseResolveDlg_4// "Case_Resolve_Dlg_Confirm_ContractDetail"...
0x391b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3920  ldc.i4.0
0x3921  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3926  ldarg.0
0x3927  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x392c  ldstr    aBistimeallotme// "_bIsTimeAllotment"
0x3931  ldloc.s  0xA
0x3933  ldstr    aAllotmenttypec// "allotmenttypecode"
0x3938  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x393d  unbox.any [mscorlib]System.Int32
0x3942  ldc.i4.2
0x3943  ceq
0x3945  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x394a  ldarg.0
0x394b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3950  ldstr    aIallotmentsrem// "_iAllotmentsRemaining"
0x3955  ldloc.s  0xD
0x3957  ldstr    aAllotmentsrema// "allotmentsremaining"
0x395c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3961  unbox.any [mscorlib]System.Int32
0x3966  conv.i8
0x3967  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x396c  ldstr    aIncident// "incident"
0x3971  ldloc.3
  ... truncated ...
```
