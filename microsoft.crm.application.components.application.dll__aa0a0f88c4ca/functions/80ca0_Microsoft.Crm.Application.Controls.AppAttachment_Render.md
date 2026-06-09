# Microsoft.Crm.Application.Controls.AppAttachment::Render

- ea: `0x80ca0`
- end: `0x816a5`
- name: `Microsoft.Crm.Application.Controls.AppAttachment::Render`
- size: `2565`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x26530`
- `0x26ba0`
- `0x26bc0`
- `0x80570`
- `0x80590`
- `0x805b0`
- `0x806d0`
- `0x806f0`
- `0x80710`
- `0x80770`
- `0x80c20`
- `0x80ca0`
- `0x816b0`
- `0x81870`
- `0x81970`
- `0x8d1a0`
- `0x8d1e0`
- `0x8d790`
- `0x8d7e0`

## string_xrefs

- `0x80d6c`: `butRemove`
- `0x80d71`: `Button_Label_Remove`
- `0x80d7b`: `removeAttachment({0:D})`
- `0x810ca`: `"><input type="hidden" name="commitUploadEndpoint" id="commitUploadEndpoint" value="`
- `0x81116`: `"><input type="hidden" name="crmFormSubmitXml"  id="crmFormSubmitXml" value="`
- `0x8112e`: `"><input type="hidden" name="OverwriteExistingFile"  id="OverwriteExistingFile" value="`
- `0x811a6`: `/_common/error/uploadFailure.aspx`
- `0x815cf`: ` disabled class="ms-crm-ReadOnly"`

## pseudocode

```c

```

## disassembly

```asm
0x80ca0  ldc.i4.0
0x80ca1  stloc.0
0x80ca2  ldc.i4.0
0x80ca3  stloc.1
0x80ca4  ldc.i4.0
0x80ca5  stloc.2
0x80ca6  ldc.i4.0
0x80ca7  stloc.3
0x80ca8  ldarg.0
0x80ca9  ldfld    bool Microsoft.Crm.Application.Controls.AppAttachment::_disabled
0x80cae  brtrue.s loc_80D10
0x80cb0  ldarg.0
0x80cb1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_uploadHandlerUrl
0x80cb6  callvirt instance string [mscorlib]System.Object::ToString()
0x80cbb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x80cc0  brfalse.s loc_80D05
0x80cc2  ldarg.0
0x80cc3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_downloadHandlerUrl
0x80cc8  callvirt instance string [mscorlib]System.Object::ToString()
0x80ccd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x80cd2  brfalse.s loc_80D05
0x80cd4  ldarg.0
0x80cd5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_successUrl
0x80cda  callvirt instance string [mscorlib]System.Object::ToString()
0x80cdf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x80ce4  brfalse.s loc_80D05
0x80ce6  ldarg.0
0x80ce7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_saveUrl
0x80cec  callvirt instance string [mscorlib]System.Object::ToString()
0x80cf1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x80cf6  brfalse.s loc_80D05
0x80cf8  ldarg.0
0x80cf9  ldfld    string Microsoft.Crm.Application.Controls.AppAttachment::_idXmlNode
0x80cfe  callvirt instance int32 [mscorlib]System.String::get_Length()
0x80d03  brtrue.s loc_80D10
0x80d05  ldc.i4.0
0x80d06  ldstr    aAllPropertiesM// "All properties must be set for the Atta"...
0x80d0b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x80d10  ldarg.1
0x80d11  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x80d16  stloc.s  4
0x80d18  ldarg.0
0x80d19  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x80d1e  isinst   Microsoft.Crm.Application.Controls.AppPage
0x80d23  stloc.s  5
0x80d25  ldstr    aButattach// "butAttach"
0x80d2a  ldstr    aButtonLabelUpl// "Button_Label_Upload"
0x80d2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80d34  ldstr    aAttach01// "attach({0}, {1});"
0x80d39  ldc.i4.2
0x80d3a  newarr   [mscorlib]System.Object
0x80d3f  dup
0x80d40  ldc.i4.0
0x80d41  ldarg.0
0x80d42  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_saveUrl
0x80d47  callvirt instance string [mscorlib]System.Object::ToString()
0x80d4c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x80d51  stelem.ref
0x80d52  dup
0x80d53  ldc.i4.1
0x80d54  ldarg.0
0x80d55  ldfld    string Microsoft.Crm.Application.Controls.AppAttachment::_idXmlNode
0x80d5a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x80d5f  stelem.ref
0x80d60  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80d65  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string)
0x80d6a  stloc.s  6
0x80d6c  ldstr    aButremove// "butRemove"
0x80d71  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x80d76  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80d7b  ldstr    aRemoveattachme// "removeAttachment({0:D})"
0x80d80  ldc.i4.1
0x80d81  newarr   [mscorlib]System.Object
0x80d86  dup
0x80d87  ldc.i4.0
0x80d88  ldloc.s  5
0x80d8a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x80d8f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x80d94  box      [mscorlib]System.Int32
0x80d99  stelem.ref
0x80d9a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80d9f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor(string, string, string)
0x80da4  stloc.s  7
0x80da6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80dab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x80db0  ldc.i4.0
0x80db1  ldc.i4.0
0x80db2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x80db7  stloc.s  0xC
0x80db9  ldloc.s  0xC
0x80dbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80dc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x80dc5  ldc.i4.0
0x80dc6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x80dcb  ldarg.0
0x80dcc  call     instance string Microsoft.Crm.Application.Controls.AppAttachment::get_ParentType()
0x80dd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x80dd6  brtrue   loc_80F03
0x80ddb  ldarg.0
0x80ddc  call     instance string Microsoft.Crm.Application.Controls.AppAttachment::get_ParentType()
0x80de1  call     int32 [mscorlib]System.Int32::Parse(string)
0x80de6  ldc.i4   0x106A
0x80deb  bne.un   loc_80F03
0x80df0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x80df5  ldloc.s  0xC
0x80df7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x80dfc  ldloc.s  0xC
0x80dfe  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x80e03  pop
0x80e04  ldloc.s  0xC
0x80e06  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEmailEngagementFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80e0b  stloc.0
0x80e0c  ldloc.s  0xC
0x80e0e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnlineSharepointConfigured(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80e13  brfalse.s loc_80E1E
0x80e15  ldloc.s  0xC
0x80e17  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOneDriveIntegrationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80e1c  br.s     loc_80E1F
0x80e1e  ldc.i4.0
0x80e1f  stloc.1
0x80e20  ldloc.s  0xC
0x80e22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x80e27  ldc.i4   0x106A
0x80e2c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x80e31  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDocumentManagementEnabled()
0x80e36  stloc.2
0x80e37  ldarg.0
0x80e38  call     instance string Microsoft.Crm.Application.Controls.AppAttachment::get_ParentType()
0x80e3d  brfalse  loc_80F03
0x80e42  ldarg.0
0x80e43  call     instance string Microsoft.Crm.Application.Controls.AppAttachment::get_ParentType()
0x80e48  call     int32 [mscorlib]System.Int32::Parse(string)
0x80e4d  ldc.i4   0x106A
0x80e52  bne.un   loc_80F03
0x80e57  ldstr    aEmail// "email"
0x80e5c  ldarg.0
0x80e5d  call     instance string Microsoft.Crm.Application.Controls.AppAttachment::get_ParentId()
0x80e62  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x80e67  ldc.i4.2
0x80e68  newarr   [mscorlib]System.String
0x80e6d  dup
0x80e6e  ldc.i4.0
0x80e6f  ldstr    aStatuscode// "statuscode"
0x80e74  stelem.ref
0x80e75  dup
0x80e76  ldc.i4.1
0x80e77  ldstr    aIsemailfollowe// "isemailfollowed"
0x80e7c  stelem.ref
0x80e7d  ldloc.s  0xC
0x80e7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80e84  stloc.s  0xD
0x80e86  ldloc.s  0xD
0x80e88  ldstr    aStatuscode// "statuscode"
0x80e8d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x80e92  callvirt instance string [mscorlib]System.Object::ToString()
0x80e97  call     int32 [mscorlib]System.Int32::Parse(string)
0x80e9c  ldc.i4.1
0x80e9d  bne.un.s loc_80EB7
0x80e9f  ldloc.s  0xD
0x80ea1  ldstr    aIsemailfollowe// "isemailfollowed"
0x80ea6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x80eab  callvirt instance string [mscorlib]System.Object::ToString()
0x80eb0  call     bool [mscorlib]System.Boolean::Parse(string)
0x80eb5  brtrue.s loc_80EB9
0x80eb7  ldc.i4.0
0x80eb8  stloc.0
0x80eb9  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x80ebe  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x80ec3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x80ec8  ldstr    aIsh// "ish"
0x80ecd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x80ed2  brfalse.s loc_80EF9
0x80ed4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x80ed9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x80ede  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x80ee3  ldstr    aIsh// "ish"
0x80ee8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x80eed  callvirt instance string [mscorlib]System.Object::ToString()
0x80ef2  call     bool [mscorlib]System.Boolean::Parse(string)
0x80ef7  brtrue.s loc_80F01
0x80ef9  ldarg.0
0x80efa  call     instance bool Microsoft.Crm.Application.Controls.AppAttachment::get_IsSPDocument()
0x80eff  brfalse.s loc_80F03
0x80f01  ldc.i4.0
0x80f02  stloc.0
0x80f03  ldloc.s  0xC
0x80f05  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.ExternalStorageUtilities::IsExternalStorageEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x80f0a  brfalse.s loc_80F0E
0x80f0c  ldc.i4.1
0x80f0d  stloc.3
0x80f0e  ldloc.s  0xC
0x80f10  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x80f15  leave.s  loc_80F23
0x80f17  ldloc.s  0xC
0x80f19  brfalse.s loc_80F22
0x80f1b  ldloc.s  0xC
0x80f1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80f22  endfinally
0x80f23  ldarg.0
0x80f24  ldfld    bool Microsoft.Crm.Application.Controls.AppAttachment::_disabled
0x80f29  brfalse.s loc_80F3B
0x80f2b  ldloc.s  7
0x80f2d  ldc.i4.1
0x80f2e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x80f33  ldloc.s  6
0x80f35  ldc.i4.1
0x80f36  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x80f3b  ldloc.s  5
0x80f3d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x80f42  stloc.s  8
0x80f44  ldloc.s  5
0x80f46  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x80f4b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x80f50  ldstr    aFilename// "filename"
0x80f55  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x80f5a  isinst   [mscorlib]System.String
0x80f5f  stloc.s  9
0x80f61  ldloc.s  9
0x80f63  brtrue.s loc_80F6C
0x80f65  ldsfld   string [mscorlib]System.String::Empty
0x80f6a  stloc.s  9
0x80f6c  ldloc.s  8
0x80f6e  ldstr    aFileAttachment// "File_Attachment_Label"
0x80f73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x80f78  stloc.s  0xA
0x80f7a  ldarg.0
0x80f7b  call     instance bool Microsoft.Crm.Application.Controls.AppAttachment::get_IsSPDocument()
0x80f80  brfalse.s loc_80F90
0x80f82  ldloc.s  8
0x80f84  ldstr    aFileAttachment_0// "File_Attachment_Label_Choose"
0x80f89  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x80f8e  stloc.s  0xA
0x80f90  ldloc.s  4
0x80f92  ldstr    aFormNameAttach// "<form name=\"Attachments\" id=\"Attachm"...
0x80f97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x80f9c  ldstr    aAction// "action"
0x80fa1  ldarg.0
0x80fa2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_uploadHandlerUrl
0x80fa7  callvirt instance string [mscorlib]System.Object::ToString()
0x80fac  ldarg.1
0x80fad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x80fb2  ldloc.s  4
0x80fb4  ldstr    asc_111CB6// ">"
0x80fb9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x80fbe  ldloc.s  5
0x80fc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext Microsoft.Crm.Application.Controls.AppPage::get_CurrentWrpcContext()
0x80fc5  ldloc.s  4
0x80fc7  ldarg.0
0x80fc8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.AppAttachment::_uploadHandlerUrl
0x80fcd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::RenderWrpcTokenAsHiddenInput(class [mscorlib]System.IO.TextWriter, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x80fd2  ldarg.0
0x80fd3  ldarg.1
0x80fd4  call     instance void Microsoft.Crm.Application.Controls.AppAttachment::RenderSolutionId(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x80fd9  ldloc.s  4
0x80fdb  ldstr    aInputTypeHidde_33// "<input type=\"hidden\" name=\"CloseWind"...
0x80fe0  ldarg.0
0x80fe1  ldflda   bool Microsoft.Crm.Application.Controls.AppAttachment::_closeWindow
0x80fe6  call     instance string [mscorlib]System.Boolean::ToString()
0x80feb  ldstr    aInputTypeHidde_34// "\"><input type=\"hidden\" name=\"Attach"...
0x80ff0  call     string [mscorlib]System.String::Concat(string, string, string)
0x80ff5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x80ffa  ldloc.s  4
0x80ffc  ldloc.s  5
0x80ffe  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x81003  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x81008  stloc.s  0xE
0x8100a  ldloca.s 0xE
0x8100c  ldstr    aD// "D"
0x81011  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x81016  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x8101b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x81020  ldloc.s  4
0x81022  ldstr    aInputTypeHidde_35// "\"><input type=\"hidden\" name=\"Attach"...
0x81027  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8102c  ldloc.s  5
0x8102e  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x81033  callvirt instance string Microsoft.Crm.Application.Forms.AppForm::get_EntityId()
0x81038  ldloc.s  4
0x8103a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x8103f  ldloc.s  4
0x81041  ldstr    aInputTypeHidde_36// "\"><input type=\"hidden\" name=\"UserId"...
0x81046  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8104b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x81050  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x81055  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x8105a  ldloc.s  4
0x8105c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x81061  ldloc.s  4
0x81063  ldstr    aInputTypeHidde_37// "\"><input type=\"hidden\" name=\"IsExte"...
0x81068  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8106d  ldloc.3
0x8106e  brtrue.s loc_81077
0x81070  ldstr    aFalse// "false"
0x81075  br.s     loc_8107C
0x81077  ldstr    aTrue// "true"
0x8107c  ldloc.s  4
0x8107e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x81083  ldloc.3
0x81084  brfalse  loc_81114
0x81089  ldstr    aApiStorage// "/api/storage?"
  ... truncated ...
```
