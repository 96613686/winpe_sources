# Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::ConfigureForm

- ea: `0x4540`
- end: `0x4840`
- name: `Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::ConfigureForm`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4540`

## string_xrefs

- `0x46bb`: `XML loaded from the stream returned String.Empty.`
- `0x46c5`: `XML loaded from the stream returned String.Empty.`
- `0x4680`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x4540  ldarg.0
0x4541  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x4546  ldarg.0
0x4547  ldarg.0
0x4548  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x454d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4552  ldstr    aItotal// "iTotal"
0x4557  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x455c  ldc.i4.7
0x455d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4562  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x4567  stfld    int32 Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::iTotal
0x456c  ldarg.0
0x456d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4572  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x4577  stloc.0
0x4578  ldloc.0
0x4579  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x457e  ldc.i4.0
0x457f  conv.i8
0x4580  ble      loc_474E
0x4585  ldloc.0
0x4586  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x458b  stloc.2
0x458c  ldsfld   string [mscorlib]System.String::Empty
0x4591  stloc.3
0x4592  ldloc.2
0x4593  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4598  brfalse  loc_46B2
0x459d  ldarg.0
0x459e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45a3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45a8  ldstr    aIid// "iId"
0x45ad  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45b2  stloc.3
0x45b3  ldc.i4.0
0x45b4  stloc.s  4
0x45b6  ldarg.0
0x45b7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45bc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45c1  ldstr    aKeepexistingus// "keepexistinguser"
0x45c6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45cb  brfalse.s loc_45E9
0x45cd  ldarg.0
0x45ce  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45d3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45d8  ldstr    aKeepexistingus// "keepexistinguser"
0x45dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45e2  call     bool [mscorlib]System.Boolean::Parse(string)
0x45e7  stloc.s  4
0x45e9  ldarg.0
0x45ea  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45ef  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45f4  ldstr    aWorkerid// "workerid"
0x45f9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45fe  stloc.s  5
0x4600  ldloc.s  5
0x4602  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4607  brtrue.s loc_4612
0x4609  ldloc.s  5
0x460b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4610  br.s     loc_4617
0x4612  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4617  stloc.s  6
0x4619  ldloc.s  5
0x461b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4620  brtrue.s loc_4643
0x4622  ldarg.0
0x4623  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4628  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x462d  ldstr    aWorkertype// "workertype"
0x4632  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4637  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x463c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x4641  br.s     loc_4644
0x4643  ldc.i4.8
0x4644  stloc.s  7
0x4646  ldarg.0
0x4647  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x464c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4651  ldstr    aQueueid_0// "queueId"
0x4656  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x465b  stloc.s  8
0x465d  ldloc.3
0x465e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4663  ldloc.s  8
0x4665  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x466a  ldloc.s  6
0x466c  ldloc.s  7
0x466e  ldloc.s  4
0x4670  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4675  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRoute(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x467a  ldarg.0
0x467b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4680  ldstr    aTextXml// "text/xml"
0x4685  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x468a  ldarg.0
0x468b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4690  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x4695  ldarg.0
0x4696  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x469b  ldstr    aOk// "<ok/>"
0x46a0  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x46a5  ldarg.0
0x46a6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x46ab  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x46b0  br.s     loc_46D5
0x46b2  ldloc.2
0x46b3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x46b8  ldc.i4.0
0x46b9  cgt.un
0x46bb  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x46c0  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x46c5  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x46ca  ldc.i4   0x80049002
0x46cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x46d4  throw
0x46d5  leave.s  loc_474E
0x46d7  stloc.s  9
0x46d9  ldloc.s  9
0x46db  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x46e0  ldc.i4   0x80040524
0x46e5  bne.un.s loc_473E
0x46e7  ldc.i4.1
0x46e8  newarr   [mscorlib]System.String
0x46ed  dup
0x46ee  ldc.i4.0
0x46ef  ldstr    aStatecode// "statecode"
0x46f4  stelem.ref
0x46f5  stloc.s  0xA
0x46f7  ldstr    aQueueitem// "queueitem"
0x46fc  ldloc.3
0x46fd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4702  ldloc.s  0xA
0x4704  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4709  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x470e  ldstr    aStatecode// "statecode"
0x4713  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4718  castclass [mscorlib]System.String
0x471d  ldstr    aInactive// "Inactive"
0x4722  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4727  brfalse.s loc_4746
0x4729  ldstr    aCannotRouteAnI// "Cannot route an inactive queue item."
0x472e  ldc.i4   0x80040527
0x4733  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4738  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x473d  throw
0x473e  ldloc.s  9
0x4740  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x4745  throw
0x4746  leave.s  loc_474E
0x4748  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x474d  throw
0x474e  ldarg.0
0x474f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::crmUserLookup
0x4754  ldc.i4.2
0x4755  newarr   [mscorlib]System.Int32
0x475a  dup
0x475b  ldc.i4.0
0x475c  ldc.i4.8
0x475d  stelem.i4
0x475e  dup
0x475f  ldc.i4.1
0x4760  ldc.i4.s 9
0x4762  stelem.i4
0x4763  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x4768  ldarg.0
0x4769  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::crmUserLookup
0x476e  ldc.i4.0
0x476f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x4774  ldarg.0
0x4775  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::crmQueueLookup
0x477a  ldc.i4.1
0x477b  newarr   [mscorlib]System.Int32
0x4780  dup
0x4781  ldc.i4.0
0x4782  ldc.i4   0x7E4
0x4787  stelem.i4
0x4788  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x478d  ldarg.0
0x478e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::crmQueueLookup
0x4793  ldc.i4.0
0x4794  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x4799  ldarg.0
0x479a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x479f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x47a4  stloc.1
0x47a5  ldloc.1
0x47a6  ldarg.0
0x47a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x47ac  ldstr    aDialogQueueite_5// "Dialog_QueueItemRoute_Title"
0x47b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x47b6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x47bb  ldloc.1
0x47bc  ldc.i4.0
0x47bd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x47c2  ldloc.1
0x47c3  ldc.i4.1
0x47c4  ldstr    aButtonLabelRou// "Button_Label_Route"
0x47c9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x47ce  ldloc.1
0x47cf  ldc.i4.1
0x47d0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DisabledButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x47d5  ldloc.1
0x47d6  ldc.i4.2
0x47d7  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x47dc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x47e1  ldarg.0
0x47e2  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::iTotal
0x47e7  ldc.i4.1
0x47e8  bne.un.s loc_4801
0x47ea  ldloc.1
0x47eb  ldarg.0
0x47ec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x47f1  ldstr    aDialogQueueite_6// "Dialog_QueueItemRoute_Description_Singl"...
0x47f6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x47fb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x4800  ret
0x4801  ldloc.1
0x4802  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4807  ldarg.0
0x4808  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x480d  ldstr    aDialogQueueite_7// "Dialog_QueueItemRoute_Description_Plura"...
0x4812  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4817  ldc.i4.1
0x4818  newarr   [mscorlib]System.Object
0x481d  dup
0x481e  ldc.i4.0
0x481f  ldarg.0
0x4820  ldflda   int32 Microsoft.Crm.Dialogs.QueueItemRouteDialogForm::iTotal
0x4825  ldstr    aD// "D"
0x482a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x482f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x4834  stelem.ref
0x4835  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x483a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x483f  ret
```
