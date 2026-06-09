# Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::AddColumnsBasedOnAvailability

- ea: `0x916e0`
- end: `0x918ab`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::AddColumnsBasedOnAvailability`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x90ec0`

## callees

- `0x916e0`

## string_xrefs

- `0x916fd`: `plugintracelogsetting`
- `0x9170a`: `plugintracelogsetting`
- `0x91715`: `autoapplydefaultoncasecreate`
- `0x91722`: `autoapplydefaultoncasecreate`
- `0x9172d`: `autoapplydefaultoncaseupdate`
- `0x9173a`: `autoapplydefaultoncaseupdate`

## pseudocode

```c

```

## disassembly

```asm
0x916e0  ldarg.2
0x916e1  brtrue.s loc_916E4
0x916e3  ret
0x916e4  ldarg.2
0x916e5  ldstr    aIsfolderbasedt// "isfolderbasedtrackingenabled"
0x916ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x916ef  brfalse.s loc_916FC
0x916f1  ldarg.1
0x916f2  ldstr    aIsfolderbasedt// "isfolderbasedtrackingenabled"
0x916f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x916fc  ldarg.2
0x916fd  ldstr    aPlugintracelog// "plugintracelogsetting"
0x91702  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91707  brfalse.s loc_91714
0x91709  ldarg.1
0x9170a  ldstr    aPlugintracelog// "plugintracelogsetting"
0x9170f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91714  ldarg.2
0x91715  ldstr    aAutoapplydefau// "autoapplydefaultoncasecreate"
0x9171a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9171f  brfalse.s loc_9172C
0x91721  ldarg.1
0x91722  ldstr    aAutoapplydefau// "autoapplydefaultoncasecreate"
0x91727  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9172c  ldarg.2
0x9172d  ldstr    aAutoapplydefau_0// "autoapplydefaultoncaseupdate"
0x91732  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91737  brfalse.s loc_91744
0x91739  ldarg.1
0x9173a  ldstr    aAutoapplydefau_0// "autoapplydefaultoncaseupdate"
0x9173f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91744  ldarg.2
0x91745  ldstr    aUselegacyrende// "uselegacyrendering"
0x9174a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9174f  brfalse.s loc_9175C
0x91751  ldarg.1
0x91752  ldstr    aUselegacyrende// "uselegacyrendering"
0x91757  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9175c  ldarg.2
0x9175d  ldstr    aServestaticres// "servestaticresourcesfromazurecdn"
0x91762  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91767  brfalse.s loc_91774
0x91769  ldarg.1
0x9176a  ldstr    aServestaticres// "servestaticresourcesfromazurecdn"
0x9176f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91774  ldarg.2
0x91775  ldstr    aBounddashboard// "bounddashboarddefaultcardexpanded"
0x9177a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9177f  brfalse.s loc_9178C
0x91781  ldarg.1
0x91782  ldstr    aBounddashboard// "bounddashboarddefaultcardexpanded"
0x91787  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9178c  ldarg.2
0x9178d  ldstr    aExternalpartye// "externalpartyentitysettings"
0x91792  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91797  brfalse.s loc_917A4
0x91799  ldarg.1
0x9179a  ldstr    aExternalpartye// "externalpartyentitysettings"
0x9179f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x917a4  ldarg.2
0x917a5  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x917aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x917af  brfalse.s loc_917BC
0x917b1  ldarg.1
0x917b2  ldstr    aExternalpartyc// "externalpartycorrelationkeys"
0x917b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x917bc  ldarg.2
0x917bd  ldstr    aPowerbifeature_0// "PowerBiFeatureEnabled"
0x917c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x917c7  brfalse.s loc_917D4
0x917c9  ldarg.1
0x917ca  ldstr    aPowerbifeature_0// "PowerBiFeatureEnabled"
0x917cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x917d4  ldarg.2
0x917d5  ldstr    aEnablelpauthor// "enablelpauthoring"
0x917da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x917df  brfalse.s loc_917EC
0x917e1  ldarg.1
0x917e2  ldstr    aEnablelpauthor// "enablelpauthoring"
0x917e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x917ec  ldarg.0
0x917ed  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomSessionTimeoutEnabled
0x917f2  brfalse.s loc_9184B
0x917f4  ldarg.0
0x917f5  ldarg.2
0x917f6  ldstr    aSessiontimeout// "sessiontimeoutenabled"
0x917fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91800  ldnull
0x91801  cgt.un
0x91803  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomSessionTimeoutEnabled
0x91808  ldarg.0
0x91809  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomSessionTimeoutEnabled
0x9180e  brfalse.s loc_9184B
0x91810  ldarg.1
0x91811  ldstr    aSessiontimeout// "sessiontimeoutenabled"
0x91816  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9181b  ldarg.2
0x9181c  ldstr    aSessiontimeout_0// "sessiontimeoutinmins"
0x91821  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91826  brfalse.s loc_91833
0x91828  ldarg.1
0x91829  ldstr    aSessiontimeout_0// "sessiontimeoutinmins"
0x9182e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91833  ldarg.2
0x91834  ldstr    aSessiontimeout_1// "sessiontimeoutreminderinmins"
0x91839  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9183e  brfalse.s loc_9184B
0x91840  ldarg.1
0x91841  ldstr    aSessiontimeout_1// "sessiontimeoutreminderinmins"
0x91846  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9184b  ldarg.0
0x9184c  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomInactivityTimeoutEnabled
0x91851  brfalse.s loc_918AA
0x91853  ldarg.0
0x91854  ldarg.2
0x91855  ldstr    aInactivitytime// "inactivitytimeoutenabled"
0x9185a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9185f  ldnull
0x91860  cgt.un
0x91862  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomInactivityTimeoutEnabled
0x91867  ldarg.0
0x91868  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCustomInactivityTimeoutEnabled
0x9186d  brfalse.s loc_918AA
0x9186f  ldarg.1
0x91870  ldstr    aInactivitytime// "inactivitytimeoutenabled"
0x91875  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9187a  ldarg.2
0x9187b  ldstr    aInactivitytime_0// "inactivitytimeoutinmins"
0x91880  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x91885  brfalse.s loc_91892
0x91887  ldarg.1
0x91888  ldstr    aInactivitytime_0// "inactivitytimeoutinmins"
0x9188d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91892  ldarg.2
0x91893  ldstr    aInactivitytime_1// "inactivitytimeoutreminderinmins"
0x91898  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x9189d  brfalse.s loc_918AA
0x9189f  ldarg.1
0x918a0  ldstr    aInactivitytime_1// "inactivitytimeoutreminderinmins"
0x918a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x918aa  ret
```
