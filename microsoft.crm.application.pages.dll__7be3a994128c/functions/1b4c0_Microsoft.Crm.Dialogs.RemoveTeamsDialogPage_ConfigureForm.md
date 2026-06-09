# Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ConfigureForm

- ea: `0x1b4c0`
- end: `0x1b69b`
- name: `Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ConfigureForm`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1b4c0`

## string_xrefs

- `0x1b5b9`: `text/xml`
- `0x1b5f4`: `XML loaded from the stream returned String.Empty.`
- `0x1b5fe`: `XML loaded from the stream returned String.Empty.`
- `0x1b62e`: `Dialog_RemoveTeams_Title`
- `0x1b654`: `Dialog_RemoveTeams_Description`
- `0x1b680`: `Dialog_RemoveTeams_Description_Casing`

## pseudocode

```c

```

## disassembly

```asm
0x1b4c0  ldarg.0
0x1b4c1  ldarg.0
0x1b4c2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b4c7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b4cc  ldstr    aItotal// "iTotal"
0x1b4d1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b4d6  ldc.i4.7
0x1b4d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b4dc  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b4e1  stfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::iTotal
0x1b4e6  ldarg.0
0x1b4e7  ldarg.0
0x1b4e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b4ed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b4f2  ldstr    aIobjtype// "iObjType"
0x1b4f7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b4fc  ldc.i4.7
0x1b4fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b502  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b507  stfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjType
0x1b50c  ldarg.0
0x1b50d  ldfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::iTotal
0x1b512  ldc.i4.1
0x1b513  beq.s    loc_1B529
0x1b515  ldarg.0
0x1b516  ldarg.0
0x1b517  ldfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjType
0x1b51c  ldc.i4.2
0x1b51d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b522  stfld    string Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjName
0x1b527  br.s     loc_1B53B
0x1b529  ldarg.0
0x1b52a  ldarg.0
0x1b52b  ldfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjType
0x1b530  ldc.i4.1
0x1b531  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b536  stfld    string Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjName
0x1b53b  ldarg.0
0x1b53c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b541  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1b546  stloc.0
0x1b547  ldloc.0
0x1b548  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1b54d  ldc.i4.0
0x1b54e  conv.i8
0x1b54f  ble      loc_1B616
0x1b554  ldloc.0
0x1b555  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1b55a  stloc.2
0x1b55b  ldloc.2
0x1b55c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b561  brfalse  loc_1B5EB
0x1b566  ldc.i4.1
0x1b567  newarr   [mscorlib]System.String
0x1b56c  stloc.3
0x1b56d  ldloc.3
0x1b56e  ldc.i4.0
0x1b56f  ldarg.0
0x1b570  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b575  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b57a  ldstr    aUserid_0// "userid"
0x1b57f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b584  stelem.ref
0x1b585  ldarg.0
0x1b586  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b58b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b590  ldstr    aIid// "iId"
0x1b595  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b59a  ldloc.3
0x1b59b  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ConvertStringArrayToGuidArray(string[])
0x1b5a0  stloc.s  4
0x1b5a2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b5a7  ldloc.s  4
0x1b5a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b5ae  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveMembersTeam(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b5b3  ldarg.0
0x1b5b4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b5b9  ldstr    aTextXml// "text/xml"
0x1b5be  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1b5c3  ldarg.0
0x1b5c4  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b5c9  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1b5ce  ldarg.0
0x1b5cf  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b5d4  ldstr    aOk// "<ok/>"
0x1b5d9  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1b5de  ldarg.0
0x1b5df  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b5e4  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1b5e9  br.s     loc_1B60E
0x1b5eb  ldloc.2
0x1b5ec  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b5f1  ldc.i4.0
0x1b5f2  cgt.un
0x1b5f4  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b5f9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1b5fe  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b603  ldc.i4   0x80049002
0x1b608  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1b60d  throw
0x1b60e  leave.s  loc_1B616
0x1b610  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1b615  throw
0x1b616  ldarg.0
0x1b617  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1b61c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1b621  stloc.1
0x1b622  ldloc.1
0x1b623  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b628  ldarg.0
0x1b629  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b62e  ldstr    aDialogRemovete// "Dialog_RemoveTeams_Title"
0x1b633  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b638  ldc.i4.0
0x1b639  newarr   [mscorlib]System.Object
0x1b63e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b643  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1b648  ldloc.1
0x1b649  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b64e  ldarg.0
0x1b64f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b654  ldstr    aDialogRemovete_0// "Dialog_RemoveTeams_Description"
0x1b659  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b65e  ldc.i4.2
0x1b65f  newarr   [mscorlib]System.Object
0x1b664  dup
0x1b665  ldc.i4.0
0x1b666  ldarg.0
0x1b667  ldfld    int32 Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::iTotal
0x1b66c  box      [mscorlib]System.Int32
0x1b671  stelem.ref
0x1b672  dup
0x1b673  ldc.i4.1
0x1b674  ldarg.0
0x1b675  ldfld    string Microsoft.Crm.Dialogs.RemoveTeamsDialogPage::ObjName
0x1b67a  ldarg.0
0x1b67b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b680  ldstr    aDialogRemovete_1// "Dialog_RemoveTeams_Description_Casing"
0x1b685  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b68a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b68f  stelem.ref
0x1b690  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b695  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1b69a  ret
```
