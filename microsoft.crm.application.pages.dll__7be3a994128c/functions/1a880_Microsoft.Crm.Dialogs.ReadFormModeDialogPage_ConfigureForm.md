# Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ConfigureForm

- ea: `0x1a880`
- end: `0x1aabf`
- name: `Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ConfigureForm`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1a880`

## string_xrefs

- `0x1a9cb`: `text/xml`
- `0x1aa07`: `XML loaded from the stream returned String.Empty.`
- `0x1aa11`: `XML loaded from the stream returned String.Empty.`
- `0x1a923`: `readform`
- `0x1aa3c`: `Web_grid_cmds_dlg_readformmode_title`
- `0x1aa66`: `FormModeRibbonButton_ReadOptimize_Label`
- `0x1aa7d`: `Web_grid_cmds_dlg_readformmode_description`

## pseudocode

```c

```

## disassembly

```asm
0x1a880  ldarg.0
0x1a881  ldarg.0
0x1a882  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a887  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a88c  ldstr    aIobjtype// "iObjType"
0x1a891  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a896  ldc.i4.7
0x1a897  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a89c  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1a8a1  stfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjType
0x1a8a6  ldarg.0
0x1a8a7  ldfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjType
0x1a8ac  ldc.i4.8
0x1a8ad  beq.s    loc_1A8BA
0x1a8af  ldstr    aPassedInEntity// "Passed-in entity type is not supported"
0x1a8b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x1a8b9  throw
0x1a8ba  ldarg.0
0x1a8bb  ldarg.0
0x1a8bc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a8c1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a8c6  ldstr    aItotal// "iTotal"
0x1a8cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a8d0  ldc.i4.7
0x1a8d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a8d6  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1a8db  stfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::Total
0x1a8e0  ldarg.0
0x1a8e1  ldfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjType
0x1a8e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a8eb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a8f0  stloc.0
0x1a8f1  ldarg.0
0x1a8f2  ldfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::Total
0x1a8f7  ldc.i4.1
0x1a8f8  ble.s    loc_1A90A
0x1a8fa  ldarg.0
0x1a8fb  ldloc.0
0x1a8fc  ldc.i4.2
0x1a8fd  ldnull
0x1a8fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x1a903  stfld    string Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjName
0x1a908  br.s     loc_1A918
0x1a90a  ldarg.0
0x1a90b  ldloc.0
0x1a90c  ldc.i4.1
0x1a90d  ldnull
0x1a90e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x1a913  stfld    string Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjName
0x1a918  ldarg.0
0x1a919  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a91e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a923  ldstr    aReadform// "readform"
0x1a928  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a92d  ldstr    aTrue_0// "true"
0x1a932  ldc.i4.5
0x1a933  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1a938  ldc.i4.0
0x1a939  ceq
0x1a93b  stloc.1
0x1a93c  ldarg.0
0x1a93d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a942  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1a947  stloc.3
0x1a948  ldloc.3
0x1a949  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1a94e  ldc.i4.0
0x1a94f  conv.i8
0x1a950  ble      loc_1AA29
0x1a955  ldloc.3
0x1a956  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1a95b  stloc.s  4
0x1a95d  ldloc.s  4
0x1a95f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a964  brfalse  loc_1A9FD
0x1a969  ldarg.0
0x1a96a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1a96f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1a974  ldstr    aIid// "iId"
0x1a979  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a97e  stloc.s  5
0x1a980  ldc.i4   0x96
0x1a985  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a98a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a98f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1a994  dup
0x1a995  ldstr    aEntityformmode// "entityformmode"
0x1a99a  ldloc.1
0x1a99b  brtrue.s loc_1A9A4
0x1a99d  ldstr    a2// "2"
0x1a9a2  br.s     loc_1A9A9
0x1a9a4  ldstr    a1// "1"
0x1a9a9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1a9ae  dup
0x1a9af  ldstr    aSystemuserid// "systemuserid"
0x1a9b4  ldloc.s  5
0x1a9b6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1a9bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a9c0  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a9c5  ldarg.0
0x1a9c6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1a9cb  ldstr    aTextXml// "text/xml"
0x1a9d0  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1a9d5  ldarg.0
0x1a9d6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1a9db  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1a9e0  ldarg.0
0x1a9e1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1a9e6  ldstr    aOk// "<ok/>"
0x1a9eb  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1a9f0  ldarg.0
0x1a9f1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1a9f6  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1a9fb  br.s     loc_1AA21
0x1a9fd  ldloc.s  4
0x1a9ff  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1aa04  ldc.i4.0
0x1aa05  cgt.un
0x1aa07  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1aa0c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1aa11  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1aa16  ldc.i4   0x80049002
0x1aa1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1aa20  throw
0x1aa21  leave.s  loc_1AA35
0x1aa23  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1aa28  throw
0x1aa29  leave.s  loc_1AA35
0x1aa2b  ldloc.3
0x1aa2c  brfalse.s loc_1AA34
0x1aa2e  ldloc.3
0x1aa2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1aa34  endfinally
0x1aa35  ldarg.0
0x1aa36  ldarg.0
0x1aa37  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1aa3c  ldstr    aWebGridCmdsDlg_74// "Web_grid_cmds_dlg_readformmode_title"
0x1aa41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa46  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x1aa4b  ldloc.1
0x1aa4c  brtrue.s loc_1AA60
0x1aa4e  ldarg.0
0x1aa4f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1aa54  ldstr    aFormmoderibbon// "FormModeRibbonButton_Edit_Label"
0x1aa59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa5e  br.s     loc_1AA70
0x1aa60  ldarg.0
0x1aa61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1aa66  ldstr    aFormmoderibbon_0// "FormModeRibbonButton_ReadOptimize_Label"
0x1aa6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa70  stloc.2
0x1aa71  ldarg.0
0x1aa72  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1aa77  ldarg.0
0x1aa78  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1aa7d  ldstr    aWebGridCmdsDlg_75// "Web_grid_cmds_dlg_readformmode_descript"...
0x1aa82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa87  ldc.i4.3
0x1aa88  newarr   [mscorlib]System.Object
0x1aa8d  dup
0x1aa8e  ldc.i4.0
0x1aa8f  ldarg.0
0x1aa90  ldfld    int32 Microsoft.Crm.Dialogs.ReadFormModeDialogPage::Total
0x1aa95  box      [mscorlib]System.Int32
0x1aa9a  stelem.ref
0x1aa9b  dup
0x1aa9c  ldc.i4.1
0x1aa9d  ldarg.0
0x1aa9e  ldfld    string Microsoft.Crm.Dialogs.ReadFormModeDialogPage::ObjName
0x1aaa3  stelem.ref
0x1aaa4  dup
0x1aaa5  ldc.i4.2
0x1aaa6  ldloc.2
0x1aaa7  stelem.ref
0x1aaa8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1aaad  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x1aab2  ldarg.0
0x1aab3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x1aab8  ldc.i4.3
0x1aab9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x1aabe  ret
```
