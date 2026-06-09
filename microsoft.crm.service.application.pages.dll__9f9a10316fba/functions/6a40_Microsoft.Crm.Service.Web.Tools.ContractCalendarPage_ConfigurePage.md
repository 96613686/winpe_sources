# Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::ConfigurePage

- ea: `0x6a40`
- end: `0x6b94`
- name: `Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::ConfigurePage`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6a40`

## string_xrefs

- `0x6acd`: `CustomerService`
- `0x6b52`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x6a40  ldarg.0
0x6a41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x6a46  ldarg.0
0x6a47  ldarg.0
0x6a48  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6a4d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6a52  ldstr    aOtype_0// "otype"
0x6a57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6a5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6a61  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6a66  stfld    int32 Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::_objectType
0x6a6b  ldarg.0
0x6a6c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a71  ldstr    aSobjectname// "_sObjectName"
0x6a76  ldarg.0
0x6a77  ldfld    int32 Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::_objectType
0x6a7c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x6a81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6a86  ldarg.0
0x6a87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a8c  ldstr    aGuidentityid// "_guidEntityId"
0x6a91  ldarg.0
0x6a92  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6a97  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6a9c  ldstr    aId// "id"
0x6aa1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6aa6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x6aab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6ab0  ldarg.0
0x6ab1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6ab6  ldstr    aIobjecttype// "_iObjectType"
0x6abb  ldarg.0
0x6abc  ldfld    int32 Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::_objectType
0x6ac1  conv.i8
0x6ac2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x6ac7  ldarg.0
0x6ac8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6acd  ldstr    aCustomerservic// "CustomerService"
0x6ad2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6ad7  ldarg.0
0x6ad8  ldc.i4.0
0x6ad9  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_ShowStatusBar(bool)
0x6ade  ldarg.0
0x6adf  ldarg.0
0x6ae0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6ae5  ldstr    aDialogSetcalen// "Dialog_SetCalendar_Title"
0x6aea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6aef  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x6af4  ldarg.0
0x6af5  ldarg.0
0x6af6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6afb  ldstr    aDialogSetcalen_0// "Dialog_SetCalendar_Description"
0x6b00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6b05  ldc.i4.1
0x6b06  newarr   [mscorlib]System.Object
0x6b0b  dup
0x6b0c  ldc.i4.0
0x6b0d  ldarg.0
0x6b0e  ldfld    int32 Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::_objectType
0x6b13  ldc.i4.1
0x6b14  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x6b19  stelem.ref
0x6b1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x6b1f  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x6b24  ldarg.0
0x6b25  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x6b2a  ldc.i4.1
0x6b2b  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x6b30  stloc.0
0x6b31  ldarg.0
0x6b32  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x6b37  ldloc.0
0x6b38  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0x6b3d  ldstr    aButtonLabelSet// "Button_Label_Set"
0x6b42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x6b47  ldarg.0
0x6b48  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6b4d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6b52  ldstr    aReadonly// "readonly"
0x6b57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6b5c  ldstr    aTrue// "true"
0x6b61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b66  brfalse.s loc_6B86
0x6b68  ldarg.0
0x6b69  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppContractCalendar Microsoft.Crm.Service.Web.Tools.ContractCalendarPage::effectivitycalendar
0x6b6e  ldc.i4.1
0x6b6f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppContractCalendar::set_AppContractCalendarDisabled(bool)
0x6b74  ldarg.0
0x6b75  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x6b7a  ldloc.0
0x6b7b  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0x6b80  ldc.i4.1
0x6b81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x6b86  ldarg.0
0x6b87  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x6b8c  ldc.i4.2
0x6b8d  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x6b92  pop
0x6b93  ret
```
