# Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::ConfigurePage

- ea: `0x9c0c0`
- end: `0x9c93f`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::ConfigurePage`
- size: `2175`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x9c0c0`
- `0x9c940`
- `0x9cc10`
- `0x9ccf0`
- `0x9cd50`
- `0x9d160`

## string_xrefs

- `0x9c619`: `update`
- `0x9c187`: `pathAndFileName`
- `0x9c1e0`: `webResourceDependencyXML`
- `0x9c46d`: `dependencyxml`
- `0x9c566`: `dependencyxml`
- `0x9c74d`: `dependencyxml`
- `0x9c7c0`: `dependencyxml`

## pseudocode

```c

```

## disassembly

```asm
0x9c0c0  ldarg.0
0x9c0c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x9c0c6  ldarg.0
0x9c0c7  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::SetScriptFiles()
0x9c0cc  ldarg.0
0x9c0cd  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::InitializeWebResourcePickList()
0x9c0d2  ldarg.0
0x9c0d3  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::libraryLookup
0x9c0d8  ldc.i4.1
0x9c0d9  newarr   [mscorlib]System.Int32
0x9c0de  dup
0x9c0df  ldc.i4.0
0x9c0e0  ldc.i4   0x2475
0x9c0e5  stelem.i4
0x9c0e6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x9c0eb  ldarg.0
0x9c0ec  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::libraryLookup
0x9c0f1  ldc.i4.0
0x9c0f2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_ShowProperty(bool)
0x9c0f7  ldarg.0
0x9c0f8  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::libraryLookup
0x9c0fd  ldc.i4.4
0x9c0fe  stloc.s  0xD
0x9c100  ldloca.s 0xD
0x9c102  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c107  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9c10c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_SavedQueryType(string)
0x9c111  ldarg.0
0x9c112  ldarg.0
0x9c113  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c118  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c11d  ldstr    aId// "id"
0x9c122  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c127  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c12c  ldarg.0
0x9c12d  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c132  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c137  brfalse.s loc_9C154
0x9c139  ldarg.0
0x9c13a  ldarg.0
0x9c13b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c140  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9c145  ldstr    aId// "id"
0x9c14a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c14f  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c154  ldarg.0
0x9c155  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c15a  brfalse.s loc_9C176
0x9c15c  ldarg.0
0x9c15d  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c162  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9c167  brfalse.s loc_9C176
0x9c169  ldarg.0
0x9c16a  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c16f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c174  br.s     loc_9C17B
0x9c176  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c17b  stloc.0
0x9c17c  ldarg.0
0x9c17d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c182  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c187  ldstr    aPathandfilenam// "pathAndFileName"
0x9c18c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c191  stloc.1
0x9c192  ldarg.0
0x9c193  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c198  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c19d  ldstr    aDisplayname_1// "displayName"
0x9c1a2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c1a7  stloc.2
0x9c1a8  ldarg.0
0x9c1a9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c1ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c1b3  ldstr    aDescription// "description"
0x9c1b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c1bd  stloc.3
0x9c1be  ldarg.0
0x9c1bf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c1c4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c1c9  ldstr    aWebresourcetyp// "webResourceType"
0x9c1ce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c1d3  stloc.s  4
0x9c1d5  ldarg.0
0x9c1d6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c1db  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c1e0  ldstr    aWebresourcedep// "webResourceDependencyXML"
0x9c1e5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c1ea  stloc.s  5
0x9c1ec  ldc.i4.0
0x9c1ed  stloc.s  6
0x9c1ef  ldarg.0
0x9c1f0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c1f5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c1fa  ldstr    aIsenabledformo// "IsEnabledForMobileClient"
0x9c1ff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c204  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c209  brtrue.s loc_9C232
0x9c20b  ldarg.0
0x9c20c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c211  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c216  ldstr    aIsenabledformo// "IsEnabledForMobileClient"
0x9c21b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c220  ldstr    aOn_1// "on"
0x9c225  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c22a  brtrue.s loc_9C22F
0x9c22c  ldc.i4.0
0x9c22d  br.s     loc_9C230
0x9c22f  ldc.i4.1
0x9c230  stloc.s  6
0x9c232  ldc.i4.0
0x9c233  stloc.s  7
0x9c235  ldarg.0
0x9c236  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c23b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c240  ldstr    aIsavailablefor// "IsAvailableForMobileOffline"
0x9c245  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c24a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c24f  brtrue.s loc_9C278
0x9c251  ldarg.0
0x9c252  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c257  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c25c  ldstr    aIsavailablefor// "IsAvailableForMobileOffline"
0x9c261  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c266  ldstr    aOn_1// "on"
0x9c26b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c270  brtrue.s loc_9C275
0x9c272  ldc.i4.0
0x9c273  br.s     loc_9C276
0x9c275  ldc.i4.1
0x9c276  stloc.s  7
0x9c278  ldloca.s 8
0x9c27a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9c280  ldarg.0
0x9c281  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c286  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c28b  ldstr    aLanguagecode// "languagecode"
0x9c290  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c295  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c29a  brtrue.s loc_9C2C2
0x9c29c  ldloca.s 8
0x9c29e  ldarg.0
0x9c29f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c2a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c2a9  ldstr    aLanguagecode// "languagecode"
0x9c2ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c2b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c2b8  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x9c2bd  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9c2c2  ldarg.0
0x9c2c3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c2c8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c2cd  ldstr    aSilverlightver_0// "silverlightVersion"
0x9c2d2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c2d7  stloc.s  9
0x9c2d9  ldloc.s  9
0x9c2db  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c2e0  brfalse.s loc_9C2E9
0x9c2e2  ldstr    a40// "4.0"
0x9c2e7  stloc.s  9
0x9c2e9  ldnull
0x9c2ea  stloc.s  0xA
0x9c2ec  ldc.i4.0
0x9c2ed  stloc.s  0xB
0x9c2ef  ldarg.0
0x9c2f0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9c2f5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x9c2fa  ldstr    aClose_0// "close"
0x9c2ff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9c304  ldstr    aTrue_0// "true"
0x9c309  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c30e  brtrue.s loc_9C313
0x9c310  ldc.i4.1
0x9c311  br.s     loc_9C314
0x9c313  ldc.i4.2
0x9c314  stloc.s  0xC
0x9c316  ldloc.1
0x9c317  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c31c  brtrue   loc_9C4E9
0x9c321  ldloc.0
0x9c322  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c327  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9c32c  brfalse  loc_9C4E9
0x9c331  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateWebResource()
0x9c336  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c33b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9c340  brtrue.s loc_9C353
0x9c342  ldc.i4   0x80040277
0x9c347  ldc.i4.0
0x9c348  newarr   [mscorlib]System.Object
0x9c34d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9c352  throw
0x9c353  ldarg.0
0x9c354  ldarg.0
0x9c355  call     instance unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::RetrieveFileData()
0x9c35a  stfld    unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::webResourceContent
0x9c35f  ldarg.0
0x9c360  ldfld    unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::webResourceContent
0x9c365  brtrue.s loc_9C373
0x9c367  ldarg.0
0x9c368  ldc.i4.0
0x9c369  newarr   [mscorlib]System.Byte
0x9c36e  stfld    unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::webResourceContent
0x9c373  ldstr    aWebresource// "webresource"
0x9c378  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c37d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9c382  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9c387  stloc.s  0xA
0x9c389  ldarg.0
0x9c38a  ldfld    unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::webResourceContent
0x9c38f  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x9c394  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9c399  ldc.i4.0
0x9c39a  bgt.s    loc_9C3A3
0x9c39c  ldsfld   string [mscorlib]System.String::Empty
0x9c3a1  br.s     loc_9C3AE
0x9c3a3  ldarg.0
0x9c3a4  ldfld    unsigned int8[] Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::webResourceContent
0x9c3a9  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x9c3ae  stloc.s  0xE
0x9c3b0  ldloc.s  0xA
0x9c3b2  ldstr    aContent_0// "content"
0x9c3b7  ldloc.s  0xE
0x9c3b9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c3be  ldloc.s  0xA
0x9c3c0  ldstr    aWebresourcetyp_0// "webresourcetype"
0x9c3c5  ldloc.s  4
0x9c3c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c3cc  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x9c3d1  box      [mscorlib]System.Int32
0x9c3d6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c3db  ldloca.s 8
0x9c3dd  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x9c3e2  brfalse.s loc_9C3F9
0x9c3e4  ldloc.s  0xA
0x9c3e6  ldstr    aLanguagecode// "languagecode"
0x9c3eb  ldloc.s  8
0x9c3ed  box      valuetype [mscorlib]System.Nullable`1<int32>
0x9c3f2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c3f7  br.s     loc_9C406
0x9c3f9  ldloc.s  0xA
0x9c3fb  ldstr    aLanguagecode// "languagecode"
0x9c400  ldnull
0x9c401  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c406  ldloc.s  4
0x9c408  ldstr    a8// "8"
0x9c40d  ldc.i4.1
0x9c40e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9c413  call     int32 [mscorlib]System.String::Compare(string, string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x9c418  brtrue.s loc_9C428
0x9c41a  ldloc.s  0xA
0x9c41c  ldstr    aSilverlightver_1// "silverlightversion"
0x9c421  ldloc.s  9
0x9c423  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c428  ldarg.0
0x9c429  ldarg.0
0x9c42a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9c42f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_Prefix()
0x9c434  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::solutionPrefix
0x9c439  ldloc.s  0xA
0x9c43b  ldstr    aName// "name"
0x9c440  ldarg.0
0x9c441  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::solutionPrefix
0x9c446  ldloc.1
0x9c447  call     string [mscorlib]System.String::Concat(string, string)
0x9c44c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c451  ldloc.s  0xA
0x9c453  ldstr    aDisplayname// "displayname"
0x9c458  ldloc.2
0x9c459  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c45e  ldloc.s  0xA
0x9c460  ldstr    aDescription// "description"
0x9c465  ldloc.3
0x9c466  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c46b  ldloc.s  0xA
0x9c46d  ldstr    aDependencyxml// "dependencyxml"
0x9c472  ldloc.s  5
0x9c474  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c479  ldloc.s  0xA
0x9c47b  ldstr    aIsenabledformo_0// "isenabledformobileclient"
0x9c480  ldloc.s  6
0x9c482  box      [mscorlib]System.Boolean
0x9c487  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c48c  ldloc.s  0xA
0x9c48e  ldstr    aIsavailablefor_0// "isavailableformobileoffline"
0x9c493  ldloc.s  7
0x9c495  box      [mscorlib]System.Boolean
0x9c49a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x9c49f  ldloc.s  0xA
0x9c4a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c4a6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9c4ab  stloc.0
0x9c4ac  ldloc.s  0xA
0x9c4ae  ldc.i4.0
0x9c4af  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0x9c4b4  ldarg.0
0x9c4b5  ldloca.s 0
0x9c4b7  constrained. [mscorlib]System.Guid
0x9c4bd  callvirt instance string [mscorlib]System.Object::ToString()
0x9c4c2  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::id
0x9c4c7  ldloc.s  5
  ... truncated ...
```
