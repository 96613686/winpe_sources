# Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ConfigureForm

- ea: `0x1ca0`
- end: `0x1e4f`
- name: `Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ConfigureForm`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1ca0`

## string_xrefs

- `0x1d7f`: `text/xml`
- `0x1dba`: `XML loaded from the stream returned String.Empty.`
- `0x1dc4`: `XML loaded from the stream returned String.Empty.`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1ca6  ldarg.0
0x1ca7  ldarg.0
0x1ca8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1cad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1cb2  ldstr    aItotal// "iTotal"
0x1cb7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1cbc  ldc.i4.7
0x1cbd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cc2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1cc7  stfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::iTotal
0x1ccc  ldarg.0
0x1ccd  ldarg.0
0x1cce  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1cd3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1cd8  ldstr    aIobjtype// "iObjType"
0x1cdd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ce2  ldc.i4.7
0x1ce3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ce8  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1ced  stfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjType
0x1cf2  ldarg.0
0x1cf3  ldfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::iTotal
0x1cf8  ldc.i4.1
0x1cf9  beq.s    loc_1D0F
0x1cfb  ldarg.0
0x1cfc  ldarg.0
0x1cfd  ldfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjType
0x1d02  ldc.i4.2
0x1d03  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1d08  stfld    string Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjName
0x1d0d  br.s     loc_1D21
0x1d0f  ldarg.0
0x1d10  ldarg.0
0x1d11  ldfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjType
0x1d16  ldc.i4.1
0x1d17  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1d1c  stfld    string Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjName
0x1d21  ldarg.0
0x1d22  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1d27  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1d2c  stloc.0
0x1d2d  ldloc.0
0x1d2e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1d33  ldc.i4.0
0x1d34  conv.i8
0x1d35  ble      loc_1DDC
0x1d3a  ldloc.0
0x1d3b  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1d40  stloc.1
0x1d41  ldloc.1
0x1d42  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d47  brfalse.s loc_1DB1
0x1d49  ldarg.0
0x1d4a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1d4f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1d54  ldstr    aIid// "iId"
0x1d59  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1d5e  stloc.2
0x1d5f  ldstr    aKbarticle// "kbarticle"
0x1d64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d69  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d6e  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Article::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1d73  ldloc.2
0x1d74  callvirt instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Article::Submit(string)
0x1d79  ldarg.0
0x1d7a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1d7f  ldstr    aTextXml// "text/xml"
0x1d84  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1d89  ldarg.0
0x1d8a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1d8f  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1d94  ldarg.0
0x1d95  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1d9a  ldstr    aOk// "<ok/>"
0x1d9f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1da4  ldarg.0
0x1da5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1daa  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1daf  br.s     loc_1DD4
0x1db1  ldloc.1
0x1db2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1db7  ldc.i4.0
0x1db8  cgt.un
0x1dba  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1dbf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1dc4  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1dc9  ldc.i4   0x80049002
0x1dce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1dd3  throw
0x1dd4  leave.s  loc_1DDC
0x1dd6  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1ddb  throw
0x1ddc  ldarg.0
0x1ddd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1de2  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1de7  dup
0x1de8  ldarg.0
0x1de9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1dee  ldstr    aDialogArticles// "Dialog_ArticleSubmit_Title"
0x1df3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1df8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1dfd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1e02  ldarg.0
0x1e03  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e08  ldstr    aDialogArticles_0// "Dialog_ArticleSubmit_Description"
0x1e0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e12  ldc.i4.2
0x1e13  newarr   [mscorlib]System.Object
0x1e18  dup
0x1e19  ldc.i4.0
0x1e1a  ldarg.0
0x1e1b  ldfld    int32 Microsoft.Crm.Service.Dialogs.SubmitDialogPage::iTotal
0x1e20  box      [mscorlib]System.Int32
0x1e25  stelem.ref
0x1e26  dup
0x1e27  ldc.i4.1
0x1e28  ldarg.0
0x1e29  ldfld    string Microsoft.Crm.Service.Dialogs.SubmitDialogPage::ObjName
0x1e2e  ldarg.0
0x1e2f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e34  ldstr    aDialogArticles_1// "Dialog_ArticleSubmit_Description_Casing"
0x1e39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e3e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1e43  stelem.ref
0x1e44  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e49  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1e4e  ret
```
