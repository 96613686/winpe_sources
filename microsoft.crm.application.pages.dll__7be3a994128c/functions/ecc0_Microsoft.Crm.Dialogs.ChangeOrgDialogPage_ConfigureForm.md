# Microsoft.Crm.Dialogs.ChangeOrgDialogPage::ConfigureForm

- ea: `0xecc0`
- end: `0xf10f`
- name: `Microsoft.Crm.Dialogs.ChangeOrgDialogPage::ConfigureForm`
- size: `1103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xec10`
- `0xecc0`

## string_xrefs

- `0xef77`: `text/xml`
- `0xefba`: `ChangeOrg_Warning_MovedUsersWillLoseRoles`
- `0xefd5`: `ChangeOrg_Warning_MovedTeamsWillLoseRoles`
- `0xf0e7`: `Dialog_ChangeOrg_DescriptionTeamSingular`

## pseudocode

```c

```

## disassembly

```asm
0xecc0  ldarg.0
0xecc1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xecc6  ldarg.0
0xecc7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xeccc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xecd1  ldstr    aIobjtype// "iObjType"
0xecd6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xecdb  ldc.i4.7
0xecdc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xece1  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xece6  stloc.0
0xece7  ldarg.0
0xece8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeced  ldstr    aIobjtype_0// "_iObjType"
0xecf2  ldloca.s 0
0xecf4  ldstr    aD// "D"
0xecf9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xecfe  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xed03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xed08  ldarg.0
0xed09  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xed0e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xed13  ldstr    aItotal// "iTotal"
0xed18  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xed1d  ldc.i4.7
0xed1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed23  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xed28  stloc.1
0xed29  ldsfld   string [mscorlib]System.String::Empty
0xed2e  stloc.2
0xed2f  ldloc.1
0xed30  ldc.i4.1
0xed31  beq.s    loc_ED3D
0xed33  ldloc.0
0xed34  ldc.i4.2
0xed35  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xed3a  stloc.2
0xed3b  br.s     loc_ED45
0xed3d  ldloc.0
0xed3e  ldc.i4.1
0xed3f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xed44  stloc.2
0xed45  ldarg.0
0xed46  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xed4b  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xed50  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xed55  ldc.i4.0
0xed56  conv.i8
0xed57  ble      loc_EFAF
0xed5c  ldarg.0
0xed5d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xed62  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xed67  ldstr    aIid// "iId"
0xed6c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xed71  brfalse  loc_EFA7
0xed76  ldarg.0
0xed77  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xed7c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xed81  ldstr    aOwnerid_0// "ownerId"
0xed86  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xed8b  brfalse  loc_EFA7
0xed90  ldarg.0
0xed91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xed96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xed9b  ldstr    aIid// "iId"
0xeda0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xeda5  ldc.i4.1
0xeda6  newarr   [mscorlib]System.Char
0xedab  dup
0xedac  ldc.i4.0
0xedad  ldc.i4.s 0x3B
0xedaf  stelem.i2
0xedb0  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xedb5  stloc.s  4
0xedb7  ldarg.0
0xedb8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xedbd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xedc2  ldstr    aOwnerid_0// "ownerId"
0xedc7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xedcc  stloc.s  5
0xedce  ldarg.0
0xedcf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xedd4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xedd9  ldstr    aIobjtype// "iObjType"
0xedde  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xede3  ldc.i4.7
0xede4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xede9  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xedee  stloc.s  6
0xedf0  ldloc.s  6
0xedf2  ldc.i4.8
0xedf3  beq.s    loc_EE3F
0xedf5  ldloc.s  6
0xedf7  ldc.i4.s 9
0xedf9  beq.s    loc_EE0C
0xedfb  ldloc.s  6
0xedfd  ldc.i4   0xFA0
0xee02  beq      loc_EF0D
0xee07  br       loc_EF71
0xee0c  ldc.i4.0
0xee0d  stloc.s  9
0xee0f  br.s     loc_EE32
0xee11  ldloc.s  4
0xee13  ldloc.s  9
0xee15  ldelem.ref
0xee16  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xee1b  ldloc.s  5
0xee1d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xee22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xee27  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetParentTeam(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xee2c  ldloc.s  9
0xee2e  ldc.i4.1
0xee2f  add
0xee30  stloc.s  9
0xee32  ldloc.s  9
0xee34  ldloc.s  4
0xee36  ldlen
0xee37  conv.i4
0xee38  blt.s    loc_EE11
0xee3a  br       loc_EF71
0xee3f  ldc.i4.0
0xee40  stloc.s  7
0xee42  ldloca.s 8
0xee44  ldloc.s  5
0xee46  call     instance void [mscorlib]System.Guid::.ctor(string)
0xee4b  ldc.i4.0
0xee4c  stloc.s  0xA
0xee4e  br       loc_EEED
0xee53  ldloca.s 0xB
0xee55  ldloc.s  4
0xee57  ldloc.s  0xA
0xee59  ldelem.ref
0xee5a  call     instance void [mscorlib]System.Guid::.ctor(string)
0xee5f  ldarg.0
0xee60  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xee65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xee6a  ldloc.s  0xB
0xee6c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xee71  brfalse.s loc_EE8C
0xee73  ldarg.0
0xee74  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xee79  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0xee7e  ldloc.s  8
0xee80  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xee85  brfalse.s loc_EEE7
0xee87  ldc.i4.1
0xee88  stloc.s  7
0xee8a  br.s     loc_EEE7
0xee8c  ldc.i4.1
0xee8d  newarr   [mscorlib]System.String
0xee92  dup
0xee93  ldc.i4.0
0xee94  ldstr    aBusinessunitid// "businessunitid"
0xee99  stelem.ref
0xee9a  stloc.s  0xC
0xee9c  ldstr    aSystemuser// "systemuser"
0xeea1  ldloc.s  0xB
0xeea3  ldloc.s  0xC
0xeea5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xeeaa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xeeaf  ldstr    aBusinessunitid// "businessunitid"
0xeeb4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xeeb9  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xeebe  stloc.s  0xD
0xeec0  ldloc.s  0xD
0xeec2  brfalse.s loc_EEE7
0xeec4  ldloc.s  5
0xeec6  ldloc.s  0xD
0xeec8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xeecd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xeed2  brfalse.s loc_EEE7
0xeed4  ldloc.s  0xB
0xeed6  ldloc.s  8
0xeed8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xeedd  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetBusinessSystemUserCommand::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xeee2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetBusinessSystemUserCommand::Execute()
0xeee7  ldloc.s  0xA
0xeee9  ldc.i4.1
0xeeea  add
0xeeeb  stloc.s  0xA
0xeeed  ldloc.s  0xA
0xeeef  ldloc.s  4
0xeef1  ldlen
0xeef2  conv.i4
0xeef3  blt      loc_EE53
0xeef8  ldloc.s  7
0xeefa  brfalse.s loc_EF71
0xeefc  ldc.i4   0x80049003
0xef01  ldc.i4.0
0xef02  newarr   [mscorlib]System.Object
0xef07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xef0c  throw
0xef0d  ldc.i4.0
0xef0e  stloc.s  0xE
0xef10  br.s     loc_EF69
0xef12  ldstr    aEquipment// "equipment"
0xef17  ldarg.0
0xef18  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Dialogs.ChangeOrgDialogPage::get_OrgContext()
0xef1d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xef22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xef27  dup
0xef28  ldstr    aId// "id"
0xef2d  ldloc.s  4
0xef2f  ldloc.s  0xE
0xef31  ldelem.ref
0xef32  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xef37  box      [mscorlib]System.Guid
0xef3c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xef41  dup
0xef42  ldstr    aBusinessunitid// "businessunitid"
0xef47  ldloc.s  5
0xef49  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xef4e  box      [mscorlib]System.Guid
0xef53  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xef58  ldarg.0
0xef59  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Dialogs.ChangeOrgDialogPage::get_OrgContext()
0xef5e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xef63  ldloc.s  0xE
0xef65  ldc.i4.1
0xef66  add
0xef67  stloc.s  0xE
0xef69  ldloc.s  0xE
0xef6b  ldloc.s  4
0xef6d  ldlen
0xef6e  conv.i4
0xef6f  blt.s    loc_EF12
0xef71  ldarg.0
0xef72  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xef77  ldstr    aTextXml// "text/xml"
0xef7c  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xef81  ldarg.0
0xef82  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xef87  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0xef8c  ldarg.0
0xef8d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xef92  ldstr    aOk// "<ok/>"
0xef97  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xef9c  ldarg.0
0xef9d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xefa2  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0xefa7  leave.s  loc_EFAF
0xefa9  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xefae  throw
0xefaf  ldloc.0
0xefb0  ldc.i4.8
0xefb1  bne.un.s loc_EFC9
0xefb3  ldarg.0
0xefb4  ldarg.0
0xefb5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xefba  ldstr    aChangeorgWarni// "ChangeOrg_Warning_MovedUsersWillLoseRol"...
0xefbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xefc4  stfld    string Microsoft.Crm.Dialogs.ChangeOrgDialogPage::userWarning
0xefc9  ldloc.0
0xefca  ldc.i4.s 9
0xefcc  bne.un.s loc_EFE4
0xefce  ldarg.0
0xefcf  ldarg.0
0xefd0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xefd5  ldstr    aChangeorgWarni_0// "ChangeOrg_Warning_MovedTeamsWillLoseRol"...
0xefda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xefdf  stfld    string Microsoft.Crm.Dialogs.ChangeOrgDialogPage::userWarning
0xefe4  ldarg.0
0xefe5  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.ChangeOrgDialogPage::crmLookup
0xefea  ldc.i4.1
0xefeb  newarr   [mscorlib]System.Int32
0xeff0  dup
0xeff1  ldc.i4.0
0xeff2  ldc.i4.s 0xA
0xeff4  stelem.i4
0xeff5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xeffa  ldarg.0
0xeffb  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.ChangeOrgDialogPage::crmLookup
0xf000  ldc.i4.s 0xA
0xf002  ldc.i4.1
0xf003  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xf008  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0xf00d  ldarg.0
0xf00e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf013  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xf018  stloc.3
0xf019  ldloc.3
0xf01a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xf01f  ldarg.0
0xf020  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf025  ldstr    aDialogChangeor// "Dialog_ChangeOrg_Title"
0xf02a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf02f  ldc.i4.0
0xf030  newarr   [mscorlib]System.Object
0xf035  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf03a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf03f  ldloc.0
0xf040  ldc.i4.8
0xf041  beq.s    loc_F091
0xf043  ldloc.0
0xf044  ldc.i4.s 9
0xf046  beq      loc_F0D0
0xf04b  ldloc.0
0xf04c  ldc.i4   0xFA0
0xf051  bne.un   loc_F10E
0xf056  ldloc.3
  ... truncated ...
```
