# Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ConfigureForm

- ea: `0x1eb0`
- end: `0x204a`
- name: `Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ConfigureForm`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1eb0`

## string_xrefs

- `0x1f8f`: `text/xml`
- `0x1fca`: `XML loaded from the stream returned String.Empty.`
- `0x1fd4`: `XML loaded from the stream returned String.Empty.`

## pseudocode

```c

```

## disassembly

```asm
0x1eb0  ldarg.0
0x1eb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1eb6  ldarg.0
0x1eb7  ldarg.0
0x1eb8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ebd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ec2  ldstr    aItotal// "iTotal"
0x1ec7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ecc  ldc.i4.7
0x1ecd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ed2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1ed7  stfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::iTotal
0x1edc  ldarg.0
0x1edd  ldarg.0
0x1ede  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ee3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ee8  ldstr    aIobjtype// "iObjType"
0x1eed  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ef2  ldc.i4.7
0x1ef3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ef8  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1efd  stfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjType
0x1f02  ldarg.0
0x1f03  ldfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::iTotal
0x1f08  ldc.i4.1
0x1f09  beq.s    loc_1F1F
0x1f0b  ldarg.0
0x1f0c  ldarg.0
0x1f0d  ldfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjType
0x1f12  ldc.i4.2
0x1f13  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1f18  stfld    string Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjName
0x1f1d  br.s     loc_1F31
0x1f1f  ldarg.0
0x1f20  ldarg.0
0x1f21  ldfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjType
0x1f26  ldc.i4.1
0x1f27  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1f2c  stfld    string Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjName
0x1f31  ldarg.0
0x1f32  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1f37  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1f3c  stloc.0
0x1f3d  ldloc.0
0x1f3e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1f43  ldc.i4.0
0x1f44  conv.i8
0x1f45  ble      loc_1FEC
0x1f4a  ldloc.0
0x1f4b  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1f50  stloc.1
0x1f51  ldloc.1
0x1f52  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1f57  brfalse.s loc_1FC1
0x1f59  ldarg.0
0x1f5a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1f5f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1f64  ldstr    aIid// "iId"
0x1f69  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1f6e  stloc.2
0x1f6f  ldstr    aKbarticle// "kbarticle"
0x1f74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f79  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f7e  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Article::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1f83  ldloc.2
0x1f84  callvirt instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Article::Unpublish(string)
0x1f89  ldarg.0
0x1f8a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f8f  ldstr    aTextXml// "text/xml"
0x1f94  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1f99  ldarg.0
0x1f9a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1f9f  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1fa4  ldarg.0
0x1fa5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1faa  ldstr    aOk// "<ok/>"
0x1faf  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1fb4  ldarg.0
0x1fb5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1fba  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1fbf  br.s     loc_1FE4
0x1fc1  ldloc.1
0x1fc2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fc7  ldc.i4.0
0x1fc8  cgt.un
0x1fca  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1fcf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1fd4  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1fd9  ldc.i4   0x80049002
0x1fde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1fe3  throw
0x1fe4  leave.s  loc_1FEC
0x1fe6  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1feb  throw
0x1fec  ldarg.0
0x1fed  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1ff2  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1ff7  dup
0x1ff8  ldarg.0
0x1ff9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1ffe  ldstr    aDialogArticleu// "Dialog_ArticleUnpublish_Title"
0x2003  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2008  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x200d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x2012  ldarg.0
0x2013  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2018  ldstr    aDialogArticleu_0// "Dialog_ArticleUnpublish_Description"
0x201d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2022  ldc.i4.2
0x2023  newarr   [mscorlib]System.Object
0x2028  dup
0x2029  ldc.i4.0
0x202a  ldarg.0
0x202b  ldfld    int32 Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::iTotal
0x2030  box      [mscorlib]System.Int32
0x2035  stelem.ref
0x2036  dup
0x2037  ldc.i4.1
0x2038  ldarg.0
0x2039  ldfld    string Microsoft.Crm.Service.Dialogs.UnpublishDialogPage::ObjName
0x203e  stelem.ref
0x203f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2044  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2049  ret
```
