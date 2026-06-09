# Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ConfigureForm

- ea: `0xaef0`
- end: `0xb1b0`
- name: `Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ConfigureForm`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xaef0`

## string_xrefs

- `0xafed`: `text/xml`
- `0xb04c`: `azureserviceconnection`
- `0xb083`: `Dialog_Activate_AzureServiceConnection_Confirmation_Title`
- `0xb0b6`: `Dialog_Activate_RecommendationConnection_Message`
- `0xb0dc`: `Dialog_Activate_Model_RecommendationConnection_Message`
- `0xb102`: `Dialog_Activate_Model_RecommendationConnection_Checkbox`

## pseudocode

```c

```

## disassembly

```asm
0xaef0  ldarg.0
0xaef1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xaef6  ldarg.0
0xaef7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaefc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf01  ldstr    aIobjtype// "iObjType"
0xaf06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf0b  brfalse.s loc_AF40
0xaf0d  ldarg.0
0xaf0e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf13  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf18  ldstr    aIobjtype// "iObjType"
0xaf1d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf22  ldc.i4.7
0xaf23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf28  ldarg.0
0xaf29  ldflda   int32 Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ObjType
0xaf2e  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xaf33  brtrue.s loc_AF40
0xaf35  ldarg.0
0xaf36  ldc.i4   0x26D0
0xaf3b  stfld    int32 Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ObjType
0xaf40  ldarg.0
0xaf41  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf46  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf4b  ldstr    aIid// "iId"
0xaf50  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf55  brfalse.s loc_AF78
0xaf57  ldarg.0
0xaf58  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf5d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf62  ldstr    aIid// "iId"
0xaf67  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaf6c  ldarg.0
0xaf6d  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::AzureServiceConnectionId
0xaf72  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xaf77  pop
0xaf78  ldarg.0
0xaf79  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf7e  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xaf83  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xaf88  ldc.i4.0
0xaf89  conv.i8
0xaf8a  ble      loc_B031
0xaf8f  ldc.i4.0
0xaf90  stloc.3
0xaf91  ldarg.0
0xaf92  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf97  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf9c  ldstr    aCascademodelst// "cascadeModelState"
0xafa1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafa6  brfalse.s loc_AFC8
0xafa8  ldarg.0
0xafa9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xafae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xafb3  ldstr    aCascademodelst// "cascadeModelState"
0xafb8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafbd  ldloca.s 3
0xafbf  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0xafc4  brtrue.s loc_AFC8
0xafc6  ldc.i4.0
0xafc7  stloc.3
0xafc8  ldarg.0
0xafc9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::AzureServiceConnectionId
0xafce  ldc.i4.0
0xafcf  ldc.i4.1
0xafd0  ldloc.3
0xafd1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xafd6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetStateAzureServiceConnection(valuetype [mscorlib]System.Guid, int32, int32, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xafdb  ldarg.0
0xafdc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::AzureServiceConnectionId
0xafe1  ldc.i4.1
0xafe2  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.AnalyticsUtility::UpdateConnectionTestStatus(valuetype [mscorlib]System.Guid, bool)
0xafe7  ldarg.0
0xafe8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xafed  ldstr    aTextXml// "text/xml"
0xaff2  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xaff7  ldarg.0
0xaff8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xaffd  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0xb002  ldarg.0
0xb003  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xb008  ldstr    aOk// "<ok/>"
0xb00d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xb012  ldarg.0
0xb013  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xb018  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0xb01d  leave.s  loc_B031
0xb01f  ldarg.0
0xb020  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::AzureServiceConnectionId
0xb025  ldc.i4.0
0xb026  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.AnalyticsUtility::UpdateConnectionTestStatus(valuetype [mscorlib]System.Guid, bool)
0xb02b  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xb030  throw
0xb031  ldarg.0
0xb032  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xb037  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xb03c  stloc.0
0xb03d  ldc.i4.1
0xb03e  newarr   [mscorlib]System.String
0xb043  dup
0xb044  ldc.i4.0
0xb045  ldstr    aConnectiontype// "connectiontype"
0xb04a  stelem.ref
0xb04b  stloc.1
0xb04c  ldstr    aAzureserviceco// "azureserviceconnection"
0xb051  ldarg.0
0xb052  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::AzureServiceConnectionId
0xb057  ldloc.1
0xb058  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb05d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb062  ldstr    aConnectiontype// "connectiontype"
0xb067  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb06c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb071  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0xb076  stloc.2
0xb077  ldloc.0
0xb078  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb07d  ldarg.0
0xb07e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb083  ldstr    aDialogActivate_19// "Dialog_Activate_AzureServiceConnection_"...
0xb088  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb08d  ldc.i4.0
0xb08e  newarr   [mscorlib]System.Object
0xb093  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb098  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xb09d  ldloc.2
0xb09e  ldc.i4.1
0xb09f  beq.s    loc_B0AA
0xb0a1  ldloc.2
0xb0a2  ldc.i4.2
0xb0a3  beq.s    loc_B11E
0xb0a5  br       loc_B190
0xb0aa  ldloc.0
0xb0ab  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb0b0  ldarg.0
0xb0b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb0b6  ldstr    aDialogActivate_20// "Dialog_Activate_RecommendationConnectio"...
0xb0bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb0c0  ldc.i4.0
0xb0c1  newarr   [mscorlib]System.Object
0xb0c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb0cb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xb0d0  ldarg.0
0xb0d1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb0d6  ldarg.0
0xb0d7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb0dc  ldstr    aDialogActivate_21// "Dialog_Activate_Model_RecommendationCon"...
0xb0e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb0e6  ldc.i4.0
0xb0e7  newarr   [mscorlib]System.Object
0xb0ec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb0f1  stfld    string Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ActivateModelAnalyticsMessage
0xb0f6  ldarg.0
0xb0f7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb0fc  ldarg.0
0xb0fd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb102  ldstr    aDialogActivate_22// "Dialog_Activate_Model_RecommendationCon"...
0xb107  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb10c  ldc.i4.0
0xb10d  newarr   [mscorlib]System.Object
0xb112  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb117  stfld    string Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ActivateModelConfirmationMessage
0xb11c  br.s     loc_B190
0xb11e  ldloc.0
0xb11f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb124  ldarg.0
0xb125  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb12a  ldstr    aDialogActivate_23// "Dialog_Activate_TextAnalyticsConnection"...
0xb12f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb134  ldc.i4.0
0xb135  newarr   [mscorlib]System.Object
0xb13a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb13f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xb144  ldarg.0
0xb145  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb14a  ldarg.0
0xb14b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb150  ldstr    aDialogActivate_24// "Dialog_Activate_Model_TextAnalyticsConn"...
0xb155  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb15a  ldc.i4.0
0xb15b  newarr   [mscorlib]System.Object
0xb160  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb165  stfld    string Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ActivateModelAnalyticsMessage
0xb16a  ldarg.0
0xb16b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xb170  ldarg.0
0xb171  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb176  ldstr    aDialogActivate_25// "Dialog_Activate_Model_TextAnalyticsConn"...
0xb17b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb180  ldc.i4.0
0xb181  newarr   [mscorlib]System.Object
0xb186  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb18b  stfld    string Microsoft.Crm.Dialogs.ActivateAzureServiceConnection::ActivateModelConfirmationMessage
0xb190  ldloc.0
0xb191  ldc.i4.0
0xb192  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xb197  ldloc.0
0xb198  ldc.i4.1
0xb199  ldstr    aButtonLabelAct// "Button_Label_Activate"
0xb19e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xb1a3  ldloc.0
0xb1a4  ldc.i4.2
0xb1a5  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xb1aa  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xb1af  ret
```
