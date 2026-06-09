# Microsoft.Crm.Application.Pages.Business.Users.AddUsers.SecurityRolesPage::ConfigurePage

- ea: `0xf3bb0`
- end: `0xf3e5c`
- name: `Microsoft.Crm.Application.Pages.Business.Users.AddUsers.SecurityRolesPage::ConfigurePage`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf3bb0`

## string_xrefs

- `0xf3bf1`: `AddUsersWizard.SecurityRolesPage.IntroPrefix`
- `0xf3c0d`: `AddUsersWizard.SecurityRolesPage.IntroFormat`
- `0xf3c41`: `AddUsersWizard.SecurityRolesPage.Intro`
- `0xf3caa`: `roletemplateid`
- `0xf3cd5`: `roletemplateid`
- `0xf3d1b`: `roletemplateid`
- `0xf3d42`: `roletemplateid`
- `0xf3d27`: `SecurityRoles.Custom.Description`
- `0xf3d33`: `SecurityRoles.{0:D}.Description`

## pseudocode

```c

```

## disassembly

```asm
0xf3bb0  ldarg.0
0xf3bb1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf3bb6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf3bbb  ldstr    aUnit// "unit"
0xf3bc0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf3bc5  stloc.0
0xf3bc6  ldloc.0
0xf3bc7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf3bcc  ldc.i4.0
0xf3bcd  ceq
0xf3bcf  ldstr    aMissingBusines// "Missing business unit"
0xf3bd4  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xf3bd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3bde  ldstr    aSpanClassMsCrm_6// "<span class=\"ms-crm-Emphasis-Strong\">"...
0xf3be3  ldc.i4.1
0xf3be4  newarr   [mscorlib]System.Object
0xf3be9  dup
0xf3bea  ldc.i4.0
0xf3beb  ldarg.0
0xf3bec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf3bf1  ldstr    aAdduserswizard_22// "AddUsersWizard.SecurityRolesPage.IntroP"...
0xf3bf6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf3bfb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf3c00  stelem.ref
0xf3c01  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf3c06  stloc.1
0xf3c07  ldarg.0
0xf3c08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf3c0d  ldstr    aAdduserswizard_23// "AddUsersWizard.SecurityRolesPage.IntroF"...
0xf3c12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf3c17  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0xf3c1c  stloc.2
0xf3c1d  ldstr    aSpan// "span"
0xf3c22  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xf3c27  stloc.3
0xf3c28  ldloc.3
0xf3c29  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3c2e  ldloc.2
0xf3c2f  ldc.i4.2
0xf3c30  newarr   [mscorlib]System.Object
0xf3c35  dup
0xf3c36  ldc.i4.0
0xf3c37  ldloc.1
0xf3c38  stelem.ref
0xf3c39  dup
0xf3c3a  ldc.i4.1
0xf3c3b  ldarg.0
0xf3c3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf3c41  ldstr    aAdduserswizard_24// "AddUsersWizard.SecurityRolesPage.Intro"
0xf3c46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf3c4b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf3c50  stelem.ref
0xf3c51  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf3c56  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xf3c5b  ldarg.0
0xf3c5c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Business.Users.AddUsers.SecurityRolesPage::introCell
0xf3c61  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf3c66  ldloc.3
0xf3c67  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xf3c6c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf3c71  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf3c76  ldstr    aRole_0// "Role"
0xf3c7b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0xf3c80  dup
0xf3c81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xf3c86  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xf3c8b  stloc.s  4
0xf3c8d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf3c92  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0xf3c97  dup
0xf3c98  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0xf3c9d  ldloc.s  4
0xf3c9f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xf3ca4  dup
0xf3ca5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0xf3caa  ldstr    aRoletemplateid// "roletemplateid"
0xf3caf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xf3cb4  dup
0xf3cb5  ldloc.s  4
0xf3cb7  ldc.i4.0
0xf3cb8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderType)
0xf3cbd  dup
0xf3cbe  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xf3cc3  ldstr    aBusinessunitid// "businessunitid"
0xf3cc8  ldc.i4.0
0xf3cc9  ldloc.0
0xf3cca  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xf3ccf  dup
0xf3cd0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xf3cd5  ldstr    aRoletemplateid// "roletemplateid"
0xf3cda  ldc.i4.1
0xf3cdb  ldstr    a2d101bb35ced41// "{2D101BB3-5CED-4122-83F1-94D5EFDE4E3B}"
0xf3ce0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xf3ce5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf3cea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf3cef  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xf3cf4  stloc.s  5
0xf3cf6  br       loc_F3E41
0xf3cfb  ldloc.s  5
0xf3cfd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xf3d02  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Role
0xf3d07  stloc.s  6
0xf3d09  ldloc.s  6
0xf3d0b  ldloc.s  4
0xf3d0d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf3d12  castclass [mscorlib]System.String
0xf3d17  stloc.s  7
0xf3d19  ldloc.s  6
0xf3d1b  ldstr    aRoletemplateid// "roletemplateid"
0xf3d20  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0xf3d25  brtrue.s loc_F3D2E
0xf3d27  ldstr    aSecurityrolesC// "SecurityRoles.Custom.Description"
0xf3d2c  br.s     loc_F3D66
0xf3d2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3d33  ldstr    aSecurityroles0// "SecurityRoles.{0:D}.Description"
0xf3d38  ldc.i4.1
0xf3d39  newarr   [mscorlib]System.Object
0xf3d3e  dup
0xf3d3f  ldc.i4.0
0xf3d40  ldloc.s  6
0xf3d42  ldstr    aRoletemplateid// "roletemplateid"
0xf3d47  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf3d4c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xf3d51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xf3d56  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xf3d5b  box      [mscorlib]System.Guid
0xf3d60  stelem.ref
0xf3d61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf3d66  stloc.s  8
0xf3d68  ldarg.0
0xf3d69  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf3d6e  ldloc.s  8
0xf3d70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf3d75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf3d7a  stloc.s  9
0xf3d7c  ldloc.s  9
0xf3d7e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf3d83  ldc.i4.0
0xf3d84  ceq
0xf3d86  ldstr    aNoDescriptionR// "No description resource found for role "...
0xf3d8b  ldc.i4.1
0xf3d8c  newarr   [mscorlib]System.Object
0xf3d91  dup
0xf3d92  ldc.i4.0
0xf3d93  ldloc.s  7
0xf3d95  stelem.ref
0xf3d96  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0xf3d9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3da0  ldstr    aSetdescription// "setDescription(\"{0}\", \"{1}\");"
0xf3da5  ldc.i4.2
0xf3da6  newarr   [mscorlib]System.Object
0xf3dab  dup
0xf3dac  ldc.i4.0
0xf3dad  ldloc.s  7
0xf3daf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xf3db4  stelem.ref
0xf3db5  dup
0xf3db6  ldc.i4.1
0xf3db7  ldloc.s  9
0xf3db9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xf3dbe  stelem.ref
0xf3dbf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf3dc4  stloc.s  0xA
0xf3dc6  ldstr    aCleardescripti// "clearDescription();"
0xf3dcb  stloc.s  0xB
0xf3dcd  ldstr    aSpan// "span"
0xf3dd2  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xf3dd7  stloc.s  0xC
0xf3dd9  ldloc.s  0xC
0xf3ddb  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf3de0  ldstr    aOnmouseover// "onmouseover"
0xf3de5  ldloc.s  0xA
0xf3de7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf3dec  ldloc.s  0xC
0xf3dee  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf3df3  ldstr    aOnmouseout// "onmouseout"
0xf3df8  ldloc.s  0xB
0xf3dfa  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf3dff  ldloc.s  0xC
0xf3e01  ldloc.s  7
0xf3e03  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xf3e08  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf3e0d  stloc.s  0xD
0xf3e0f  ldloc.s  0xD
0xf3e11  ldstr    aOnclick// "onclick"
0xf3e16  ldloc.s  0xA
0xf3e18  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0xf3e1d  ldloc.s  0xD
0xf3e1f  ldstr    aOnblur// "onblur"
0xf3e24  ldloc.s  0xB
0xf3e26  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0xf3e2b  ldarg.0
0xf3e2c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.CheckBoxList Microsoft.Crm.Application.Pages.Business.Users.AddUsers.SecurityRolesPage::securityRoles
0xf3e31  ldloc.s  0xC
0xf3e33  ldloc.s  6
0xf3e35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xf3e3a  ldloc.s  0xD
0xf3e3c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.CheckBoxList::AddItem(class [System.Web]System.Web.UI.Control, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0xf3e41  ldloc.s  5
0xf3e43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf3e48  brtrue   loc_F3CFB
0xf3e4d  leave.s  loc_F3E5B
0xf3e4f  ldloc.s  5
0xf3e51  brfalse.s loc_F3E5A
0xf3e53  ldloc.s  5
0xf3e55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf3e5a  endfinally
0xf3e5b  ret
```
