# Microsoft.Crm.Dialogs.RejectQueueDialogPage::ConfigureForm

- ea: `0x53a0`
- end: `0x5579`
- name: `Microsoft.Crm.Dialogs.RejectQueueDialogPage::ConfigureForm`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x53a0`

## string_xrefs

- `0x54cc`: `XML loaded from the stream returned String.Empty.`
- `0x54d6`: `XML loaded from the stream returned String.Empty.`
- `0x5491`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x53a0  ldarg.0
0x53a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x53a6  ldarg.0
0x53a7  ldarg.0
0x53a8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53ad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53b2  ldstr    aItotal// "iTotal"
0x53b7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53bc  ldc.i4.7
0x53bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53c2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x53c7  stfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::Total
0x53cc  ldarg.0
0x53cd  ldarg.0
0x53ce  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53d3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53d8  ldstr    aIobjtype// "iObjType"
0x53dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53e2  ldc.i4.7
0x53e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53e8  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x53ed  stfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjType
0x53f2  ldarg.0
0x53f3  ldfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::Total
0x53f8  ldc.i4.1
0x53f9  beq.s    loc_540F
0x53fb  ldarg.0
0x53fc  ldarg.0
0x53fd  ldfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjType
0x5402  ldc.i4.2
0x5403  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x5408  stfld    string Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjName
0x540d  br.s     loc_5421
0x540f  ldarg.0
0x5410  ldarg.0
0x5411  ldfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjType
0x5416  ldc.i4.1
0x5417  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x541c  stfld    string Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjName
0x5421  ldarg.0
0x5422  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5427  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x542c  stloc.1
0x542d  ldloc.1
0x542e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x5433  ldc.i4.0
0x5434  conv.i8
0x5435  ble      loc_54EE
0x543a  ldloc.1
0x543b  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x5440  stloc.2
0x5441  ldloc.2
0x5442  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5447  brfalse.s loc_54C3
0x5449  ldarg.0
0x544a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x544f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5454  ldstr    aIid// "iId"
0x5459  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x545e  stloc.3
0x545f  ldarg.0
0x5460  ldfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjType
0x5465  stloc.s  4
0x5467  ldloc.s  4
0x5469  ldc.i4   0x7E4
0x546e  bne.un.s loc_548B
0x5470  ldstr    aQueue// "queue"
0x5475  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x547a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x547f  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Queue::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x5484  ldloc.3
0x5485  ldc.i4.0
0x5486  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Queue::ApproveOrReject(string, bool)
0x548b  ldarg.0
0x548c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x5491  ldstr    aTextXml// "text/xml"
0x5496  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x549b  ldarg.0
0x549c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x54a1  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x54a6  ldarg.0
0x54a7  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x54ac  ldstr    aOk// "<ok/>"
0x54b1  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x54b6  ldarg.0
0x54b7  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x54bc  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x54c1  br.s     loc_54E6
0x54c3  ldloc.2
0x54c4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x54c9  ldc.i4.0
0x54ca  cgt.un
0x54cc  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x54d1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x54d6  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x54db  ldc.i4   0x80049002
0x54e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x54e5  throw
0x54e6  leave.s  loc_54FA
0x54e8  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x54ed  throw
0x54ee  leave.s  loc_54FA
0x54f0  ldloc.1
0x54f1  brfalse.s loc_54F9
0x54f3  ldloc.1
0x54f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54f9  endfinally
0x54fa  ldarg.0
0x54fb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5500  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x5505  stloc.0
0x5506  ldloc.0
0x5507  ldarg.0
0x5508  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x550d  ldstr    aDialogRejectem// "Dialog_RejectEmail_Title"
0x5512  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5517  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x551c  ldloc.0
0x551d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5522  ldarg.0
0x5523  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5528  ldstr    aDialogRejectem_0// "Dialog_RejectEmail_Description"
0x552d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5532  ldc.i4.2
0x5533  newarr   [mscorlib]System.Object
0x5538  dup
0x5539  ldc.i4.0
0x553a  ldarg.0
0x553b  ldfld    int32 Microsoft.Crm.Dialogs.RejectQueueDialogPage::Total
0x5540  box      [mscorlib]System.Int32
0x5545  stelem.ref
0x5546  dup
0x5547  ldc.i4.1
0x5548  ldarg.0
0x5549  ldfld    string Microsoft.Crm.Dialogs.RejectQueueDialogPage::ObjName
0x554e  stelem.ref
0x554f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5554  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x5559  ldloc.0
0x555a  ldc.i4.0
0x555b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x5560  ldloc.0
0x5561  ldc.i4.1
0x5562  ldstr    aButtonLabelRej// "Button_Label_Reject_User"
0x5567  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x556c  ldloc.0
0x556d  ldc.i4.2
0x556e  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x5573  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x5578  ret
```
