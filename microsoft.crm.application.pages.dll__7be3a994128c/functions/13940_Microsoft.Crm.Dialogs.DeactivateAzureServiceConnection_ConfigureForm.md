# Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::ConfigureForm

- ea: `0x13940`
- end: `0x13b7d`
- name: `Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::ConfigureForm`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13940`

## string_xrefs

- `0x13a12`: `text/xml`
- `0x13a65`: `azureserviceconnection`
- `0x13a9c`: `Dialog_Deactivate_AzureServiceConnection_Confirmation_Title`
- `0x13acf`: `Dialog_Deactivate_RecommendationConnection_Message`
- `0x13af5`: `Dialog_Deactivate_Model_RecommendationConnection_Message`

## pseudocode

```c

```

## disassembly

```asm
0x13940  ldarg.0
0x13941  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x13946  ldarg.0
0x13947  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1394c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13951  ldstr    aIobjtype// "iObjType"
0x13956  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1395b  brfalse.s loc_13990
0x1395d  ldarg.0
0x1395e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13963  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13968  ldstr    aIobjtype// "iObjType"
0x1396d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13972  ldc.i4.7
0x13973  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13978  ldarg.0
0x13979  ldflda   int32 Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::ObjType
0x1397e  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x13983  brtrue.s loc_13990
0x13985  ldarg.0
0x13986  ldc.i4   0x26D0
0x1398b  stfld    int32 Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::ObjType
0x13990  ldarg.0
0x13991  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13996  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1399b  ldstr    aIid// "iId"
0x139a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x139a5  brfalse.s loc_139C8
0x139a7  ldarg.0
0x139a8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139ad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x139b2  ldstr    aIid// "iId"
0x139b7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x139bc  ldarg.0
0x139bd  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::AzureServiceConnectionId
0x139c2  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x139c7  pop
0x139c8  ldarg.0
0x139c9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139ce  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x139d3  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x139d8  ldc.i4.0
0x139d9  conv.i8
0x139da  ble.s    loc_13A4A
0x139dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x139e1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x139e6  ldarg.0
0x139e7  ldfld    int32 Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::ObjType
0x139ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x139f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x139f6  pop
0x139f7  ldc.i4.1
0x139f8  stloc.3
0x139f9  ldarg.0
0x139fa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::AzureServiceConnectionId
0x139ff  ldc.i4.1
0x13a00  ldc.i4.2
0x13a01  ldloc.3
0x13a02  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a07  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetStateAzureServiceConnection(valuetype [mscorlib]System.Guid, int32, int32, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a0c  ldarg.0
0x13a0d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x13a12  ldstr    aTextXml// "text/xml"
0x13a17  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x13a1c  ldarg.0
0x13a1d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x13a22  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x13a27  ldarg.0
0x13a28  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x13a2d  ldstr    aOk// "<ok/>"
0x13a32  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x13a37  ldarg.0
0x13a38  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x13a3d  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x13a42  leave.s  loc_13A4A
0x13a44  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x13a49  throw
0x13a4a  ldarg.0
0x13a4b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x13a50  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x13a55  stloc.0
0x13a56  ldc.i4.1
0x13a57  newarr   [mscorlib]System.String
0x13a5c  dup
0x13a5d  ldc.i4.0
0x13a5e  ldstr    aConnectiontype// "connectiontype"
0x13a63  stelem.ref
0x13a64  stloc.1
0x13a65  ldstr    aAzureserviceco// "azureserviceconnection"
0x13a6a  ldarg.0
0x13a6b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::AzureServiceConnectionId
0x13a70  ldloc.1
0x13a71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a76  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a7b  ldstr    aConnectiontype// "connectiontype"
0x13a80  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x13a85  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a8a  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x13a8f  stloc.2
0x13a90  ldloc.0
0x13a91  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13a96  ldarg.0
0x13a97  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13a9c  ldstr    aDialogDeactiva_19// "Dialog_Deactivate_AzureServiceConnectio"...
0x13aa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13aa6  ldc.i4.0
0x13aa7  newarr   [mscorlib]System.Object
0x13aac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13ab1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x13ab6  ldloc.2
0x13ab7  ldc.i4.1
0x13ab8  beq.s    loc_13AC3
0x13aba  ldloc.2
0x13abb  ldc.i4.2
0x13abc  beq.s    loc_13B11
0x13abe  br       loc_13B5D
0x13ac3  ldloc.0
0x13ac4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13ac9  ldarg.0
0x13aca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13acf  ldstr    aDialogDeactiva_20// "Dialog_Deactivate_RecommendationConnect"...
0x13ad4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13ad9  ldc.i4.0
0x13ada  newarr   [mscorlib]System.Object
0x13adf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13ae4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x13ae9  ldarg.0
0x13aea  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13aef  ldarg.0
0x13af0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13af5  ldstr    aDialogDeactiva_21// "Dialog_Deactivate_Model_RecommendationC"...
0x13afa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13aff  ldc.i4.0
0x13b00  newarr   [mscorlib]System.Object
0x13b05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13b0a  stfld    string Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::DeactivateModelConfirmationMessage
0x13b0f  br.s     loc_13B5D
0x13b11  ldloc.0
0x13b12  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13b17  ldarg.0
0x13b18  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13b1d  ldstr    aDialogDeactiva_22// "Dialog_Deactivate_TextAnalyticsConnecti"...
0x13b22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13b27  ldc.i4.0
0x13b28  newarr   [mscorlib]System.Object
0x13b2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13b32  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x13b37  ldarg.0
0x13b38  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13b3d  ldarg.0
0x13b3e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13b43  ldstr    aDialogDeactiva_23// "Dialog_Deactivate_Model_TextAnalyticsCo"...
0x13b48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13b4d  ldc.i4.0
0x13b4e  newarr   [mscorlib]System.Object
0x13b53  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13b58  stfld    string Microsoft.Crm.Dialogs.DeactivateAzureServiceConnection::DeactivateModelConfirmationMessage
0x13b5d  ldloc.0
0x13b5e  ldc.i4.0
0x13b5f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x13b64  ldloc.0
0x13b65  ldc.i4.1
0x13b66  ldstr    aButtonLabelDea// "Button_Label_Deactivate"
0x13b6b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x13b70  ldloc.0
0x13b71  ldc.i4.2
0x13b72  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x13b77  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x13b7c  ret
```
