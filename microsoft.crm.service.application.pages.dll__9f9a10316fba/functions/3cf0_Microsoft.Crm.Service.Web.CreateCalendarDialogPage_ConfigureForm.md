# Microsoft.Crm.Service.Web.CreateCalendarDialogPage::ConfigureForm

- ea: `0x3cf0`
- end: `0x3ec9`
- name: `Microsoft.Crm.Service.Web.CreateCalendarDialogPage::ConfigureForm`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3cf0`

## string_xrefs

- `0x3dc2`: `/_static/_common/styles/AutoToolTip.js`
- `0x3d07`: `SM_Customer_Service_Schedule_Calendar_Name`
- `0x3d28`: `SM_Customer_Service_Schedule_Calendar_Name_01`
- `0x3d3e`: `LOCID_ERROR_CAL_CREATE`
- `0x3d49`: `SM_Customer_Service_Schedule_Calendar_Create_Error`
- `0x3d5f`: `LOCID_ERROR_HOLIDAY_CAL_CREATE`
- `0x3d6a`: `SM_Customer_Service_Holiday_Calendar_Create_Error`
- `0x3d8b`: `SM_Customer_Service_Schedule_Calendar_Provide_Name`
- `0x3df4`: `SM_Customer_Service_Schedule_Dialog_Title_03`
- `0x3e0c`: `DocumentManagement.Button_Label_Create`
- `0x3e52`: `serviceCalendarType`
- `0x3e6a`: `serviceCalendarType`

## pseudocode

```c

```

## disassembly

```asm
0x3cf0  ldarg.0
0x3cf1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3cf6  ldarg.0
0x3cf7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3cfc  ldstr    aLocidSelectDif// "LOCID_SELECT_DIFF_CAL_NAME"
0x3d01  ldarg.0
0x3d02  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3d07  ldstr    aSmCustomerServ// "SM_Customer_Service_Schedule_Calendar_N"...
0x3d0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3d11  ldc.i4.0
0x3d12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3d17  ldarg.0
0x3d18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3d1d  ldstr    aLocidSelectDif_0// "LOCID_SELECT_DIFF_SCH_NAME"
0x3d22  ldarg.0
0x3d23  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3d28  ldstr    aSmCustomerServ_0// "SM_Customer_Service_Schedule_Calendar_N"...
0x3d2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3d32  ldc.i4.0
0x3d33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3d38  ldarg.0
0x3d39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3d3e  ldstr    aLocidErrorCalC// "LOCID_ERROR_CAL_CREATE"
0x3d43  ldarg.0
0x3d44  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3d49  ldstr    aSmCustomerServ_1// "SM_Customer_Service_Schedule_Calendar_C"...
0x3d4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3d53  ldc.i4.0
0x3d54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3d59  ldarg.0
0x3d5a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3d5f  ldstr    aLocidErrorHoli// "LOCID_ERROR_HOLIDAY_CAL_CREATE"
0x3d64  ldarg.0
0x3d65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3d6a  ldstr    aSmCustomerServ_2// "SM_Customer_Service_Holiday_Calendar_Cr"...
0x3d6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3d74  ldc.i4.0
0x3d75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3d7a  ldarg.0
0x3d7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3d80  ldstr    aLocidSelectCal// "LOCID_SELECT_CAL_NAME"
0x3d85  ldarg.0
0x3d86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3d8b  ldstr    aSmCustomerServ_3// "SM_Customer_Service_Schedule_Calendar_P"...
0x3d90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3d95  ldc.i4.0
0x3d96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3d9b  ldarg.0
0x3d9c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3da1  ldstr    aLocidSelectHol// "LOCID_SELECT_HOLIDAY_CAL_NAME"
0x3da6  ldarg.0
0x3da7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3dac  ldstr    aSmHolidaySched// "SM_Holiday_Schedule_Calendar_Provide_Na"...
0x3db1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3db6  ldc.i4.0
0x3db7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3dbc  ldarg.0
0x3dbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3dc2  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x3dc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3dcc  ldarg.0
0x3dcd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3dd2  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x3dd7  ldstr    aNameC// "name_c"
0x3ddc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x3de1  ldarg.0
0x3de2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x3de7  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3dec  stloc.0
0x3ded  ldloc.0
0x3dee  ldarg.0
0x3def  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3df4  ldstr    aSmCustomerServ_4// "SM_Customer_Service_Schedule_Dialog_Tit"...
0x3df9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3dfe  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3e03  ldloc.0
0x3e04  ldc.i4.0
0x3e05  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x3e0a  ldloc.0
0x3e0b  ldc.i4.1
0x3e0c  ldstr    aDocumentmanage// "DocumentManagement.Button_Label_Create"
0x3e11  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3e16  ldloc.0
0x3e17  ldc.i4.2
0x3e18  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x3e1d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3e22  ldarg.0
0x3e23  ldarg.0
0x3e24  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3e29  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3e2e  ldstr    aOtype// "oType"
0x3e33  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3e38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3e3d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3e42  stfld    int32 Microsoft.Crm.Service.Web.CreateCalendarDialogPage::_ObjType
0x3e47  ldarg.0
0x3e48  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3e4d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3e52  ldstr    aServicecalenda// "serviceCalendarType"
0x3e57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3e5c  brfalse.s loc_3EA6
0x3e5e  ldarg.0
0x3e5f  ldarg.0
0x3e60  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3e65  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3e6a  ldstr    aServicecalenda// "serviceCalendarType"
0x3e6f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3e74  callvirt instance string [mscorlib]System.Object::ToString()
0x3e79  stfld    string Microsoft.Crm.Service.Web.CreateCalendarDialogPage::_serviceCalendarType
0x3e7e  ldarg.0
0x3e7f  ldfld    string Microsoft.Crm.Service.Web.CreateCalendarDialogPage::_serviceCalendarType
0x3e84  ldstr    a2// "2"
0x3e89  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e8e  brfalse.s loc_3EA6
0x3e90  ldloc.0
0x3e91  ldarg.0
0x3e92  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3e97  ldstr    aSmHolidaySched_0// "SM_Holiday_Schedule_Dialog_Title"
0x3e9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ea1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3ea6  ldarg.0
0x3ea7  ldarg.0
0x3ea8  ldfld    int32 Microsoft.Crm.Service.Web.CreateCalendarDialogPage::_ObjType
0x3ead  ldc.i4.1
0x3eae  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3eb3  stfld    string Microsoft.Crm.Service.Web.CreateCalendarDialogPage::_ObjName
0x3eb8  ldarg.0
0x3eb9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3ebe  ldstr    aScheduleplanni// "SchedulePlanning"
0x3ec3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x3ec8  ret
```
