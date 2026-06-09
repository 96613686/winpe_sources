# Microsoft.Crm.Dialogs.RemoveRolesDialogPage::ConfigureForm

- ea: `0x1aff0`
- end: `0x1b2d7`
- name: `Microsoft.Crm.Dialogs.RemoveRolesDialogPage::ConfigureForm`
- size: `743`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1aff0`

## string_xrefs

- `0x1b166`: `text/xml`
- `0x1b1a1`: `XML loaded from the stream returned String.Empty.`
- `0x1b1ab`: `XML loaded from the stream returned String.Empty.`
- `0x1b1d5`: `Dialog_RemoveRoles_Title`
- `0x1b1ef`: `Dialog_RemoveRoles_Description`
- `0x1b216`: `Dialog_RemoveRoles_Description_Casing`
- `0x1b28a`: `Web._grid.cmds.dlg_removeroles.aspx_68`
- `0x1b2a3`: `Web._grid.cmds.dlg_removeroles.aspx_68_Casing0`
- `0x1b2bc`: `Web._grid.cmds.dlg_removeroles.aspx_68_Casing1`

## pseudocode

```c

```

## disassembly

```asm
0x1aff0  ldarg.0
0x1aff1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1aff6  ldarg.0
0x1aff7  ldarg.0
0x1aff8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1affd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b002  ldstr    aItotal// "iTotal"
0x1b007  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b00c  ldc.i4.7
0x1b00d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b012  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b017  stfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iTotal
0x1b01c  ldarg.0
0x1b01d  ldarg.0
0x1b01e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b023  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b028  ldstr    aIobjtype// "iObjType"
0x1b02d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b032  ldc.i4.7
0x1b033  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b038  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b03d  stfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::ObjType
0x1b042  ldarg.0
0x1b043  ldarg.0
0x1b044  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b049  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b04e  ldstr    aIallroles// "iAllRoles"
0x1b053  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b058  ldc.i4.7
0x1b059  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b05e  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1b063  stfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iAllRoles
0x1b068  ldarg.0
0x1b069  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::ObjType
0x1b06e  ldc.i4.1
0x1b06f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b074  stloc.0
0x1b075  ldc.i4   0x40C
0x1b07a  ldarg.0
0x1b07b  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iTotal
0x1b080  ldc.i4.1
0x1b081  bne.un.s loc_1B086
0x1b083  ldc.i4.1
0x1b084  br.s     loc_1B087
0x1b086  ldc.i4.2
0x1b087  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1b08c  stloc.1
0x1b08d  ldarg.0
0x1b08e  ldarg.0
0x1b08f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x1b094  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x1b099  ldarg.0
0x1b09a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b09f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b0a4  ldstr    aUserid_0// "userid"
0x1b0a9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b0ae  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b0b3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b0b8  stfld    bool Microsoft.Crm.Dialogs.RemoveRolesDialogPage::RemovingOwnRole
0x1b0bd  ldarg.0
0x1b0be  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b0c3  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1b0c8  stloc.2
0x1b0c9  ldloc.2
0x1b0ca  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1b0cf  ldc.i4.0
0x1b0d0  conv.i8
0x1b0d1  ble      loc_1B1C3
0x1b0d6  ldloc.2
0x1b0d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1b0dc  stloc.3
0x1b0dd  ldloc.3
0x1b0de  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b0e3  brfalse  loc_1B198
0x1b0e8  ldc.i4.1
0x1b0e9  newarr   [mscorlib]System.Guid
0x1b0ee  stloc.s  4
0x1b0f0  ldloc.s  4
0x1b0f2  ldc.i4.0
0x1b0f3  ldarg.0
0x1b0f4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b0f9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b0fe  ldstr    aIid// "iId"
0x1b103  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b108  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b10d  stelem   [mscorlib]System.Guid
0x1b112  ldarg.0
0x1b113  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b118  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b11d  ldstr    aUserid_0// "userid"
0x1b122  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b127  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x1b12c  stloc.s  5
0x1b12e  ldarg.0
0x1b12f  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::ObjType
0x1b134  ldc.i4.s 9
0x1b136  bne.un.s loc_1B14D
0x1b138  ldloc.s  5
0x1b13a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b13f  ldloc.s  4
0x1b141  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b146  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveTeamRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b14b  br.s     loc_1B160
0x1b14d  ldloc.s  5
0x1b14f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1b154  ldloc.s  4
0x1b156  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b15b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveUserRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b160  ldarg.0
0x1b161  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b166  ldstr    aTextXml// "text/xml"
0x1b16b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1b170  ldarg.0
0x1b171  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b176  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1b17b  ldarg.0
0x1b17c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b181  ldstr    aOk// "<ok/>"
0x1b186  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1b18b  ldarg.0
0x1b18c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1b191  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1b196  br.s     loc_1B1BB
0x1b198  ldloc.3
0x1b199  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b19e  ldc.i4.0
0x1b19f  cgt.un
0x1b1a1  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b1a6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1b1ab  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1b1b0  ldc.i4   0x80049002
0x1b1b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1b1ba  throw
0x1b1bb  leave.s  loc_1B1C3
0x1b1bd  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1b1c2  throw
0x1b1c3  ldarg.0
0x1b1c4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1b1c9  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1b1ce  dup
0x1b1cf  ldarg.0
0x1b1d0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b1d5  ldstr    aDialogRemovero// "Dialog_RemoveRoles_Title"
0x1b1da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b1df  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1b1e4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b1e9  ldarg.0
0x1b1ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b1ef  ldstr    aDialogRemovero_0// "Dialog_RemoveRoles_Description"
0x1b1f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b1f9  ldc.i4.2
0x1b1fa  newarr   [mscorlib]System.Object
0x1b1ff  dup
0x1b200  ldc.i4.0
0x1b201  ldarg.0
0x1b202  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iTotal
0x1b207  box      [mscorlib]System.Int32
0x1b20c  stelem.ref
0x1b20d  dup
0x1b20e  ldc.i4.1
0x1b20f  ldloc.1
0x1b210  ldarg.0
0x1b211  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b216  ldstr    aDialogRemovero_1// "Dialog_RemoveRoles_Description_Casing"
0x1b21b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b220  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b225  stelem.ref
0x1b226  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b22b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1b230  ldarg.0
0x1b231  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iTotal
0x1b236  ldarg.0
0x1b237  ldfld    int32 Microsoft.Crm.Dialogs.RemoveRolesDialogPage::iAllRoles
0x1b23c  bne.un.s loc_1B27E
0x1b23e  ldarg.0
0x1b23f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b244  ldarg.0
0x1b245  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b24a  ldstr    aWebGridCmdsDlg_77// "Web._grid.cmds.dlg_role.aspx_87"
0x1b24f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b254  ldc.i4.1
0x1b255  newarr   [mscorlib]System.Object
0x1b25a  dup
0x1b25b  ldc.i4.0
0x1b25c  ldloc.0
0x1b25d  ldarg.0
0x1b25e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b263  ldstr    aWebGridCmdsDlg_78// "Web._grid.cmds.dlg_role.aspx_87_Casing"
0x1b268  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b26d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b272  stelem.ref
0x1b273  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b278  stfld    string Microsoft.Crm.Dialogs.RemoveRolesDialogPage::message
0x1b27d  ret
0x1b27e  ldarg.0
0x1b27f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1b284  ldarg.0
0x1b285  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b28a  ldstr    aWebGridCmdsDlg_79// "Web._grid.cmds.dlg_removeroles.aspx_68"
0x1b28f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b294  ldc.i4.2
0x1b295  newarr   [mscorlib]System.Object
0x1b29a  dup
0x1b29b  ldc.i4.0
0x1b29c  ldloc.1
0x1b29d  ldarg.0
0x1b29e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b2a3  ldstr    aWebGridCmdsDlg_80// "Web._grid.cmds.dlg_removeroles.aspx_68_"...
0x1b2a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b2ad  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b2b2  stelem.ref
0x1b2b3  dup
0x1b2b4  ldc.i4.1
0x1b2b5  ldloc.0
0x1b2b6  ldarg.0
0x1b2b7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1b2bc  ldstr    aWebGridCmdsDlg_81// "Web._grid.cmds.dlg_removeroles.aspx_68_"...
0x1b2c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b2c6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x1b2cb  stelem.ref
0x1b2cc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b2d1  stfld    string Microsoft.Crm.Dialogs.RemoveRolesDialogPage::message
0x1b2d6  ret
```
