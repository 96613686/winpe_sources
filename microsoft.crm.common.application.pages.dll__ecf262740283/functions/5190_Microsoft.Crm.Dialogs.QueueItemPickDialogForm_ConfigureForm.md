# Microsoft.Crm.Dialogs.QueueItemPickDialogForm::ConfigureForm

- ea: `0x5190`
- end: `0x534d`
- name: `Microsoft.Crm.Dialogs.QueueItemPickDialogForm::ConfigureForm`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5190`

## string_xrefs

- `0x528b`: `XML loaded from the stream returned String.Empty.`
- `0x5295`: `XML loaded from the stream returned String.Empty.`
- `0x5250`: `text/xml`
- `0x5207`: `isQueueItemRemove`
- `0x52c0`: `Dialog_QueueItemPick_Title`
- `0x52fe`: `Dialog_QueueItemPick_Description_Single`
- `0x531a`: `Dialog_QueueItemPick_Description_Plural`

## pseudocode

```c

```

## disassembly

```asm
0x5190  ldarg.0
0x5191  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x5196  ldarg.0
0x5197  ldarg.0
0x5198  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x519d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51a2  ldstr    aItotal// "iTotal"
0x51a7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51ac  ldc.i4.7
0x51ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51b2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x51b7  stfld    int32 Microsoft.Crm.Dialogs.QueueItemPickDialogForm::iTotal
0x51bc  ldarg.0
0x51bd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51c2  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x51c7  stloc.0
0x51c8  ldloc.0
0x51c9  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x51ce  ldc.i4.0
0x51cf  conv.i8
0x51d0  ble      loc_52AD
0x51d5  ldloc.0
0x51d6  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x51db  stloc.2
0x51dc  ldloc.2
0x51dd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x51e2  brfalse  loc_5282
0x51e7  ldarg.0
0x51e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51ed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51f2  ldstr    aIid// "iId"
0x51f7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51fc  ldarg.0
0x51fd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5202  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5207  ldstr    aIsqueueitemrem// "isQueueItemRemove"
0x520c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5211  ldstr    a1// "1"
0x5216  call     bool [mscorlib]System.String::op_Equality(string, string)
0x521b  stloc.3
0x521c  ldloca.s 4
0x521e  ldarg.0
0x521f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5224  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5229  ldstr    aWorkerid// "workerid"
0x522e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5233  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5238  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x523d  ldloc.s  4
0x523f  ldloc.3
0x5240  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5245  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemPickAndRemove(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x524a  ldarg.0
0x524b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x5250  ldstr    aTextXml// "text/xml"
0x5255  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x525a  ldarg.0
0x525b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x5260  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x5265  ldarg.0
0x5266  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x526b  ldstr    aOk// "<ok/>"
0x5270  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x5275  ldarg.0
0x5276  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x527b  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x5280  br.s     loc_52A5
0x5282  ldloc.2
0x5283  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5288  ldc.i4.0
0x5289  cgt.un
0x528b  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x5290  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x5295  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x529a  ldc.i4   0x80049002
0x529f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x52a4  throw
0x52a5  leave.s  loc_52AD
0x52a7  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x52ac  throw
0x52ad  ldarg.0
0x52ae  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x52b3  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x52b8  stloc.1
0x52b9  ldloc.1
0x52ba  ldarg.0
0x52bb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52c0  ldstr    aDialogQueueite_11// "Dialog_QueueItemPick_Title"
0x52c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52ca  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x52cf  ldloc.1
0x52d0  ldc.i4.0
0x52d1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x52d6  ldloc.1
0x52d7  ldc.i4.1
0x52d8  ldstr    aButtonLabelPic// "Button_Label_Pick"
0x52dd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x52e2  ldloc.1
0x52e3  ldc.i4.2
0x52e4  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x52e9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x52ee  ldarg.0
0x52ef  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemPickDialogForm::iTotal
0x52f4  ldc.i4.1
0x52f5  bne.un.s loc_530E
0x52f7  ldloc.1
0x52f8  ldarg.0
0x52f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52fe  ldstr    aDialogQueueite_12// "Dialog_QueueItemPick_Description_Single"
0x5303  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5308  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x530d  ret
0x530e  ldloc.1
0x530f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5314  ldarg.0
0x5315  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x531a  ldstr    aDialogQueueite_13// "Dialog_QueueItemPick_Description_Plural"
0x531f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5324  ldc.i4.1
0x5325  newarr   [mscorlib]System.Object
0x532a  dup
0x532b  ldc.i4.0
0x532c  ldarg.0
0x532d  ldflda   int32 Microsoft.Crm.Dialogs.QueueItemPickDialogForm::iTotal
0x5332  ldstr    aD// "D"
0x5337  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x533c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x5341  stelem.ref
0x5342  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5347  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x534c  ret
```
