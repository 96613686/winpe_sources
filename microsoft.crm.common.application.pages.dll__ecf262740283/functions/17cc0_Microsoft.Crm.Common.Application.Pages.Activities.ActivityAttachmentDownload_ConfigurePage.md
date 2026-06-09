# Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentDownload::ConfigurePage

- ea: `0x17cc0`
- end: `0x1813d`
- name: `Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentDownload::ConfigurePage`
- size: `1149`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17cc0`

## string_xrefs

- `0x17d66`: `/_common/error/downloadFailure.aspx`
- `0x180c9`: `/_common/error/downloadFailure.aspx`
- `0x1809e`: `noopen`

## pseudocode

```c

```

## disassembly

```asm
0x17cc0  call     void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState()
0x17cc5  ldarg.0
0x17cc6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x17ccb  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x17cd0  ldstr    asc_1F1DE// ""
0x17cd5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17cda  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17cdf  stloc.0
0x17ce0  ldc.i4.0
0x17ce1  stloc.1
0x17ce2  ldc.i4   0x80004005
0x17ce7  stloc.2
0x17ce8  ldc.i4.0
0x17ce9  stloc.3
0x17cea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17cef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x17cf4  ldc.i4.0
0x17cf5  ldc.i4.0
0x17cf6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x17cfb  stloc.s  4
0x17cfd  ldloc.s  4
0x17cff  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.ExternalStorageUtilities::IsExternalStorageEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17d04  brfalse.s loc_17D08
0x17d06  ldc.i4.1
0x17d07  stloc.3
0x17d08  leave.s  loc_17D16
0x17d0a  ldloc.s  4
0x17d0c  brfalse.s loc_17D15
0x17d0e  ldloc.s  4
0x17d10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17d15  endfinally
0x17d16  nop
0x17d17  ldarg.0
0x17d18  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17d1d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17d22  ldstr    aAttachmentid// "AttachmentId"
0x17d27  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17d2c  stloc.s  5
0x17d2e  ldarg.0
0x17d2f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17d34  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17d39  ldstr    aAttachmenttype// "AttachmentType"
0x17d3e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17d43  stloc.s  6
0x17d45  ldarg.0
0x17d46  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17d4b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17d50  ldstr    aIsnotestabatta// "IsNotesTabAttachment"
0x17d55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17d5a  ldstr    a1// "1"
0x17d5f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17d64  stloc.s  7
0x17d66  ldstr    aCommonErrorDow// "/_common/error/downloadFailure.aspx"
0x17d6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17d70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17d75  stloc.0
0x17d76  ldsfld   string [mscorlib]System.String::Empty
0x17d7b  stloc.s  8
0x17d7d  ldloc.s  6
0x17d7f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17d84  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x17d89  stloc.s  9
0x17d8b  ldloc.s  9
0x17d8d  ldc.i4   0x3E9
0x17d92  bgt.s    loc_17DA4
0x17d94  ldloc.s  9
0x17d96  ldc.i4.5
0x17d97  beq.s    loc_17DBF
0x17d99  ldloc.s  9
0x17d9b  ldc.i4   0x3E9
0x17da0  beq.s    loc_17DB6
0x17da2  br.s     loc_17DC8
0x17da4  ldloc.s  9
0x17da6  ldc.i4   0x42E
0x17dab  beq.s    loc_17DBF
0x17dad  ldloc.s  9
0x17daf  ldc.i4   0x2392
0x17db4  bne.un.s loc_17DC8
0x17db6  ldstr    aBody// "body"
0x17dbb  stloc.s  8
0x17dbd  br.s     loc_17DED
0x17dbf  ldstr    aDocumentbody// "documentbody"
0x17dc4  stloc.s  8
0x17dc6  br.s     loc_17DED
0x17dc8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17dcd  ldstr    aInvalidAttachm// "Invalid attachment type {0}"
0x17dd2  ldc.i4.1
0x17dd3  newarr   [mscorlib]System.Object
0x17dd8  dup
0x17dd9  ldc.i4.0
0x17dda  ldloc.s  6
0x17ddc  stelem.ref
0x17ddd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17de2  ldc.i4   0x80040203
0x17de7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17dec  throw
0x17ded  ldloc.s  9
0x17def  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17df4  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17df9  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x17dfe  stloc.s  0xA
0x17e00  ldc.i4.3
0x17e01  newarr   [mscorlib]System.String
0x17e06  dup
0x17e07  ldc.i4.0
0x17e08  ldstr    aFilename// "filename"
0x17e0d  stelem.ref
0x17e0e  dup
0x17e0f  ldc.i4.1
0x17e10  ldloc.s  8
0x17e12  stelem.ref
0x17e13  dup
0x17e14  ldc.i4.2
0x17e15  ldstr    aMimetype// "mimetype"
0x17e1a  stelem.ref
0x17e1b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x17e20  stloc.s  0xB
0x17e22  ldloc.s  0xB
0x17e24  ldc.i4.1
0x17e25  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_HasLazyFileAttribute(bool)
0x17e2a  ldloc.s  0xB
0x17e2c  ldloc.s  8
0x17e2e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_LazyFileAttributeKey(string)
0x17e33  ldloc.s  0xB
0x17e35  ldloc.s  0xA
0x17e37  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_LazyFileAttributeEntityName(string)
0x17e3c  ldloc.s  0xB
0x17e3e  ldarg.0
0x17e3f  ldfld    int32 Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentDownload::_32MBytes
0x17e44  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_LazyFileAttributeSizeLimit(int32)
0x17e49  ldloc.s  0xA
0x17e4b  ldloc.s  5
0x17e4d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x17e52  ldloc.s  0xB
0x17e54  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17e59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveSdkEntity(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17e5e  stloc.s  0xC
0x17e60  ldloc.s  0xC
0x17e62  ldstr    aFilename// "filename"
0x17e67  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x17e6c  castclass [mscorlib]System.String
0x17e71  stloc.s  0xD
0x17e73  ldloc.3
0x17e74  brfalse.s loc_17EE6
0x17e76  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x17e7b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x17e80  ldc.i4.0
0x17e81  ldc.i4.0
0x17e82  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x17e87  stloc.s  0x13
0x17e89  ldloc.s  0x13
0x17e8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17e90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x17e95  ldc.i4.0
0x17e96  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x17e9b  ldloc.s  5
0x17e9d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x17ea2  ldloc.s  6
0x17ea4  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x17ea9  ldloc.s  0xD
0x17eab  ldloc.s  0x13
0x17ead  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.DownloadService::DownloadSASURI(valuetype [mscorlib]System.Guid, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17eb2  stloc.s  0x14
0x17eb4  ldarg.0
0x17eb5  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x17eba  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x17ebf  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x17ec4  ldarg.0
0x17ec5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x17eca  ldloc.s  0x14
0x17ecc  ldc.i4.0
0x17ecd  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x17ed2  leave    loc_1813C
0x17ed7  ldloc.s  0x13
0x17ed9  brfalse.s loc_17EE2
0x17edb  ldloc.s  0x13
0x17edd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17ee2  endfinally
0x17ee3  pop
0x17ee4  leave.s  loc_17EE6
0x17ee6  ldloc.s  0xD
0x17ee8  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x17eed  stloc.s  0xD
0x17eef  ldloc.s  9
0x17ef1  ldc.i4.5
0x17ef2  ceq
0x17ef4  ldloc.s  7
0x17ef6  and
0x17ef7  brfalse.s loc_17F10
0x17ef9  ldloc.s  0xD
0x17efb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsBlockedAttachment(string)
0x17f00  brfalse.s loc_17F10
0x17f02  ldc.i4   0x80043E09
0x17f07  stloc.2
0x17f08  ldloc.s  0xD
0x17f0a  newobj   instance void [mscorlib]System.Security.SecurityException::.ctor(string)
0x17f0f  throw
0x17f10  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x17f15  ldloc.s  0xD
0x17f17  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::IsBlockedAttachment(string)
0x17f1c  brfalse.s loc_17F2C
0x17f1e  ldc.i4   0x80043E09
0x17f23  stloc.2
0x17f24  ldloc.s  0xD
0x17f26  newobj   instance void [mscorlib]System.Security.SecurityException::.ctor(string)
0x17f2b  throw
0x17f2c  ldarg.0
0x17f2d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x17f32  ldstr    aApplicationOct// "application/octet-stream"
0x17f37  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x17f3c  ldloc.s  0xD
0x17f3e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x17f43  stloc.s  0xE
0x17f45  ldc.i4   0x9B
0x17f4a  ldloc.s  0xD
0x17f4c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17f51  bge.s    loc_17FBB
0x17f53  ldnull
0x17f54  stloc.s  0x15
0x17f56  ldloc.s  0xD
0x17f58  ldstr    asc_32ABE// "."
0x17f5d  ldc.i4.4
0x17f5e  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x17f63  stloc.s  0x16
0x17f65  ldc.i4.m1
0x17f66  ldloc.s  0x16
0x17f68  bne.un.s loc_17F84
0x17f6a  ldloc.s  0xD
0x17f6c  ldc.i4.0
0x17f6d  ldc.i4.s 0xC
0x17f6f  ldloc.s  0xD
0x17f71  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17f76  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x17f7b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17f80  stloc.s  0x15
0x17f82  br.s     loc_17FB2
0x17f84  ldloc.s  0xD
0x17f86  ldc.i4.0
0x17f87  ldc.i4.8
0x17f88  ldloc.s  0x16
0x17f8a  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x17f8f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17f94  stloc.s  0x15
0x17f96  ldloc.s  0x15
0x17f98  ldloc.s  0xD
0x17f9a  ldloc.s  0x16
0x17f9c  ldloc.s  0xD
0x17f9e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17fa3  ldloc.s  0x16
0x17fa5  sub
0x17fa6  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17fab  call     string [mscorlib]System.String::Concat(string, string)
0x17fb0  stloc.s  0x15
0x17fb2  ldloc.s  0x15
0x17fb4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x17fb9  stloc.s  0xE
0x17fbb  ldc.i4.1
0x17fbc  stloc.1
0x17fbd  ldloc.s  0xC
0x17fbf  ldloc.s  8
0x17fc1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x17fc6  isinst   [mscorlib]System.String
0x17fcb  stloc.s  0xF
0x17fcd  ldloc.s  0xF
0x17fcf  brtrue.s loc_17FD8
0x17fd1  ldsfld   string [mscorlib]System.String::Empty
0x17fd6  stloc.s  0xF
0x17fd8  ldnull
0x17fd9  stloc.s  0x10
0x17fdb  ldloc.s  0xB
0x17fdd  callvirt instance class [mscorlib]System.Lazy`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::get_LazyFileAttributeValue()
0x17fe2  stloc.s  0x11
0x17fe4  ldloc.s  0x11
0x17fe6  brfalse.s loc_18025
0x17fe8  ldloc.s  0x11
0x17fea  callvirt instance var<u1> class [mscorlib]System.Lazy`1<object>::get_Value()
0x17fef  isinst   [mscorlib]System.String
0x17ff4  stloc.s  0x17
0x17ff6  ldloc.s  0x17
0x17ff8  brfalse.s loc_18005
0x17ffa  ldloc.s  0x17
0x17ffc  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x18001  stloc.s  0x10
0x18003  br.s     loc_1802E
0x18005  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1800a  ldstr    aContentRetreiv// "Content retreived from the database is "...
0x1800f  ldc.i4.1
0x18010  newarr   [mscorlib]System.Object
0x18015  dup
0x18016  ldc.i4.0
0x18017  ldloc.s  5
0x18019  stelem.ref
0x1801a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1801f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x18024  throw
0x18025  ldloc.s  0xF
0x18027  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x1802c  stloc.s  0x10
0x1802e  ldarg.0
0x1802f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
  ... truncated ...
```
