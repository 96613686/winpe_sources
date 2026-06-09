# Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::ConfigureForm

- ea: `0x48d0`
- end: `0x4ae7`
- name: `Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::ConfigureForm`
- size: `535`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x48d0`

## string_xrefs

- `0x49ff`: `XML loaded from the stream returned String.Empty.`
- `0x4a09`: `XML loaded from the stream returned String.Empty.`
- `0x49c4`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x48d0  ldarg.0
0x48d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x48d6  ldarg.0
0x48d7  ldarg.0
0x48d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x48dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x48e2  ldstr    aItotal// "iTotal"
0x48e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x48ec  ldc.i4.7
0x48ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x48f2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x48f7  stfld    int32 Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::iTotal
0x48fc  ldarg.0
0x48fd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4902  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x4907  stloc.0
0x4908  ldloc.0
0x4909  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x490e  ldc.i4.0
0x490f  conv.i8
0x4910  ble      loc_4A21
0x4915  ldloc.0
0x4916  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x491b  stloc.2
0x491c  ldloc.2
0x491d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4922  brfalse  loc_49F6
0x4927  ldarg.0
0x4928  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x492d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4932  ldstr    aIid// "iId"
0x4937  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x493c  ldarg.0
0x493d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4942  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4947  ldstr    aIsworkerme// "isworkerme"
0x494c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4951  ldstr    a1// "1"
0x4956  call     bool [mscorlib]System.String::op_Equality(string, string)
0x495b  dup
0x495c  brtrue.s loc_497A
0x495e  ldarg.0
0x495f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4964  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4969  ldstr    aWorkerid// "workerid"
0x496e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4973  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4978  br.s     loc_4985
0x497a  ldarg.0
0x497b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x4980  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x4985  stloc.3
0x4986  brtrue.s loc_49A9
0x4988  ldarg.0
0x4989  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x498e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4993  ldstr    aWorkertype// "workertype"
0x4998  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x499d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49a2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x49a7  br.s     loc_49AA
0x49a9  ldc.i4.8
0x49aa  stloc.s  4
0x49ac  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x49b1  ldloc.3
0x49b2  ldloc.s  4
0x49b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x49b9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::QueueItemWorkOn(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x49be  ldarg.0
0x49bf  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x49c4  ldstr    aTextXml// "text/xml"
0x49c9  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x49ce  ldarg.0
0x49cf  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x49d4  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x49d9  ldarg.0
0x49da  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x49df  ldstr    aOk// "<ok/>"
0x49e4  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x49e9  ldarg.0
0x49ea  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x49ef  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x49f4  br.s     loc_4A19
0x49f6  ldloc.2
0x49f7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x49fc  ldc.i4.0
0x49fd  cgt.un
0x49ff  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x4a04  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4a09  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x4a0e  ldc.i4   0x80049002
0x4a13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4a18  throw
0x4a19  leave.s  loc_4A21
0x4a1b  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x4a20  throw
0x4a21  ldarg.0
0x4a22  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::crmUserLookup
0x4a27  ldc.i4.2
0x4a28  newarr   [mscorlib]System.Int32
0x4a2d  dup
0x4a2e  ldc.i4.0
0x4a2f  ldc.i4.8
0x4a30  stelem.i4
0x4a31  dup
0x4a32  ldc.i4.1
0x4a33  ldc.i4.s 9
0x4a35  stelem.i4
0x4a36  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x4a3b  ldarg.0
0x4a3c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::crmUserLookup
0x4a41  ldc.i4.1
0x4a42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x4a47  ldarg.0
0x4a48  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4a4d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x4a52  stloc.1
0x4a53  ldloc.1
0x4a54  ldarg.0
0x4a55  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4a5a  ldstr    aDialogQueueite_8// "Dialog_QueueItemWorkOn_Title"
0x4a5f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a64  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x4a69  ldloc.1
0x4a6a  ldc.i4.0
0x4a6b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x4a70  ldloc.1
0x4a71  ldc.i4.1
0x4a72  ldstr    aButtonLabelAss// "Button_Label_Assign"
0x4a77  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x4a7c  ldloc.1
0x4a7d  ldc.i4.2
0x4a7e  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x4a83  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x4a88  ldarg.0
0x4a89  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::iTotal
0x4a8e  ldc.i4.1
0x4a8f  bne.un.s loc_4AA8
0x4a91  ldloc.1
0x4a92  ldarg.0
0x4a93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4a98  ldstr    aDialogQueueite_9// "Dialog_QueueItemWorkOn_Description_Sing"...
0x4a9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4aa2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x4aa7  ret
0x4aa8  ldloc.1
0x4aa9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4aae  ldarg.0
0x4aaf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4ab4  ldstr    aDialogQueueite_10// "Dialog_QueueItemWorkOn_Description_Plur"...
0x4ab9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4abe  ldc.i4.1
0x4abf  newarr   [mscorlib]System.Object
0x4ac4  dup
0x4ac5  ldc.i4.0
0x4ac6  ldarg.0
0x4ac7  ldflda   int32 Microsoft.Crm.Dialogs.QueueItemWorkOnDialogForm::iTotal
0x4acc  ldstr    aD// "D"
0x4ad1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4ad6  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x4adb  stelem.ref
0x4adc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ae1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x4ae6  ret
```
