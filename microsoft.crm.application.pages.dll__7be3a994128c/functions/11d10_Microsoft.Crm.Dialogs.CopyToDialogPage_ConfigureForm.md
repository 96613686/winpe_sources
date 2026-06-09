# Microsoft.Crm.Dialogs.CopyToDialogPage::ConfigureForm

- ea: `0x11d10`
- end: `0x11f19`
- name: `Microsoft.Crm.Dialogs.CopyToDialogPage::ConfigureForm`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11d10`

## string_xrefs

- `0x11e42`: `XML loaded from the stream returned String.Empty.`
- `0x11e4c`: `XML loaded from the stream returned String.Empty.`
- `0x11d1d`: `Dialog_CopyTo_ActionStringCopyTo`
- `0x11ea7`: `Dialog_CopyTo_Title`
- `0x11ed6`: `Dialog_CopyTo_Description`

## pseudocode

```c

```

## disassembly

```asm
0x11d10  ldarg.0
0x11d11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x11d16  ldarg.0
0x11d17  ldarg.0
0x11d18  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11d1d  ldstr    aDialogCopytoAc// "Dialog_CopyTo_ActionStringCopyTo"
0x11d22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11d27  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::actionString
0x11d2c  ldarg.0
0x11d2d  ldarg.0
0x11d2e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11d33  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11d38  ldstr    aItemobjectid// "itemObjectId"
0x11d3d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d42  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x11d47  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::itemObjectId
0x11d4c  ldarg.0
0x11d4d  ldarg.0
0x11d4e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11d53  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11d58  ldstr    aItotal// "iTotal"
0x11d5d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d62  ldc.i4.7
0x11d63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11d68  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x11d6d  stfld    int32 Microsoft.Crm.Dialogs.CopyToDialogPage::Total
0x11d72  ldarg.0
0x11d73  ldarg.0
0x11d74  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11d79  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11d7e  ldstr    aIobjtype// "iObjType"
0x11d83  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11d88  ldc.i4.7
0x11d89  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11d8e  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x11d93  stfld    int32 Microsoft.Crm.Dialogs.CopyToDialogPage::ObjType
0x11d98  ldarg.0
0x11d99  ldfld    int32 Microsoft.Crm.Dialogs.CopyToDialogPage::Total
0x11d9e  ldc.i4.1
0x11d9f  beq.s    loc_11DB5
0x11da1  ldarg.0
0x11da2  ldarg.0
0x11da3  ldfld    int32 Microsoft.Crm.Dialogs.CopyToDialogPage::ObjType
0x11da8  ldc.i4.2
0x11da9  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x11dae  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::ObjName
0x11db3  br.s     loc_11DC7
0x11db5  ldarg.0
0x11db6  ldarg.0
0x11db7  ldfld    int32 Microsoft.Crm.Dialogs.CopyToDialogPage::ObjType
0x11dbc  ldc.i4.1
0x11dbd  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x11dc2  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::ObjName
0x11dc7  ldarg.0
0x11dc8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11dcd  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x11dd2  stloc.0
0x11dd3  ldloc.0
0x11dd4  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x11dd9  ldc.i4.0
0x11dda  conv.i8
0x11ddb  ble      loc_11E64
0x11de0  ldloc.0
0x11de1  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x11de6  stloc.1
0x11de7  ldloc.1
0x11de8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11ded  brfalse.s loc_11E39
0x11def  ldarg.0
0x11df0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11df5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11dfa  ldstr    aIid// "iId"
0x11dff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11e04  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x11e09  stloc.2
0x11e0a  ldarg.0
0x11e0b  ldfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::itemObjectId
0x11e10  stloc.3
0x11e11  ldstr    aList// "list"
0x11e16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11e1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11e20  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11e25  ldloc.2
0x11e26  ldloc.3
0x11e27  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::CopyTo(string, string)
0x11e2c  ldarg.0
0x11e2d  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x11e32  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x11e37  br.s     loc_11E5C
0x11e39  ldloc.1
0x11e3a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11e3f  ldc.i4.0
0x11e40  cgt.un
0x11e42  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x11e47  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x11e4c  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x11e51  ldc.i4   0x80049002
0x11e56  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x11e5b  throw
0x11e5c  leave.s  loc_11E64
0x11e5e  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x11e63  throw
0x11e64  ldarg.0
0x11e65  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11e6a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11e6f  ldstr    aConfirmmode// "confirmMode"
0x11e74  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11e79  ldstr    a1// "1"
0x11e7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11e83  brfalse.s loc_11E9B
0x11e85  ldarg.0
0x11e86  ldstr    aConfirmmodeTru// "confirmMode(true)"
0x11e8b  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::dialogActionOk
0x11e90  ldarg.0
0x11e91  ldstr    aConfirmmodeFal// "confirmMode(false)"
0x11e96  stfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::dialogActionCancel
0x11e9b  ldarg.0
0x11e9c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11ea1  ldarg.0
0x11ea2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11ea7  ldstr    aDialogCopytoTi// "Dialog_CopyTo_Title"
0x11eac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11eb1  ldc.i4.1
0x11eb2  newarr   [mscorlib]System.Object
0x11eb7  dup
0x11eb8  ldc.i4.0
0x11eb9  ldarg.0
0x11eba  ldfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::ObjName
0x11ebf  stelem.ref
0x11ec0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ec5  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x11eca  ldarg.0
0x11ecb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11ed0  ldarg.0
0x11ed1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11ed6  ldstr    aDialogCopytoDe// "Dialog_CopyTo_Description"
0x11edb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11ee0  ldc.i4.2
0x11ee1  newarr   [mscorlib]System.Object
0x11ee6  dup
0x11ee7  ldc.i4.0
0x11ee8  ldarg.0
0x11ee9  ldflda   int32 Microsoft.Crm.Dialogs.CopyToDialogPage::Total
0x11eee  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11ef3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11ef8  stelem.ref
0x11ef9  dup
0x11efa  ldc.i4.1
0x11efb  ldarg.0
0x11efc  ldfld    string Microsoft.Crm.Dialogs.CopyToDialogPage::ObjName
0x11f01  stelem.ref
0x11f02  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11f07  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x11f0c  ldarg.0
0x11f0d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x11f12  ldc.i4.3
0x11f13  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x11f18  ret
```
