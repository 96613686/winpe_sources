# Microsoft.Crm.Dialogs.AddToQueueDialogForm::ConfigureForm

- ea: `0x1dd0`
- end: `0x207d`
- name: `Microsoft.Crm.Dialogs.AddToQueueDialogForm::ConfigureForm`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1dd0`

## string_xrefs

- `0x1f64`: `XML loaded from the stream returned String.Empty.`
- `0x1f6e`: `XML loaded from the stream returned String.Empty.`
- `0x1f28`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldarg.0
0x1dd1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1dd6  ldarg.0
0x1dd7  ldarg.0
0x1dd8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ddd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1de2  ldstr    aItotal// "iTotal"
0x1de7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1dec  ldc.i4.7
0x1ded  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1df2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1df7  stfld    int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::iTotal
0x1dfc  ldarg.0
0x1dfd  ldarg.0
0x1dfe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e03  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e08  ldstr    aIobjtype// "iObjType"
0x1e0d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e12  ldc.i4.7
0x1e13  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e18  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1e1d  stfld    int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::objectType
0x1e22  ldarg.0
0x1e23  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e28  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e2d  ldstr    aSsubtypes// "sSubTypes"
0x1e32  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e37  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e3c  brtrue.s loc_1E97
0x1e3e  ldarg.0
0x1e3f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e44  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e49  ldstr    aSsubtypes// "sSubTypes"
0x1e4e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e53  ldc.i4.1
0x1e54  newarr   [mscorlib]System.Char
0x1e59  dup
0x1e5a  ldc.i4.0
0x1e5b  ldc.i4.s 0x2C
0x1e5d  stelem.i2
0x1e5e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1e63  stloc.3
0x1e64  ldarg.0
0x1e65  ldloc.3
0x1e66  ldarg.0
0x1e67  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e6c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e71  ldstr    aIindex// "iIndex"
0x1e76  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e7b  ldc.i4.7
0x1e7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e81  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1e86  ldelem.ref
0x1e87  ldc.i4.7
0x1e88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e8d  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1e92  stfld    int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::objectType
0x1e97  ldarg.0
0x1e98  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e9d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1ea2  stloc.1
0x1ea3  ldloc.1
0x1ea4  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1ea9  ldc.i4.0
0x1eaa  conv.i8
0x1eab  ble      loc_1F86
0x1eb0  ldloc.1
0x1eb1  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1eb6  stloc.s  4
0x1eb8  ldloc.s  4
0x1eba  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1ebf  brfalse  loc_1F5A
0x1ec4  ldarg.0
0x1ec5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1eca  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ecf  ldstr    aIid// "iId"
0x1ed4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ed9  ldarg.0
0x1eda  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1edf  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ee4  ldstr    aQueueid_0// "queueId"
0x1ee9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1eee  stloc.s  5
0x1ef0  ldarg.0
0x1ef1  ldfld    int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::objectType
0x1ef6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1efb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f00  stloc.0
0x1f01  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f06  ldloc.0
0x1f07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x1f0c  ldloc.s  5
0x1f0e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f13  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f1d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::AddToQueue(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f22  ldarg.0
0x1f23  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f28  ldstr    aTextXml// "text/xml"
0x1f2d  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1f32  ldarg.0
0x1f33  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f38  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1f3d  ldarg.0
0x1f3e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f43  ldstr    aOk// "<ok/>"
0x1f48  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1f4d  ldarg.0
0x1f4e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f53  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1f58  br.s     loc_1F7E
0x1f5a  ldloc.s  4
0x1f5c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1f61  ldc.i4.0
0x1f62  cgt.un
0x1f64  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1f69  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1f6e  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1f73  ldc.i4   0x80049002
0x1f78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f7d  throw
0x1f7e  leave.s  loc_1F86
0x1f80  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1f85  throw
0x1f86  ldarg.0
0x1f87  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.AddToQueueDialogForm::crmQueueLookup
0x1f8c  ldc.i4.1
0x1f8d  newarr   [mscorlib]System.Int32
0x1f92  dup
0x1f93  ldc.i4.0
0x1f94  ldc.i4   0x7E4
0x1f99  stelem.i4
0x1f9a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1f9f  ldarg.0
0x1fa0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.AddToQueueDialogForm::crmQueueLookup
0x1fa5  ldc.i4.0
0x1fa6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x1fab  ldarg.0
0x1fac  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.AddToQueueDialogForm::crmQueueLookup
0x1fb1  ldarg.0
0x1fb2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fb7  ldstr    aDialogAddtoque// "Dialog_AddToQueue_LabelDetails"
0x1fbc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fc1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x1fc6  ldarg.0
0x1fc7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.AddToQueueDialogForm::crmQueueLookup
0x1fcc  ldstr    aF374f81400a244// "f374f814-00a2-44ed-8b88-13f34e202e79"
0x1fd1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1fd6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultViewId(valuetype [mscorlib]System.Guid)
0x1fdb  ldarg.0
0x1fdc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1fe1  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1fe6  stloc.2
0x1fe7  ldloc.2
0x1fe8  ldarg.0
0x1fe9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fee  ldstr    aDialogAddtoque_0// "Dialog_AddToQueue_Title"
0x1ff3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ff8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1ffd  ldloc.2
0x1ffe  ldc.i4.0
0x1fff  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2004  ldloc.2
0x2005  ldc.i4.1
0x2006  ldstr    aButtonLabelAdd// "Button_Label_Add"
0x200b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x2010  ldloc.2
0x2011  ldc.i4.2
0x2012  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2017  ldloc.2
0x2018  ldc.i4.1
0x2019  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DisabledButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x201e  ldarg.0
0x201f  ldfld    int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::iTotal
0x2024  ldc.i4.1
0x2025  bne.un.s loc_203E
0x2027  ldloc.2
0x2028  ldarg.0
0x2029  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x202e  ldstr    aDialogAddtoque_1// "Dialog_AddToQueue_Description_Single"
0x2033  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2038  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x203d  ret
0x203e  ldloc.2
0x203f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2044  ldarg.0
0x2045  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x204a  ldstr    aDialogAddtoque_2// "Dialog_AddToQueue_Description_Plural"
0x204f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2054  ldc.i4.1
0x2055  newarr   [mscorlib]System.Object
0x205a  dup
0x205b  ldc.i4.0
0x205c  ldarg.0
0x205d  ldflda   int32 Microsoft.Crm.Dialogs.AddToQueueDialogForm::iTotal
0x2062  ldstr    aD// "D"
0x2067  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x206c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2071  stelem.ref
0x2072  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2077  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x207c  ret
```
