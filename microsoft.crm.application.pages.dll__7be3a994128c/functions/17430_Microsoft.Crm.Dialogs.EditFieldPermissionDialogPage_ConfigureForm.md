# Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::ConfigureForm

- ea: `0x17430`
- end: `0x1774f`
- name: `Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::ConfigureForm`
- size: `799`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x17430`
- `0x17750`
- `0x17880`
- `0x17ad0`

## string_xrefs

- `0x1764f`: `text/xml`
- `0x17540`: `create`
- `0x1768b`: `XML loaded from the stream returned String.Empty.`
- `0x17695`: `XML loaded from the stream returned String.Empty.`
- `0x17519`: `update`

## pseudocode

```c

```

## disassembly

```asm
0x17430  ldarg.0
0x17431  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x17436  ldarg.0
0x17437  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1743c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17441  ldstr    aPrincipalid// "principalId"
0x17446  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1744b  ldnull
0x1744c  cgt.un
0x1744e  stloc.0
0x1744f  ldarg.0
0x17450  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::divCreateLabel
0x17455  ldloc.0
0x17456  ldc.i4.0
0x17457  ceq
0x17459  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1745e  ldarg.0
0x1745f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::divCreateSelect
0x17464  ldloc.0
0x17465  ldc.i4.0
0x17466  ceq
0x17468  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1746d  ldarg.0
0x1746e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::divCreateDescription
0x17473  ldloc.0
0x17474  ldc.i4.0
0x17475  ceq
0x17477  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1747c  ldarg.0
0x1747d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::divCreateSeparationLine
0x17482  ldloc.0
0x17483  ldc.i4.0
0x17484  ceq
0x17486  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1748b  ldarg.0
0x1748c  ldarg.0
0x1748d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17492  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17497  ldstr    aItotal// "iTotal"
0x1749c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x174a1  ldc.i4.7
0x174a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x174a7  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x174ac  stfld    int32 Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::iTotal
0x174b1  ldarg.0
0x174b2  ldarg.0
0x174b3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x174b8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x174bd  ldstr    aIobjtype// "iObjType"
0x174c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x174c7  ldc.i4.7
0x174c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x174cd  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x174d2  stfld    int32 Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::ObjType
0x174d7  ldarg.0
0x174d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x174dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x174e2  ldstr    aObjectid// "objectId"
0x174e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x174ec  stloc.1
0x174ed  ldarg.0
0x174ee  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x174f3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x174f8  ldstr    aRead// "read"
0x174fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17502  ldc.i4.7
0x17503  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17508  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1750d  stloc.2
0x1750e  ldarg.0
0x1750f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17514  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17519  ldstr    aUpdate// "update"
0x1751e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17523  ldc.i4.7
0x17524  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17529  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1752e  stloc.3
0x1752f  ldc.i4.2
0x17530  stloc.s  4
0x17532  ldloc.0
0x17533  brtrue.s loc_17557
0x17535  ldarg.0
0x17536  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1753b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17540  ldstr    aCreate// "create"
0x17545  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1754a  ldc.i4.7
0x1754b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17550  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x17555  stloc.s  4
0x17557  ldarg.0
0x17558  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1755d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x17562  stloc.s  6
0x17564  ldloc.s  6
0x17566  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1756b  ldc.i4.0
0x1756c  conv.i8
0x1756d  ble      loc_176AD
0x17572  ldloc.s  6
0x17574  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x17579  stloc.s  7
0x1757b  ldloc.s  7
0x1757d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17582  brfalse  loc_17681
0x17587  ldarg.0
0x17588  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1758d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17592  ldstr    aIid// "iId"
0x17597  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1759c  stloc.s  8
0x1759e  ldloc.0
0x1759f  brfalse.s loc_17600
0x175a1  ldarg.0
0x175a2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x175a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x175ac  ldstr    aPrincipalid// "principalId"
0x175b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x175b6  stloc.s  9
0x175b8  ldarg.0
0x175b9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x175be  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x175c3  ldstr    aIprincipaltype// "iPrincipalType"
0x175c8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x175cd  ldc.i4.7
0x175ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x175d3  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x175d8  stloc.s  0xA
0x175da  ldarg.0
0x175db  ldloc.s  9
0x175dd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x175e2  ldloc.s  0xA
0x175e4  ldloc.1
0x175e5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x175ea  ldarg.0
0x175eb  ldfld    int32 Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::ObjType
0x175f0  ldloc.s  8
0x175f2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x175f7  ldloc.2
0x175f8  ldloc.3
0x175f9  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleGrant(valuetype [mscorlib]System.Guid principalId, int32 principalIdType, valuetype [mscorlib]System.Guid objectId, int32 objectTypeCode, valuetype [mscorlib]System.Guid attributeId, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess read, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess update)
0x175fe  br.s     loc_17649
0x17600  ldarg.0
0x17601  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17606  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1760b  ldstr    aAttributename// "attributeName"
0x17610  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17615  stloc.s  0xB
0x17617  ldarg.0
0x17618  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1761d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17622  ldstr    aEntityname_0// "entityName"
0x17627  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1762c  stloc.s  0xC
0x1762e  ldarg.0
0x1762f  ldloc.1
0x17630  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x17635  ldloc.s  8
0x17637  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1763c  ldloc.s  0xC
0x1763e  ldloc.s  0xB
0x17640  ldloc.2
0x17641  ldloc.3
0x17642  ldloc.s  4
0x17644  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleCustomization(valuetype [mscorlib]System.Guid profileId, valuetype [mscorlib]System.Guid fieldPermissionId, string entityName, string attributeName, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess read, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess update, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess create)
0x17649  ldarg.0
0x1764a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1764f  ldstr    aTextXml// "text/xml"
0x17654  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x17659  ldarg.0
0x1765a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1765f  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x17664  ldarg.0
0x17665  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1766a  ldstr    aOk// "<ok/>"
0x1766f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x17674  ldarg.0
0x17675  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1767a  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1767f  br.s     loc_176A5
0x17681  ldloc.s  7
0x17683  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17688  ldc.i4.0
0x17689  cgt.un
0x1768b  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x17690  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x17695  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1769a  ldc.i4   0x80049002
0x1769f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x176a4  throw
0x176a5  leave.s  loc_176BB
0x176a7  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x176ac  throw
0x176ad  leave.s  loc_176BB
0x176af  ldloc.s  6
0x176b1  brfalse.s loc_176BA
0x176b3  ldloc.s  6
0x176b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x176ba  endfinally
0x176bb  ldarg.0
0x176bc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x176c1  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x176c6  stloc.s  5
0x176c8  ldloc.s  5
0x176ca  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x176cf  ldarg.0
0x176d0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x176d5  ldstr    aDialogEditfiel// "Dialog_EditFieldPermission_Title"
0x176da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x176df  ldc.i4.0
0x176e0  newarr   [mscorlib]System.Object
0x176e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x176ea  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x176ef  ldloc.s  5
0x176f1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x176f6  ldarg.0
0x176f7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x176fc  ldstr    aDialogEditfiel_0// "Dialog_EditFieldPermission_Description"
0x17701  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17706  ldc.i4.0
0x17707  newarr   [mscorlib]System.Object
0x1770c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17711  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x17716  ldloc.s  5
0x17718  dup
0x17719  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_ButtonStyle()
0x1771e  ldc.i4.s 0x20
0x17720  or
0x17721  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x17726  ldarg.0
0x17727  ldloc.2
0x17728  ldarg.0
0x17729  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::readSelect
0x1772e  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetSelectContent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select select)
0x17733  ldarg.0
0x17734  ldloc.3
0x17735  ldarg.0
0x17736  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::updateSelect
0x1773b  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetSelectContent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select select)
0x17740  ldarg.0
0x17741  ldloc.s  4
0x17743  ldarg.0
0x17744  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::createSelect
0x17749  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetSelectContent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select select)
0x1774e  ret
```
