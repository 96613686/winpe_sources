# Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::ConfigurePage

- ea: `0x18170`
- end: `0x18816`
- name: `Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::ConfigurePage`
- size: `1702`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18170`
- `0x18820`
- `0x18840`
- `0x18870`
- `0x188b0`
- `0x18960`
- `0x18c60`
- `0x18d00`

## string_xrefs

- `0x181e2`: `OverwriteExistingFile`
- `0x18425`: `crmFormSubmitXml`

## pseudocode

```c

```

## disassembly

```asm
0x18170  ldarg.0
0x18171  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x18176  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1817b  ldnull
0x1817c  stloc.0
0x1817d  ldnull
0x1817e  stloc.1
0x1817f  ldc.i4   0x80004005
0x18184  stloc.2
0x18185  ldarg.0
0x18186  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1818b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x18190  ldstr    aAttachmentid// "AttachmentId"
0x18195  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1819a  stloc.0
0x1819b  ldarg.0
0x1819c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x181a1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x181a6  ldstr    aAttachmenttype// "AttachmentType"
0x181ab  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x181b0  stloc.1
0x181b1  ldarg.0
0x181b2  ldarg.0
0x181b3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x181b8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x181bd  ldstr    aIsspdocument// "IsSPDocument"
0x181c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x181c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x181cc  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x181d1  stfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::isSharePointDocument
0x181d6  ldarg.0
0x181d7  ldarg.0
0x181d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x181dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x181e2  ldstr    aOverwriteexist// "OverwriteExistingFile"
0x181e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x181ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x181f1  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x181f6  stfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::overwriteExistingFile
0x181fb  ldarg.0
0x181fc  ldarg.0
0x181fd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18202  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x18207  ldstr    aSuccessurl// "SuccessURL"
0x1820c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18211  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18216  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1821b  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x18220  ldarg.0
0x18221  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18226  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x1822b  ldstr    aResponsetype// "ResponseType"
0x18230  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18235  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1823a  brtrue.s loc_18257
0x1823c  ldarg.0
0x1823d  ldarg.0
0x1823e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18243  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0x18248  ldstr    aResponsetype// "ResponseType"
0x1824d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18252  stfld    string Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::responseType
0x18257  ldc.i4.6
0x18258  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri
0x1825d  dup
0x1825e  ldc.i4.0
0x1825f  ldstr    aSfaSaleslitAtt// "/SFA/SalesLit/Attachment_edit.aspx"
0x18264  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18269  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1826e  stelem.ref
0x1826f  dup
0x18270  ldc.i4.1
0x18271  ldstr    aActivitiesAtta_2// "/Activities/Attachment/edit.aspx"
0x18276  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1827b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18280  stelem.ref
0x18281  dup
0x18282  ldc.i4.2
0x18283  ldstr    aToolsMailmerge_0// "/Tools/MailMerge/edit.aspx"
0x18288  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1828d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18292  stelem.ref
0x18293  dup
0x18294  ldc.i4.3
0x18295  ldstr    aNotesEditAspx// "/Notes/edit.aspx"
0x1829a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1829f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x182a4  stelem.ref
0x182a5  dup
0x182a6  ldc.i4.4
0x182a7  ldstr    aNotesNotesv2at// "/Notes/notesv2attach.aspx"
0x182ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x182b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x182b6  stelem.ref
0x182b7  dup
0x182b8  ldc.i4.5
0x182b9  ldstr    aGridCmdsDlgSpU_0// "/_grid/cmds/dlg_SP_upload.aspx"
0x182be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x182c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x182c8  stelem.ref
0x182c9  stloc.3
0x182ca  ldarg.0
0x182cb  ldarg.0
0x182cc  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x182d1  brfalse.s loc_182EE
0x182d3  ldarg.0
0x182d4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x182d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x182de  ldstr    aNotesv2attachA// "notesv2attach.aspx"
0x182e3  ldc.i4.5
0x182e4  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x182e9  ldc.i4.0
0x182ea  cgt
0x182ec  br.s     loc_182EF
0x182ee  ldc.i4.0
0x182ef  stfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::isNotesV2Attachment
0x182f4  ldarg.0
0x182f5  ldfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::isNotesV2Attachment
0x182fa  brfalse.s loc_18306
0x182fc  ldloc.0
0x182fd  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x18302  brfalse.s loc_18306
0x18304  ldnull
0x18305  stloc.0
0x18306  ldarg.0
0x18307  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x1830c  ldloc.3
0x1830d  call     bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::AllowListCheckUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri urlToVerify, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri[] knownUrls)
0x18312  brtrue.s loc_1831F
0x18314  ldstr    aRequestSuccess// "Request.successUrl"
0x18319  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1831e  throw
0x1831f  ldarg.0
0x18320  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18325  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x1832a  stloc.s  4
0x1832c  ldloc.s  4
0x1832e  brfalse.s loc_1833A
0x18330  ldc.i4.1
0x18331  ldloc.s  4
0x18333  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x18338  beq.s    loc_18345
0x1833a  ldstr    aRequestFiles// "Request.Files"
0x1833f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x18344  throw
0x18345  ldloc.s  4
0x18347  ldc.i4.0
0x18348  callvirt instance class [System.Web]System.Web.HttpPostedFile [System.Web]System.Web.HttpFileCollection::get_Item(int32)
0x1834d  stloc.s  5
0x1834f  ldloc.s  5
0x18351  brtrue.s loc_1835E
0x18353  ldstr    aRequestFiles0// "Request.Files[0]"
0x18358  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1835d  throw
0x1835e  ldloc.s  5
0x18360  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0x18365  brtrue.s loc_1837A
0x18367  ldc.i4   0x80048296
0x1836c  stloc.2
0x1836d  ldloc.s  5
0x1836f  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0x18374  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x18379  throw
0x1837a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1837f  stloc.s  6
0x18381  ldloc.s  6
0x18383  ldloc.s  5
0x18385  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0x1838a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::IsBlockedAttachment(string)
0x1838f  brfalse.s loc_183A4
0x18391  ldc.i4   0x80043E09
0x18396  stloc.2
0x18397  ldloc.s  5
0x18399  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0x1839e  newobj   instance void [mscorlib]System.Security.SecurityException::.ctor(string)
0x183a3  throw
0x183a4  ldloc.s  5
0x183a6  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0x183ab  ldloc.s  6
0x183ad  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxUploadFileSize()
0x183b2  ble.s    loc_183C7
0x183b4  ldc.i4   0x80043E08
0x183b9  stloc.2
0x183ba  ldloc.s  5
0x183bc  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0x183c1  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x183c6  throw
0x183c7  ldloc.s  5
0x183c9  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_ContentType()
0x183ce  stloc.s  7
0x183d0  ldloc.s  7
0x183d2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x183d7  brfalse.s loc_183E0
0x183d9  ldstr    aApplicationOct// "application/octet-stream"
0x183de  stloc.s  7
0x183e0  ldloc.1
0x183e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183e6  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x183eb  stloc.s  8
0x183ed  ldloc.s  5
0x183ef  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0x183f4  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x183f9  stloc.s  9
0x183fb  ldloc.s  8
0x183fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18402  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18407  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x1840c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18411  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18416  stloc.s  0xA
0x18418  ldloc.s  0xA
0x1841a  ldarg.0
0x1841b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18420  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x18425  ldstr    aCrmformsubmitx_0// "crmFormSubmitXml"
0x1842a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1842f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x18434  ldloc.s  0xA
0x18436  ldstr    aStepid_0// "stepid"
0x1843b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x18440  isinst   [mscorlib]System.String
0x18445  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1844a  brtrue.s loc_18454
0x1844c  ldarg.0
0x1844d  ldloc.s  0xA
0x1844f  call     instance void Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::CustomizeAttachmentForWorkflow(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity attachment)
0x18454  ldloc.s  0xA
0x18456  ldstr    aMimetype// "mimetype"
0x1845b  ldloc.s  7
0x1845d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x18462  ldloc.s  0xA
0x18464  ldstr    aFilename// "filename"
0x18469  ldloc.s  9
0x1846b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x18470  ldloc.0
0x18471  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18476  brtrue.s loc_18480
0x18478  ldloc.s  0xA
0x1847a  ldloc.0
0x1847b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x18480  ldloc.s  8
0x18482  ldc.i4   0x3E9
0x18487  bgt.s    loc_1849F
0x18489  ldloc.s  8
0x1848b  ldc.i4.5
0x1848c  beq      loc_18533
0x18491  ldloc.s  8
0x18493  ldc.i4   0x3E9
0x18498  beq.s    loc_184B7
0x1849a  br       loc_185A9
0x1849f  ldloc.s  8
0x184a1  ldc.i4   0x42E
0x184a6  beq      loc_18533
0x184ab  ldloc.s  8
0x184ad  ldc.i4   0x2392
0x184b2  bne.un   loc_185A9
0x184b7  ldloc.s  5
0x184b9  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0x184be  ldarg.0
0x184bf  ldfld    int32 Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::_32MBytes
0x184c4  bgt.s    loc_184DF
0x184c6  ldloc.s  0xA
0x184c8  ldstr    aBody// "body"
0x184cd  ldarg.0
0x184ce  ldloc.s  5
0x184d0  call     instance string Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::GetBase64Data(class [System.Web]System.Web.HttpPostedFile httpPostedFile)
0x184d5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x184da  br       loc_185CD
0x184df  ldloc.s  0xA
0x184e1  ldstr    aBody// "body"
0x184e6  ldsfld   string [mscorlib]System.String::Empty
0x184eb  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x184f0  ldloc.s  0xA
0x184f2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x184f7  dup
0x184f8  ldc.i4.1
0x184f9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_HasLazyFileAttribute(bool)
0x184fe  dup
0x184ff  ldstr    aBody// "body"
0x18504  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LazyFileAttributeKey(string)
0x18509  dup
0x1850a  ldstr    aFilesize// "filesize"
0x1850f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LazyFileSizeAttributeKey(string)
0x18514  dup
0x18515  ldloc.s  5
0x18517  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0x1851c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LazyFileSizeAttributeValue(int32)
0x18521  ldarg.0
0x18522  ldloc.s  5
0x18524  call     instance class [mscorlib]System.Lazy`1<object> Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::NewLazyObject(class [System.Web]System.Web.HttpPostedFile httpPostedFile)
0x18529  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LazyFileAttributeValue(class [mscorlib]System.Lazy`1<object>)
0x1852e  br       loc_185CD
0x18533  ldloc.s  5
0x18535  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0x1853a  ldarg.0
0x1853b  ldfld    int32 Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::_32MBytes
0x18540  bgt.s    loc_18558
0x18542  ldloc.s  0xA
0x18544  ldstr    aDocumentbody// "documentbody"
0x18549  ldarg.0
  ... truncated ...
```
