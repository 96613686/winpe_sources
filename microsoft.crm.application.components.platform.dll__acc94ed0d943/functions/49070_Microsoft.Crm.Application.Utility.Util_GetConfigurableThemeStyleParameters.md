# Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleParameters

- ea: `0x49070`
- end: `0x49178`
- name: `Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleParameters`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x49000`

## callees

- `0xfd20`
- `0x2fb90`
- `0x2fbc0`
- `0x2fca0`
- `0x48ef0`
- `0x49070`
- `0x492e0`

## string_xrefs

- `0x4911b`: `updateTimeStamp`
- `0x4912f`: `updateTimeStamp`
- `0x49160`: `updateTimeStamp`
- `0x4914a`: `Theme Id or Update Time Stamp is not present in theme data.`

## pseudocode

```c

```

## disassembly

```asm
0x49070  ldsfld   string [mscorlib]System.String::Empty
0x49075  stloc.0
0x49076  ldsfld   string [mscorlib]System.String::Empty
0x4907b  stloc.1
0x4907c  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x49081  callvirt instance bool Microsoft.Crm.Application.Security.UserInformation::get_IsUserAuthenticated()
0x49086  brfalse  loc_4915A
0x4908b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x49090  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x49095  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Theme()
0x4909a  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x4909f  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x490a4  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x490a9  brfalse  loc_4915A
0x490ae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x490b3  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x490b8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x490bd  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x490c2  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x490c7  stloc.2
0x490c8  call     bool Microsoft.Crm.Application.Utility.Util::IsPreviewThemeEnabled()
0x490cd  brtrue.s loc_490D7
0x490cf  ldloc.2
0x490d0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_DefaultThemeData()
0x490d5  br.s     loc_490DC
0x490d7  call     string Microsoft.Crm.Application.Utility.Util::GetPreviewThemeData()
0x490dc  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x490e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x490e6  stloc.3
0x490e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x490ec  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x490f1  brtrue.s loc_490FA
0x490f3  ldstr    aF499443d208249// "F499443D-2082-4938-8842-E7EE62DE9A23"
0x490f8  br.s     loc_49119
0x490fa  ldloc.3
0x490fb  ldstr    aThemeid// "themeId"
0x49100  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x49105  brtrue.s loc_4910E
0x49107  ldsfld   string [mscorlib]System.String::Empty
0x4910c  br.s     loc_49119
0x4910e  ldloc.3
0x4910f  ldstr    aThemeid// "themeId"
0x49114  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x49119  stloc.0
0x4911a  ldloc.3
0x4911b  ldstr    aUpdatetimestam// "updateTimeStamp"
0x49120  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x49125  brtrue.s loc_4912E
0x49127  ldsfld   string [mscorlib]System.String::Empty
0x4912c  br.s     loc_49139
0x4912e  ldloc.3
0x4912f  ldstr    aUpdatetimestam// "updateTimeStamp"
0x49134  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x49139  stloc.1
0x4913a  ldloc.0
0x4913b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x49140  brtrue.s loc_4914A
0x49142  ldloc.1
0x49143  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x49148  brfalse.s loc_4915A
0x4914a  ldstr    aThemeIdOrUpdat// "Theme Id or Update Time Stamp is not pr"...
0x4914f  ldc.i4   0x800608D1
0x49154  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x49159  throw
0x4915a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x4915f  dup
0x49160  ldstr    aUpdatetimestam// "updateTimeStamp"
0x49165  ldloc.1
0x49166  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4916b  dup
0x4916c  ldstr    aThemeid// "themeId"
0x49171  ldloc.0
0x49172  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x49177  ret
```
