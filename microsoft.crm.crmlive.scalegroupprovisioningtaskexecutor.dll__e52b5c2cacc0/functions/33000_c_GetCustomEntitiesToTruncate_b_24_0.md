# <>c::<GetCustomEntitiesToTruncate>b__24_0

- ea: `0x33000`
- end: `0x332c5`
- name: `<>c::<GetCustomEntitiesToTruncate>b__24_0`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x33000`

## string_xrefs

- `0x3301c`: `msdyn_postconfig`
- `0x33032`: `msdyn_postruleconfig`
- `0x33074`: `adx_contentaccesslevel`
- `0x330f8`: `adx_pagetemplate`
- `0x33200`: `adx_weblink`
- `0x33216`: `adx_weblinkset`
- `0x33242`: `adx_webpageaccesscontrolrule`
- `0x3327b`: `adx_websiteaccess`
- `0x332b4`: `adx_webtemplate`

## pseudocode

```c

```

## disassembly

```asm
0x33000  ldarg.1
0x33001  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33006  ldstr    aMsdynWallsaved// "msdyn_wallsavedqueryusersettings"
0x3300b  ldc.i4.5
0x3300c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33011  brtrue   loc_332C3
0x33016  ldarg.1
0x33017  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3301c  ldstr    aMsdynPostconfi// "msdyn_postconfig"
0x33021  ldc.i4.5
0x33022  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33027  brtrue   loc_332C3
0x3302c  ldarg.1
0x3302d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33032  ldstr    aMsdynPostrulec// "msdyn_postruleconfig"
0x33037  ldc.i4.5
0x33038  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3303d  brtrue   loc_332C3
0x33042  ldarg.1
0x33043  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33048  ldstr    aMsdynPostalbum// "msdyn_postalbum"
0x3304d  ldc.i4.5
0x3304e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33053  brtrue   loc_332C3
0x33058  ldarg.1
0x33059  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3305e  ldstr    aMsdynWallsaved_0// "msdyn_wallsavedquery"
0x33063  ldc.i4.5
0x33064  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33069  brtrue   loc_332C3
0x3306e  ldarg.1
0x3306f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33074  ldstr    aAdxContentacce// "adx_contentaccesslevel"
0x33079  ldc.i4.5
0x3307a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3307f  brtrue   loc_332C3
0x33084  ldarg.1
0x33085  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3308a  ldstr    aAdxContentsnip// "adx_contentsnippet"
0x3308f  ldc.i4.5
0x33090  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33095  brtrue   loc_332C3
0x3309a  ldarg.1
0x3309b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x330a0  ldstr    aAdxEntityform// "adx_entityform"
0x330a5  ldc.i4.5
0x330a6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x330ab  brtrue   loc_332C3
0x330b0  ldarg.1
0x330b1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x330b6  ldstr    aAdxEntityformm// "adx_entityformmetadata"
0x330bb  ldc.i4.5
0x330bc  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x330c1  brtrue   loc_332C3
0x330c6  ldarg.1
0x330c7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x330cc  ldstr    aAdxEntitylist// "adx_entitylist"
0x330d1  ldc.i4.5
0x330d2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x330d7  brtrue   loc_332C3
0x330dc  ldarg.1
0x330dd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x330e2  ldstr    aAdxEntitypermi// "adx_entitypermission"
0x330e7  ldc.i4.5
0x330e8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x330ed  brtrue   loc_332C3
0x330f2  ldarg.1
0x330f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x330f8  ldstr    aAdxPagetemplat// "adx_pagetemplate"
0x330fd  ldc.i4.5
0x330fe  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33103  brtrue   loc_332C3
0x33108  ldarg.1
0x33109  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3310e  ldstr    aAdxPortallangu// "adx_portallanguage"
0x33113  ldc.i4.5
0x33114  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33119  brtrue   loc_332C3
0x3311e  ldarg.1
0x3311f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33124  ldstr    aAdxPublishings// "adx_publishingstate"
0x33129  ldc.i4.5
0x3312a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3312f  brtrue   loc_332C3
0x33134  ldarg.1
0x33135  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3313a  ldstr    aAdxPublishings_0// "adx_publishingstatetransitionrule"
0x3313f  ldc.i4.5
0x33140  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33145  brtrue   loc_332C3
0x3314a  ldarg.1
0x3314b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33150  ldstr    aAdxRedirect// "adx_redirect"
0x33155  ldc.i4.5
0x33156  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3315b  brtrue   loc_332C3
0x33160  ldarg.1
0x33161  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33166  ldstr    aAdxSetting// "adx_setting"
0x3316b  ldc.i4.5
0x3316c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33171  brtrue   loc_332C3
0x33176  ldarg.1
0x33177  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3317c  ldstr    aAdxSitemarker// "adx_sitemarker"
0x33181  ldc.i4.5
0x33182  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33187  brtrue   loc_332C3
0x3318c  ldarg.1
0x3318d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33192  ldstr    aAdxSitesetting// "adx_sitesetting"
0x33197  ldc.i4.5
0x33198  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3319d  brtrue   loc_332C3
0x331a2  ldarg.1
0x331a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x331a8  ldstr    aAdxWebfile// "adx_webfile"
0x331ad  ldc.i4.5
0x331ae  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x331b3  brtrue   loc_332C3
0x331b8  ldarg.1
0x331b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x331be  ldstr    aAdxWebform// "adx_webform"
0x331c3  ldc.i4.5
0x331c4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x331c9  brtrue   loc_332C3
0x331ce  ldarg.1
0x331cf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x331d4  ldstr    aAdxWebformmeta// "adx_webformmetadata"
0x331d9  ldc.i4.5
0x331da  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x331df  brtrue   loc_332C3
0x331e4  ldarg.1
0x331e5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x331ea  ldstr    aAdxWebformstep// "adx_webformstep"
0x331ef  ldc.i4.5
0x331f0  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x331f5  brtrue   loc_332C3
0x331fa  ldarg.1
0x331fb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33200  ldstr    aAdxWeblink// "adx_weblink"
0x33205  ldc.i4.5
0x33206  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3320b  brtrue   loc_332C3
0x33210  ldarg.1
0x33211  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33216  ldstr    aAdxWeblinkset// "adx_weblinkset"
0x3321b  ldc.i4.5
0x3321c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33221  brtrue   loc_332C3
0x33226  ldarg.1
0x33227  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3322c  ldstr    aAdxWebpage// "adx_webpage"
0x33231  ldc.i4.5
0x33232  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33237  brtrue   loc_332C3
0x3323c  ldarg.1
0x3323d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33242  ldstr    aAdxWebpageacce// "adx_webpageaccesscontrolrule"
0x33247  ldc.i4.5
0x33248  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3324d  brtrue.s loc_332C3
0x3324f  ldarg.1
0x33250  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33255  ldstr    aAdxWebrole// "adx_webrole"
0x3325a  ldc.i4.5
0x3325b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33260  brtrue.s loc_332C3
0x33262  ldarg.1
0x33263  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x33268  ldstr    aAdxWebsite// "adx_website"
0x3326d  ldc.i4.5
0x3326e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33273  brtrue.s loc_332C3
0x33275  ldarg.1
0x33276  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3327b  ldstr    aAdxWebsiteacce// "adx_websiteaccess"
0x33280  ldc.i4.5
0x33281  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33286  brtrue.s loc_332C3
0x33288  ldarg.1
0x33289  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3328e  ldstr    aAdxWebsitebind// "adx_websitebinding"
0x33293  ldc.i4.5
0x33294  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33299  brtrue.s loc_332C3
0x3329b  ldarg.1
0x3329c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x332a1  ldstr    aAdxWebsitelang// "adx_websitelanguage"
0x332a6  ldc.i4.5
0x332a7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x332ac  brtrue.s loc_332C3
0x332ae  ldarg.1
0x332af  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x332b4  ldstr    aAdxWebtemplate// "adx_webtemplate"
0x332b9  ldc.i4.5
0x332ba  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x332bf  ldc.i4.0
0x332c0  ceq
0x332c2  ret
0x332c3  ldc.i4.0
0x332c4  ret
```
