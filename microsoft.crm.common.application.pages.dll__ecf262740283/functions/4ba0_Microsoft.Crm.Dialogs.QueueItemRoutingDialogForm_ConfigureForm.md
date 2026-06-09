# Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::ConfigureForm

- ea: `0x4ba0`
- end: `0x50d3`
- name: `Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::ConfigureForm`
- size: `1331`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4ba0`

## string_xrefs

- `0x4eda`: `XML loaded from the stream returned String.Empty.`
- `0x4ee4`: `XML loaded from the stream returned String.Empty.`
- `0x4e9e`: `text/xml`
- `0x4e56`: `isQueueItemRemove`
- `0x4e6d`: `isQueueItemRemove`

## pseudocode

```c

```

## disassembly

```asm
0x4ba0  ldarg.0
0x4ba1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x4ba6  ldc.i4.0
0x4ba7  stloc.0
0x4ba8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4bad  stloc.1
0x4bae  ldarg.0
0x4baf  ldarg.0
0x4bb0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bb5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bba  ldstr    aItotal// "iTotal"
0x4bbf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bc4  ldc.i4.7
0x4bc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bca  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x4bcf  stfld    int32 Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::iTotal
0x4bd4  ldarg.0
0x4bd5  ldarg.0
0x4bd6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bdb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4be0  ldstr    aQueueid// "queueid"
0x4be5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bea  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4bef  ldarg.0
0x4bf0  ldarg.0
0x4bf1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bf6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bfb  ldstr    aIid// "iId"
0x4c00  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c05  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueItemId
0x4c0a  ldarg.0
0x4c0b  ldarg.0
0x4c0c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4c11  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4c16  ldstr    aObjectid// "objectId"
0x4c1b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c20  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::objectId
0x4c25  ldarg.0
0x4c26  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4c2b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4c30  brtrue.s loc_4C68
0x4c32  ldarg.0
0x4c33  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4c38  ldstr    a5850fc36859645// "{5850FC36-8596-45fe-B607-FE81D0C453FD}"
0x4c3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c42  brtrue.s loc_4C68
0x4c44  ldarg.0
0x4c45  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4c4a  ldstr    a436e2293Da8f4e// "{436e2293-da8f-4ef9-a1e6-fff25a5beb22}"
0x4c4f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c54  brtrue.s loc_4C68
0x4c56  ldarg.0
0x4c57  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4c5c  ldstr    aE611d9506bab47// "{e611d950-6bab-477c-a5a3-7e9a447b326d}"
0x4c61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c66  brfalse.s loc_4CE0
0x4c68  ldarg.0
0x4c69  ldstr    asc_1F1DE// ""
0x4c6e  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4c73  ldarg.0
0x4c74  ldfld    int32 Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::iTotal
0x4c79  ldc.i4.1
0x4c7a  bne.un.s loc_4CE0
0x4c7c  ldarg.0
0x4c7d  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::objectId
0x4c82  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4c87  brtrue.s loc_4CE0
0x4c89  ldstr    aQueueitem// "queueitem"
0x4c8e  ldarg.0
0x4c8f  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::objectId
0x4c94  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4c99  ldc.i4.1
0x4c9a  newarr   [mscorlib]System.String
0x4c9f  dup
0x4ca0  ldc.i4.0
0x4ca1  ldstr    aQueueid// "queueid"
0x4ca6  stelem.ref
0x4ca7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4cac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cb1  stloc.s  4
0x4cb3  ldarg.0
0x4cb4  ldloc.s  4
0x4cb6  ldstr    aQueueid// "queueid"
0x4cbb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4cc0  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x4cc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x4cca  callvirt instance string [mscorlib]System.Object::ToString()
0x4ccf  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4cd4  ldarg.0
0x4cd5  ldarg.0
0x4cd6  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::objectId
0x4cdb  stfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueItemId
0x4ce0  ldarg.0
0x4ce1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4ce6  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x4ceb  stloc.2
0x4cec  ldloc.2
0x4ced  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x4cf2  ldc.i4.0
0x4cf3  conv.i8
0x4cf4  ble      loc_4F72
0x4cf9  ldloc.2
0x4cfa  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x4cff  stloc.s  5
0x4d01  ldloc.s  5
0x4d03  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4d08  brfalse  loc_4ED0
0x4d0d  ldsfld   string [mscorlib]System.String::Empty
0x4d12  stloc.s  6
0x4d14  ldarg.0
0x4d15  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d1a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d1f  ldstr    aDstqueueid// "dstQueueId"
0x4d24  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d29  brfalse.s loc_4D47
0x4d2b  ldarg.0
0x4d2c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d31  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d36  ldstr    aDstqueueid// "dstQueueId"
0x4d3b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d40  callvirt instance string [mscorlib]System.Object::ToString()
0x4d45  stloc.s  6
0x4d47  ldarg.0
0x4d48  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d4d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d52  ldstr    aWorkerid// "workerid"
0x4d57  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d5c  brfalse.s loc_4D9F
0x4d5e  ldarg.0
0x4d5f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d64  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d69  ldstr    aWorkerid// "workerid"
0x4d6e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d73  callvirt instance string [mscorlib]System.Object::ToString()
0x4d78  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d7d  brtrue.s loc_4D9F
0x4d7f  ldarg.0
0x4d80  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d85  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d8a  ldstr    aWorkerid// "workerid"
0x4d8f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d94  callvirt instance string [mscorlib]System.Object::ToString()
0x4d99  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4d9e  stloc.1
0x4d9f  ldnull
0x4da0  stloc.s  7
0x4da2  ldloc.1
0x4da3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4da8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4dad  brfalse.s loc_4E12
0x4daf  ldarg.0
0x4db0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4db5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4dba  ldstr    aWorkertype// "workertype"
0x4dbf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4dc4  brfalse.s loc_4E12
0x4dc6  ldarg.0
0x4dc7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4dcc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4dd1  ldstr    aWorkertype// "workertype"
0x4dd6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4ddb  callvirt instance string [mscorlib]System.Object::ToString()
0x4de0  ldloca.s 0
0x4de2  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x4de7  brfalse.s loc_4E25
0x4de9  ldloc.0
0x4dea  ldc.i4.8
0x4deb  beq.s    loc_4DF4
0x4ded  ldloc.0
0x4dee  ldc.i4.s 9
0x4df0  beq.s    loc_4E03
0x4df2  br.s     loc_4E25
0x4df4  ldstr    aSystemuser// "systemuser"
0x4df9  ldloc.1
0x4dfa  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4dff  stloc.s  7
0x4e01  br.s     loc_4E25
0x4e03  ldstr    aTeam// "team"
0x4e08  ldloc.1
0x4e09  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4e0e  stloc.s  7
0x4e10  br.s     loc_4E25
0x4e12  ldstr    aQueue// "queue"
0x4e17  ldloc.s  6
0x4e19  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4e1e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4e23  stloc.s  7
0x4e25  ldloc.s  7
0x4e27  brtrue.s loc_4E34
0x4e29  ldstr    aDefinedOnlyFor// "Defined only for Team/User and Queue.No"...
0x4e2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4e33  throw
0x4e34  ldarg.0
0x4e35  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueItemId
0x4e3a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4e3f  ldloc.s  7
0x4e41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4e46  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRouteTo(valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e4b  ldarg.0
0x4e4c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4e51  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4e56  ldstr    aIsqueueitemrem// "isQueueItemRemove"
0x4e5b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4e60  brfalse.s loc_4E98
0x4e62  ldarg.0
0x4e63  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4e68  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4e6d  ldstr    aIsqueueitemrem// "isQueueItemRemove"
0x4e72  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4e77  ldstr    a1// "1"
0x4e7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e81  brfalse.s loc_4E98
0x4e83  ldarg.0
0x4e84  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueItemId
0x4e89  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4e8e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4e93  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRemoveFromQueue(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e98  ldarg.0
0x4e99  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4e9e  ldstr    aTextXml// "text/xml"
0x4ea3  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x4ea8  ldarg.0
0x4ea9  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4eae  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x4eb3  ldarg.0
0x4eb4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4eb9  ldstr    aOk// "<ok/>"
0x4ebe  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x4ec3  ldarg.0
0x4ec4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4ec9  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x4ece  br.s     loc_4EF4
0x4ed0  ldloc.s  5
0x4ed2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ed7  ldc.i4.0
0x4ed8  cgt.un
0x4eda  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x4edf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4ee4  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x4ee9  ldc.i4   0x80049002
0x4eee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4ef3  throw
0x4ef4  leave.s  loc_4F72
0x4ef6  stloc.s  8
0x4ef8  ldloc.s  8
0x4efa  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x4eff  ldc.i4   0x80040524
0x4f04  bne.un.s loc_4F62
0x4f06  ldc.i4.1
0x4f07  newarr   [mscorlib]System.String
0x4f0c  dup
0x4f0d  ldc.i4.0
0x4f0e  ldstr    aStatecode// "statecode"
0x4f13  stelem.ref
0x4f14  stloc.s  9
0x4f16  ldstr    aQueueitem// "queueitem"
0x4f1b  ldarg.0
0x4f1c  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueItemId
0x4f21  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4f26  ldloc.s  9
0x4f28  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4f2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f32  ldstr    aStatecode// "statecode"
0x4f37  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4f3c  castclass [mscorlib]System.String
0x4f41  ldstr    aInactive// "Inactive"
0x4f46  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f4b  brfalse.s loc_4F6A
0x4f4d  ldstr    aCannotRouteAnI// "Cannot route an inactive queue item."
0x4f52  ldc.i4   0x80040527
0x4f57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4f5c  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x4f61  throw
0x4f62  ldloc.s  8
0x4f64  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x4f69  throw
0x4f6a  leave.s  loc_4F72
0x4f6c  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x4f71  throw
0x4f72  ldarg.0
0x4f73  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4f78  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f7d  brtrue.s loc_4FC0
0x4f7f  ldstr    aQueue// "queue"
0x4f84  ldarg.0
0x4f85  ldfld    string Microsoft.Crm.Dialogs.QueueItemRoutingDialogForm::queueId
0x4f8a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4f8f  ldc.i4.1
0x4f90  newarr   [mscorlib]System.String
0x4f95  dup
0x4f96  ldc.i4.0
0x4f97  ldstr    aQueueviewtype// "queueviewtype"
0x4f9c  stelem.ref
0x4f9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4fa2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4fa7  stloc.s  0xA
0x4fa9  ldarg.0
0x4faa  ldloc.s  0xA
0x4fac  ldstr    aQueueviewtype// "queueviewtype"
0x4fb1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
  ... truncated ...
```
