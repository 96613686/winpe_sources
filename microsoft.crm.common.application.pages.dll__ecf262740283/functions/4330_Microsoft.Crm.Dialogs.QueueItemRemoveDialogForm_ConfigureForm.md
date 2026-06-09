# Microsoft.Crm.Dialogs.QueueItemRemoveDialogForm::ConfigureForm

- ea: `0x4330`
- end: `0x44ab`
- name: `Microsoft.Crm.Dialogs.QueueItemRemoveDialogForm::ConfigureForm`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4330`

## string_xrefs

- `0x43e9`: `XML loaded from the stream returned String.Empty.`
- `0x43f3`: `XML loaded from the stream returned String.Empty.`
- `0x43ae`: `text/xml`
- `0x4420`: `Button_Label_Remove`
- `0x443d`: `Dialog_QueueItemRemove_Title`
- `0x445c`: `Dialog_QueueItemRemoveNew_Description_Single`
- `0x4478`: `Dialog_QueueItemRemoveNew_Description_Plural`

## pseudocode

```c

```

## disassembly

```asm
0x4330  ldarg.0
0x4331  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x4336  ldarg.0
0x4337  ldarg.0
0x4338  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x433d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4342  ldstr    aItotal// "iTotal"
0x4347  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x434c  ldc.i4.7
0x434d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4352  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x4357  stfld    int32 Microsoft.Crm.Dialogs.QueueItemRemoveDialogForm::iTotal
0x435c  ldarg.0
0x435d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4362  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x4367  stloc.0
0x4368  ldloc.0
0x4369  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x436e  ldc.i4.0
0x436f  conv.i8
0x4370  ble      loc_440B
0x4375  ldloc.0
0x4376  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x437b  stloc.2
0x437c  ldloc.2
0x437d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4382  brfalse.s loc_43E0
0x4384  ldarg.0
0x4385  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x438a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x438f  ldstr    aIid// "iId"
0x4394  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4399  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x439e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x43a3  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRemoveFromQueue(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x43a8  ldarg.0
0x43a9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x43ae  ldstr    aTextXml// "text/xml"
0x43b3  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x43b8  ldarg.0
0x43b9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x43be  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x43c3  ldarg.0
0x43c4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x43c9  ldstr    aOk// "<ok/>"
0x43ce  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x43d3  ldarg.0
0x43d4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x43d9  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x43de  br.s     loc_4403
0x43e0  ldloc.2
0x43e1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x43e6  ldc.i4.0
0x43e7  cgt.un
0x43e9  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x43ee  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x43f3  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x43f8  ldc.i4   0x80049002
0x43fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4402  throw
0x4403  leave.s  loc_440B
0x4405  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x440a  throw
0x440b  ldarg.0
0x440c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4411  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x4416  stloc.1
0x4417  ldloc.1
0x4418  ldc.i4.0
0x4419  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x441e  ldloc.1
0x441f  ldc.i4.1
0x4420  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x4425  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x442a  ldloc.1
0x442b  ldc.i4.2
0x442c  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x4431  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x4436  ldloc.1
0x4437  ldarg.0
0x4438  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x443d  ldstr    aDialogQueueite_2// "Dialog_QueueItemRemove_Title"
0x4442  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4447  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x444c  ldarg.0
0x444d  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemRemoveDialogForm::iTotal
0x4452  ldc.i4.1
0x4453  bne.un.s loc_446C
0x4455  ldloc.1
0x4456  ldarg.0
0x4457  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x445c  ldstr    aDialogQueueite_3// "Dialog_QueueItemRemoveNew_Description_S"...
0x4461  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4466  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x446b  ret
0x446c  ldloc.1
0x446d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4472  ldarg.0
0x4473  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4478  ldstr    aDialogQueueite_4// "Dialog_QueueItemRemoveNew_Description_P"...
0x447d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4482  ldc.i4.1
0x4483  newarr   [mscorlib]System.Object
0x4488  dup
0x4489  ldc.i4.0
0x448a  ldarg.0
0x448b  ldflda   int32 Microsoft.Crm.Dialogs.QueueItemRemoveDialogForm::iTotal
0x4490  ldstr    aD// "D"
0x4495  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x449a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x449f  stelem.ref
0x44a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44a5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x44aa  ret
```
