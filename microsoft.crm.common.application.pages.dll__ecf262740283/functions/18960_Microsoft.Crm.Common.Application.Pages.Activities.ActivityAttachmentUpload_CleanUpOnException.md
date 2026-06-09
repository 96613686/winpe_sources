# Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::CleanUpOnException

- ea: `0x18960`
- end: `0x18c54`
- name: `Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::CleanUpOnException`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18170`

## callees

- `0x18960`
- `0x18c60`
- `0x18d00`

## string_xrefs

- `0x189a4`: `/_common/error/uploadFailure.aspx`
- `0x189b6`: `/_common/error/dlg_error.aspx`
- `0x18ad6`: `/_common/error/dlg_error.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x18960  ldarg.0
0x18961  ldarg.1
0x18962  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x18967  call     instance bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::HandleXmlResponseType(valuetype [mscorlib]System.Nullable`1<int32> errorCode)
0x1896c  brfalse.s loc_18970
0x1896e  ldc.i4.1
0x1896f  ret
0x18970  ldarg.2
0x18971  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18976  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1897b  stloc.0
0x1897c  ldarg.0
0x1897d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18982  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x18987  ldstr    aErrorurl// "ErrorURL"
0x1898c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18991  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18996  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1899b  stloc.1
0x1899c  ldc.i4.2
0x1899d  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri
0x189a2  dup
0x189a3  ldc.i4.0
0x189a4  ldstr    aCommonErrorUpl// "/_common/error/uploadFailure.aspx"
0x189a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x189ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x189b3  stelem.ref
0x189b4  dup
0x189b5  ldc.i4.1
0x189b6  ldstr    aCommonErrorDlg// "/_common/error/dlg_error.aspx"
0x189bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x189c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x189c5  stelem.ref
0x189c6  stloc.2
0x189c7  ldloc.1
0x189c8  ldloc.2
0x189c9  call     bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::AllowListCheckUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri urlToVerify, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri[] knownUrls)
0x189ce  brtrue.s loc_189DB
0x189d0  ldstr    aRequestErrorur// "Request.errorUrl"
0x189d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x189da  throw
0x189db  ldloc.1
0x189dc  brfalse  loc_18C52
0x189e1  ldloc.1
0x189e2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x189e7  brtrue   loc_18C52
0x189ec  ldarg.0
0x189ed  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x189f2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x189f7  brtrue.s loc_18A05
0x189f9  ldloc.0
0x189fa  ldc.i4   0x42E
0x189ff  beq.s    loc_18A10
0x18a01  ldloc.0
0x18a02  ldc.i4.5
0x18a03  beq.s    loc_18A10
0x18a05  ldloc.0
0x18a06  ldc.i4   0x2392
0x18a0b  bne.un   loc_18BDC
0x18a10  ldarg.0
0x18a11  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x18a16  callvirt instance string [mscorlib]System.Object::ToString()
0x18a1b  stloc.3
0x18a1c  ldarg.3
0x18a1d  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x18a22  stloc.s  4
0x18a24  ldloc.s  4
0x18a26  brfalse  loc_18AC6
0x18a2b  ldloc.s  4
0x18a2d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x18a32  ldc.i4   0x80040265
0x18a37  bne.un   loc_18AC6
0x18a3c  ldarg.3
0x18a3d  ldarg.0
0x18a3e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18a43  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x18a48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18a4d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [System]System.Uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18a52  stloc.s  5
0x18a54  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x18a59  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x18a5e  ldstr    aRedirecturl// "RedirectURL"
0x18a63  ldloc.3
0x18a64  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x18a69  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x18a6e  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x18a73  ldstr    aAttachmenttype// "AttachmentType"
0x18a78  ldloc.0
0x18a79  box      [mscorlib]System.Int32
0x18a7e  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x18a83  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x18a88  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x18a8d  ldstr    aErrorinformati// "ErrorInformation"
0x18a92  ldloc.s  5
0x18a94  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x18a99  ldarg.0
0x18a9a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18a9f  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x18aa4  ldloc.1
0x18aa5  callvirt instance string [mscorlib]System.Object::ToString()
0x18aaa  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x18aaf  stloc.s  6
0x18ab1  ldarg.0
0x18ab2  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.UI.Page::get_Server()
0x18ab7  ldloc.s  6
0x18ab9  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x18abe  ldc.i4.0
0x18abf  callvirt instance void [System.Web]System.Web.HttpServerUtility::Transfer(string, bool)
0x18ac4  ldc.i4.1
0x18ac5  ret
0x18ac6  ldarg.0
0x18ac7  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x18acc  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x18ad1  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x18ad6  ldstr    aCommonErrorDlg// "/_common/error/dlg_error.aspx"
0x18adb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18ae0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18ae5  stloc.1
0x18ae6  ldstr    a0x// "0x"
0x18aeb  ldarga.s 1
0x18aed  ldstr    aX// "x"
0x18af2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18af7  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18afc  call     string [mscorlib]System.String::Concat(string, string)
0x18b01  stloc.s  7
0x18b03  ldloc.1
0x18b04  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b09  ldstr    aHresult// "hresult"
0x18b0e  ldloc.s  7
0x18b10  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18b15  ldarg.0
0x18b16  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x18b1b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b20  ldstr    aPopuperrorurl// "popupErrorUrl"
0x18b25  ldloc.1
0x18b26  callvirt instance string [mscorlib]System.Object::ToString()
0x18b2b  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18b30  ldarg.0
0x18b31  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x18b36  stloc.1
0x18b37  ldarg.0
0x18b38  ldfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::isNotesV2Attachment
0x18b3d  brfalse  loc_18BC8
0x18b42  ldloc.1
0x18b43  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b48  ldstr    aHr// "hr"
0x18b4d  ldloc.s  7
0x18b4f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18b54  ldloc.1
0x18b55  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b5a  ldstr    aPid// "pId"
0x18b5f  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x18b64  brfalse.s loc_18B8E
0x18b66  ldloc.1
0x18b67  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b6c  ldstr    aPid// "pId"
0x18b71  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x18b76  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18b7b  brfalse.s loc_18B8E
0x18b7d  ldloc.1
0x18b7e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b83  ldstr    aPid// "pId"
0x18b88  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::Remove(var<u1>)
0x18b8d  pop
0x18b8e  ldloc.1
0x18b8f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18b94  ldstr    aPtype// "pType"
0x18b99  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x18b9e  brfalse.s loc_18BC8
0x18ba0  ldloc.1
0x18ba1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18ba6  ldstr    aPtype// "pType"
0x18bab  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x18bb0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18bb5  brfalse.s loc_18BC8
0x18bb7  ldloc.1
0x18bb8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18bbd  ldstr    aPtype// "pType"
0x18bc2  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::Remove(var<u1>)
0x18bc7  pop
0x18bc8  ldarg.0
0x18bc9  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.UI.Page::get_Server()
0x18bce  ldloc.1
0x18bcf  callvirt instance string [mscorlib]System.Object::ToString()
0x18bd4  ldc.i4.1
0x18bd5  callvirt instance void [System.Web]System.Web.HttpServerUtility::Transfer(string, bool)
0x18bda  br.s     loc_18C50
0x18bdc  ldloc.1
0x18bdd  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18be2  ldstr    aHr// "hr"
0x18be7  ldstr    a0x// "0x"
0x18bec  ldarga.s 1
0x18bee  ldstr    aX// "x"
0x18bf3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18bf8  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18bfd  call     string [mscorlib]System.String::Concat(string, string)
0x18c02  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18c07  ldloc.1
0x18c08  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18c0d  ldstr    aRedirecturl// "RedirectURL"
0x18c12  ldarg.0
0x18c13  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::successUrl
0x18c18  callvirt instance string [mscorlib]System.Object::ToString()
0x18c1d  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18c22  ldloc.1
0x18c23  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x18c28  ldstr    aAttachmenttype// "AttachmentType"
0x18c2d  ldloca.s 0
0x18c2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18c34  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x18c39  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x18c3e  ldarg.0
0x18c3f  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.UI.Page::get_Server()
0x18c44  ldloc.1
0x18c45  callvirt instance string [mscorlib]System.Object::ToString()
0x18c4a  ldc.i4.1
0x18c4b  callvirt instance void [System.Web]System.Web.HttpServerUtility::Transfer(string, bool)
0x18c50  ldc.i4.1
0x18c51  ret
0x18c52  ldc.i4.0
0x18c53  ret
```
