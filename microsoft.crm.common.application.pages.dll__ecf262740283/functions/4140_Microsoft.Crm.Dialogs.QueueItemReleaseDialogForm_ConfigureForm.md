# Microsoft.Crm.Dialogs.QueueItemReleaseDialogForm::ConfigureForm

- ea: `0x4140`
- end: `0x42bb`
- name: `Microsoft.Crm.Dialogs.QueueItemReleaseDialogForm::ConfigureForm`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4140`

## string_xrefs

- `0x41f9`: `XML loaded from the stream returned String.Empty.`
- `0x4203`: `XML loaded from the stream returned String.Empty.`
- `0x41be`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x4140  ldarg.0
0x4141  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x4146  ldarg.0
0x4147  ldarg.0
0x4148  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x414d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4152  ldstr    aItotal// "iTotal"
0x4157  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x415c  ldc.i4.7
0x415d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4162  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x4167  stfld    int32 Microsoft.Crm.Dialogs.QueueItemReleaseDialogForm::iTotal
0x416c  ldarg.0
0x416d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4172  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x4177  stloc.0
0x4178  ldloc.0
0x4179  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x417e  ldc.i4.0
0x417f  conv.i8
0x4180  ble      loc_421B
0x4185  ldloc.0
0x4186  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x418b  stloc.2
0x418c  ldloc.2
0x418d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4192  brfalse.s loc_41F0
0x4194  ldarg.0
0x4195  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x419a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x419f  ldstr    aIid// "iId"
0x41a4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x41a9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x41ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x41b3  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemReleaseToQueue(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41b8  ldarg.0
0x41b9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x41be  ldstr    aTextXml// "text/xml"
0x41c3  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x41c8  ldarg.0
0x41c9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x41ce  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x41d3  ldarg.0
0x41d4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x41d9  ldstr    aOk// "<ok/>"
0x41de  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x41e3  ldarg.0
0x41e4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x41e9  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x41ee  br.s     loc_4213
0x41f0  ldloc.2
0x41f1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x41f6  ldc.i4.0
0x41f7  cgt.un
0x41f9  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x41fe  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4203  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x4208  ldc.i4   0x80049002
0x420d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4212  throw
0x4213  leave.s  loc_421B
0x4215  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x421a  throw
0x421b  ldarg.0
0x421c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4221  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x4226  stloc.1
0x4227  ldloc.1
0x4228  ldc.i4.0
0x4229  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x422e  ldloc.1
0x422f  ldc.i4.1
0x4230  ldstr    aButtonLabelRel// "Button_Label_Release"
0x4235  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x423a  ldloc.1
0x423b  ldc.i4.2
0x423c  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x4241  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x4246  ldloc.1
0x4247  ldarg.0
0x4248  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x424d  ldstr    aDialogQueueite// "Dialog_QueueItemRelease_Title"
0x4252  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4257  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x425c  ldarg.0
0x425d  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemReleaseDialogForm::iTotal
0x4262  ldc.i4.1
0x4263  bne.un.s loc_427C
0x4265  ldloc.1
0x4266  ldarg.0
0x4267  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x426c  ldstr    aDialogQueueite_0// "Dialog_QueueItemReleaseNew_Description_"...
0x4271  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4276  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x427b  ret
0x427c  ldloc.1
0x427d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4282  ldarg.0
0x4283  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4288  ldstr    aDialogQueueite_1// "Dialog_QueueItemReleaseNew_Description_"...
0x428d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4292  ldc.i4.1
0x4293  newarr   [mscorlib]System.Object
0x4298  dup
0x4299  ldc.i4.0
0x429a  ldarg.0
0x429b  ldflda   int32 Microsoft.Crm.Dialogs.QueueItemReleaseDialogForm::iTotal
0x42a0  ldstr    aD// "D"
0x42a5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x42aa  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x42af  stelem.ref
0x42b0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42b5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x42ba  ret
```
