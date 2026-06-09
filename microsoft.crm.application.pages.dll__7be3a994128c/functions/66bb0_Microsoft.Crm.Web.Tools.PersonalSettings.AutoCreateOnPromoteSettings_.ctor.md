# Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::.ctor

- ea: `0x66bb0`
- end: `0x66d8d`
- name: `Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::.ctor`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x64410`
- `0x644b0`
- `0x64530`
- `0x64540`
- `0x66bb0`

## string_xrefs

- `0x66bd2`: `AutoCreateContactOnPromote`
- `0x66c6c`: `Web.Tools.personalsettings.dialogs.personalsettings.AutoCreateOnPromoteTitle`
- `0x66c87`: `Web.Tools.personalsettings.dialogs.personalsettings.AutoCreateOnPromoteAutoCreate`
- `0x66c97`: `checkAutoCreateEnabled`
- `0x66cb8`: `$get('selectAutoCreateEntity').disabled=!this.checked;`
- `0x66cd3`: `Web.Tools.personalsettings.dialogs.personalsettings.AutoCreateOnPromoteRestOfSentence`
- `0x66cee`: `selectAutoCreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x66bb0  ldarg.0
0x66bb1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0x66bb6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x66bbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66bc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x66bc5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66bca  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x66bcf  stloc.0
0x66bd0  ldarg.0
0x66bd1  ldloc.0
0x66bd2  ldstr    aAutocreatecont// "AutoCreateContactOnPromote"
0x66bd7  ldc.i4.1
0x66bd8  box      [mscorlib]System.Boolean
0x66bdd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x66be2  unbox.any [mscorlib]System.Boolean
0x66be7  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::orgCanCreateContact
0x66bec  ldarg.0
0x66bed  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::orgCanCreateContact
0x66bf2  brtrue.s loc_66BF5
0x66bf4  ret
0x66bf5  ldarg.0
0x66bf6  ldstr    aContact// "contact"
0x66bfb  ldc.i4.s 0x20
0x66bfd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66c02  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66c07  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::canCreateContact
0x66c0c  ldsfld   string [mscorlib]System.String::Empty
0x66c11  stloc.1
0x66c12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66c17  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66c1c  ldstr    aLead// "lead"
0x66c21  ldc.i4.1
0x66c22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x66c27  brfalse.s loc_66C5B
0x66c29  ldarg.0
0x66c2a  ldstr    aLead// "lead"
0x66c2f  ldc.i4.s 0x20
0x66c31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66c36  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66c3b  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::canCreateLead
0x66c40  ldstr    aLead// "lead"
0x66c45  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66c4a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66c4f  ldc.i4.2
0x66c50  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x66c55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x66c5a  stloc.1
0x66c5b  ldarg.0
0x66c5c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::.ctor()
0x66c61  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::titleLabel
0x66c66  ldarg.0
0x66c67  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::titleLabel
0x66c6c  ldstr    aWebToolsPerson_72// "Web.Tools.personalsettings.dialogs.pers"...
0x66c71  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x66c76  ldarg.0
0x66c77  newobj   instance void Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::.ctor()
0x66c7c  stfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateEnabled
0x66c81  ldarg.0
0x66c82  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateEnabled
0x66c87  ldstr    aWebToolsPerson_73// "Web.Tools.personalsettings.dialogs.pers"...
0x66c8c  callvirt instance void Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::set_CheckBoxLabel(string value)
0x66c91  ldarg.0
0x66c92  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateEnabled
0x66c97  ldstr    aCheckautocreat// "checkAutoCreateEnabled"
0x66c9c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x66ca1  ldarg.0
0x66ca2  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateEnabled
0x66ca7  ldc.i4.1
0x66ca8  callvirt instance void Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::set_IsCompositeControl(bool value)
0x66cad  ldarg.0
0x66cae  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateEnabled
0x66cb3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::get_InnerCheckBox()
0x66cb8  ldstr    aGetSelectautoc// "$get('selectAutoCreateEntity').disabled"...
0x66cbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_OnClick(string)
0x66cc2  ldarg.0
0x66cc3  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::.ctor()
0x66cc8  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateMessage
0x66ccd  ldarg.0
0x66cce  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::autoCreateMessage
0x66cd3  ldstr    aWebToolsPerson_74// "Web.Tools.personalsettings.dialogs.pers"...
0x66cd8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x66cdd  ldarg.0
0x66cde  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x66ce3  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::selectAutoCreateEntity
0x66ce8  ldarg.0
0x66ce9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::selectAutoCreateEntity
0x66cee  ldstr    aSelectautocrea// "selectAutoCreateEntity"
0x66cf3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x66cf8  ldarg.0
0x66cf9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::selectAutoCreateEntity
0x66cfe  ldc.i4.0
0x66cff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x66d04  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x66d09  stloc.2
0x66d0a  ldloc.2
0x66d0b  ldstr    aContact// "contact"
0x66d10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66d15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66d1a  ldc.i4.2
0x66d1b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x66d20  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x66d25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x66d2a  ldarg.0
0x66d2b  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::canCreateLead
0x66d30  brfalse.s loc_66D39
0x66d32  ldloc.2
0x66d33  ldloc.1
0x66d34  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x66d39  ldloc.2
0x66d3a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x66d3f  stloc.3
0x66d40  ldarg.0
0x66d41  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::canCreateContact
0x66d46  brfalse.s loc_66D66
0x66d48  ldarg.0
0x66d49  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::selectAutoCreateEntity
0x66d4e  ldloc.3
0x66d4f  ldc.i4.0
0x66d50  ldelem.ref
0x66d51  ldc.i4.0
0x66d52  stloc.s  4
0x66d54  ldloca.s 4
0x66d56  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AutoCreateEntity
0x66d5c  callvirt instance string [mscorlib]System.Object::ToString()
0x66d61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x66d66  ldarg.0
0x66d67  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::canCreateLead
0x66d6c  brfalse.s loc_66D8C
0x66d6e  ldarg.0
0x66d6f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.PersonalSettings.AutoCreateOnPromoteSettings::selectAutoCreateEntity
0x66d74  ldloc.3
0x66d75  ldc.i4.1
0x66d76  ldelem.ref
0x66d77  ldc.i4.1
0x66d78  stloc.s  4
0x66d7a  ldloca.s 4
0x66d7c  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AutoCreateEntity
0x66d82  callvirt instance string [mscorlib]System.Object::ToString()
0x66d87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x66d8c  ret
```
