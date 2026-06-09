# Microsoft.Crm.Dialogs.RoleDialogPage::ConfigureForm

- ea: `0x1bda0`
- end: `0x1c074`
- name: `Microsoft.Crm.Dialogs.RoleDialogPage::ConfigureForm`
- size: `724`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1bda0`
- `0x1c080`
- `0x1c0f0`

## string_xrefs

- `0x1bf53`: `text/xml`
- `0x1bf03`: `remove`
- `0x1bf85`: `XML loaded from the stream returned String.Empty.`
- `0x1c02b`: `<img alt="" id="_gccimg" src="/_imgs/securityinfo_16.png">`

## pseudocode

```c

```

## disassembly

```asm
0x1bda0  ldarg.0
0x1bda1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1bda6  ldarg.0
0x1bda7  ldarg.0
0x1bda8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1bdad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bdb2  ldstr    aItotal// "iTotal"
0x1bdb7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bdbc  ldc.i4.7
0x1bdbd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bdc2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1bdc7  stfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::iTotal
0x1bdcc  ldarg.0
0x1bdcd  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::iTotal
0x1bdd2  ldc.i4.1
0x1bdd3  beq.s    loc_1BDE9
0x1bdd5  ldarg.0
0x1bdd6  ldarg.0
0x1bdd7  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1bddc  ldc.i4.2
0x1bddd  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1bde2  stfld    string Microsoft.Crm.Dialogs.RoleDialogPage::ObjName
0x1bde7  br.s     loc_1BDFB
0x1bde9  ldarg.0
0x1bdea  ldarg.0
0x1bdeb  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1bdf0  ldc.i4.1
0x1bdf1  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1bdf6  stfld    string Microsoft.Crm.Dialogs.RoleDialogPage::ObjName
0x1bdfb  ldarg.0
0x1bdfc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1be01  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1be06  stloc.0
0x1be07  ldloc.0
0x1be08  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1be0d  ldc.i4.0
0x1be0e  conv.i8
0x1be0f  ble      loc_1BF9D
0x1be14  ldloc.0
0x1be15  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x1be1a  stloc.2
0x1be1b  ldloc.2
0x1be1c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1be21  brtrue   loc_1BF85
0x1be26  ldarg.0
0x1be27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1be2c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1be31  ldstr    aIid// "iId"
0x1be36  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1be3b  stloc.3
0x1be3c  ldloca.s 4
0x1be3e  ldarg.0
0x1be3f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1be44  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1be49  ldstr    aIid// "iId"
0x1be4e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1be53  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1be58  ldc.i4.1
0x1be59  newarr   [mscorlib]System.String
0x1be5e  dup
0x1be5f  ldc.i4.0
0x1be60  ldstr    aBusinessunitid// "businessunitid"
0x1be65  stelem.ref
0x1be66  stloc.s  5
0x1be68  ldarg.0
0x1be69  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1be6e  ldc.i4.s 9
0x1be70  bne.un.s loc_1BE7B
0x1be72  ldstr    aTeam// "team"
0x1be77  stloc.s  6
0x1be79  br.s     loc_1BE82
0x1be7b  ldstr    aSystemuser// "systemuser"
0x1be80  stloc.s  6
0x1be82  ldloc.s  6
0x1be84  ldloc.s  4
0x1be86  ldloc.s  5
0x1be88  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1be8d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1be92  ldstr    aBusinessunitid// "businessunitid"
0x1be97  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1be9c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1bea1  stloc.s  7
0x1bea3  ldarg.0
0x1bea4  ldloc.s  7
0x1bea6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1beab  ldloc.2
0x1beac  call     instance string Microsoft.Crm.Dialogs.RoleDialogPage::FindValidRolesForBusiness(string businessId, string roleXml)
0x1beb1  stloc.2
0x1beb2  ldnull
0x1beb3  stloc.s  8
0x1beb5  ldarg.0
0x1beb6  ldloc.2
0x1beb7  ldstr    aAdd// "add"
0x1bebc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeInnerXml(string, string)
0x1bec1  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Dialogs.RoleDialogPage::ParseRolesToArray(string roleXml)
0x1bec6  stloc.s  8
0x1bec8  ldloc.s  8
0x1beca  brfalse.s loc_1BF01
0x1becc  ldloc.s  8
0x1bece  ldlen
0x1becf  brfalse.s loc_1BF01
0x1bed1  ldarg.0
0x1bed2  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1bed7  ldc.i4.s 9
0x1bed9  bne.un.s loc_1BEEF
0x1bedb  ldloc.3
0x1bedc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1bee1  ldloc.s  8
0x1bee3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bee8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::AssignTeamRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1beed  br.s     loc_1BF01
0x1beef  ldloc.3
0x1bef0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1bef5  ldloc.s  8
0x1bef7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1befc  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::AssignUserRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bf01  ldarg.0
0x1bf02  ldloc.2
0x1bf03  ldstr    aRemove// "remove"
0x1bf08  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeInnerXml(string, string)
0x1bf0d  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Dialogs.RoleDialogPage::ParseRolesToArray(string roleXml)
0x1bf12  stloc.s  8
0x1bf14  ldloc.s  8
0x1bf16  brfalse.s loc_1BF4D
0x1bf18  ldloc.s  8
0x1bf1a  ldlen
0x1bf1b  brfalse.s loc_1BF4D
0x1bf1d  ldarg.0
0x1bf1e  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1bf23  ldc.i4.s 9
0x1bf25  bne.un.s loc_1BF3B
0x1bf27  ldloc.3
0x1bf28  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1bf2d  ldloc.s  8
0x1bf2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bf34  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveTeamRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bf39  br.s     loc_1BF4D
0x1bf3b  ldloc.3
0x1bf3c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1bf41  ldloc.s  8
0x1bf43  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bf48  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RemoveUserRolesRole(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bf4d  ldarg.0
0x1bf4e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bf53  ldstr    aTextXml// "text/xml"
0x1bf58  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1bf5d  ldarg.0
0x1bf5e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bf63  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1bf68  ldarg.0
0x1bf69  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bf6e  ldstr    aOk// "<ok/>"
0x1bf73  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bf78  ldarg.0
0x1bf79  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bf7e  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1bf83  br.s     loc_1BF95
0x1bf85  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x1bf8a  ldc.i4   0x80049002
0x1bf8f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1bf94  throw
0x1bf95  leave.s  loc_1BF9D
0x1bf97  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x1bf9c  throw
0x1bf9d  ldarg.0
0x1bf9e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1bfa3  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1bfa8  stloc.1
0x1bfa9  ldarg.0
0x1bfaa  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::ObjType
0x1bfaf  ldc.i4.s 9
0x1bfb1  bne.un.s loc_1BFCB
0x1bfb3  ldloc.1
0x1bfb4  ldarg.0
0x1bfb5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1bfba  ldstr    aDialogTeamRole// "Dialog_Team_Role_Title"
0x1bfbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1bfc4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1bfc9  br.s     loc_1BFE1
0x1bfcb  ldloc.1
0x1bfcc  ldarg.0
0x1bfcd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1bfd2  ldstr    aDialogRoleTitl// "Dialog_Role_Title"
0x1bfd7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1bfdc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1bfe1  ldloc.1
0x1bfe2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1bfe7  ldarg.0
0x1bfe8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1bfed  ldstr    aDialogRoleDesc// "Dialog_Role_Description"
0x1bff2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1bff7  ldc.i4.2
0x1bff8  newarr   [mscorlib]System.Object
0x1bffd  dup
0x1bffe  ldc.i4.0
0x1bfff  ldarg.0
0x1c000  ldfld    int32 Microsoft.Crm.Dialogs.RoleDialogPage::iTotal
0x1c005  box      [mscorlib]System.Int32
0x1c00a  stelem.ref
0x1c00b  dup
0x1c00c  ldc.i4.1
0x1c00d  ldarg.0
0x1c00e  ldfld    string Microsoft.Crm.Dialogs.RoleDialogPage::ObjName
0x1c013  stelem.ref
0x1c014  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c019  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1c01e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1c023  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1c028  ldc.i4.2
0x1c029  bne.un.s loc_1C068
0x1c02b  ldstr    aImgAltIdGccimg// "<img alt=\"\" id=\"_gccimg\" src=\"/_im"...
0x1c030  stloc.s  9
0x1c032  ldarg.0
0x1c033  ldstr    aDivStyleHeight// "<div style='height: 20px'></div>"
0x1c038  ldloc.s  9
0x1c03a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1c03f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1c044  ldstr    aGcclegaldiscla// "GCCLegalDisclaimer.Roles"
0x1c049  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c04e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1c053  ldc.i4.0
0x1c054  newarr   [mscorlib]System.Object
0x1c059  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c05e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c063  stfld    string Microsoft.Crm.Dialogs.RoleDialogPage::GCCLegalDisclaimer
0x1c068  ldloc.1
0x1c069  ldc.i4   0x1C2
0x1c06e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x1c073  ret
```
