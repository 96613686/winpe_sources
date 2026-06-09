# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddAppModuleGlobalVariables

- ea: `0x1a420`
- end: `0x1a548`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddAppModuleGlobalVariables`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a050`

## callees

- `0x19f10`
- `0x1a420`

## string_xrefs

- `0x1a510`: `APP_MODULE_WELCOME_ID`
- `0x1a532`: `APP_MODULE_WELCOME_NAME`

## pseudocode

```c

```

## disassembly

```asm
0x1a420  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1a425  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1a42a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x1a42f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a434  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a439  brfalse  loc_1A547
0x1a43e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a443  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0x1a448  stloc.0
0x1a449  ldloc.0
0x1a44a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a44f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a454  brfalse  loc_1A547
0x1a459  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a45e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppDataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a463  ldloc.0
0x1a464  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a469  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache::LookupEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a46e  stloc.1
0x1a46f  ldarg.0
0x1a470  ldarg.1
0x1a471  ldstr    aAppModuleUniqu// "APP_MODULE_UNIQUE_NAME"
0x1a476  ldloc.1
0x1a477  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x1a47c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a481  ldarg.0
0x1a482  ldarg.1
0x1a483  ldstr    aAppModuleAppid// "APP_MODULE_APPID"
0x1a488  ldloc.1
0x1a489  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1a48e  stloc.2
0x1a48f  ldloca.s 2
0x1a491  constrained. [mscorlib]System.Guid
0x1a497  callvirt instance string [mscorlib]System.Object::ToString()
0x1a49c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a4a1  ldarg.0
0x1a4a2  ldarg.1
0x1a4a3  ldstr    aAppModuleDispl// "APP_MODULE_DISPLAYNAME"
0x1a4a8  ldloc.1
0x1a4a9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleName()
0x1a4ae  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a4b3  ldarg.0
0x1a4b4  ldarg.1
0x1a4b5  ldstr    aAppModuleUrl// "APP_MODULE_URL"
0x1a4ba  ldloc.1
0x1a4bb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a4c0  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a4c5  ldloc.1
0x1a4c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x1a4cb  brfalse.s loc_1A506
0x1a4cd  ldarg.0
0x1a4ce  ldarg.1
0x1a4cf  ldstr    aAppModuleIconI// "APP_MODULE_ICON_ID"
0x1a4d4  ldloc.1
0x1a4d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x1a4da  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Id
0x1a4df  constrained. [mscorlib]System.Guid
0x1a4e5  callvirt instance string [mscorlib]System.Object::ToString()
0x1a4ea  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a4ef  ldarg.0
0x1a4f0  ldarg.1
0x1a4f1  ldstr    aAppModuleIconN// "APP_MODULE_ICON_NAME"
0x1a4f6  ldloc.1
0x1a4f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x1a4fc  ldfld    string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Name
0x1a501  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a506  ldloc.1
0x1a507  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x1a50c  brfalse.s loc_1A547
0x1a50e  ldarg.0
0x1a50f  ldarg.1
0x1a510  ldstr    aAppModuleWelco// "APP_MODULE_WELCOME_ID"
0x1a515  ldloc.1
0x1a516  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x1a51b  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Id
0x1a520  constrained. [mscorlib]System.Guid
0x1a526  callvirt instance string [mscorlib]System.Object::ToString()
0x1a52b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a530  ldarg.0
0x1a531  ldarg.1
0x1a532  ldstr    aAppModuleWelco_0// "APP_MODULE_WELCOME_NAME"
0x1a537  ldloc.1
0x1a538  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x1a53d  ldfld    string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Name
0x1a542  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a547  ret
```
