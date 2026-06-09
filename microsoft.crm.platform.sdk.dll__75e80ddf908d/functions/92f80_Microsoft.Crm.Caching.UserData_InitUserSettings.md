# Microsoft.Crm.Caching.UserData::InitUserSettings

- ea: `0x92f80`
- end: `0x936ac`
- name: `Microsoft.Crm.Caching.UserData::InitUserSettings`
- size: `1836`
- prototype: ``
- caller_count: `1`
- callee_count: `55`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x929a0`

## callees

- `0x81f50`
- `0x81f60`
- `0x85df0`
- `0x91980`
- `0x91aa0`
- `0x91ab0`
- `0x91ac0`
- `0x91ad0`
- `0x91af0`
- `0x91b10`
- `0x91b30`
- `0x91b50`
- `0x91b70`
- `0x91b90`
- `0x91bb0`
- `0x91bd0`
- `0x91bf0`
- `0x91c10`
- `0x91c30`
- `0x91c50`
- `0x91c70`
- `0x91c90`
- `0x91cb0`
- `0x92110`
- `0x92130`
- `0x92150`
- `0x92170`
- `0x92190`
- `0x921b0`
- `0x921d0`
- `0x921f0`
- `0x92210`
- `0x92230`
- `0x92250`
- `0x92270`
- `0x922e0`
- `0x92300`
- `0x92320`
- `0x92330`
- `0x92340`
- `0x92360`
- `0x92510`
- `0x92530`
- `0x92550`
- `0x925b0`
- `0x925d0`
- `0x925f0`
- `0x92610`
- `0x92630`
- `0x92650`

## string_xrefs

- `0x93139`: `incomingemailfilteringmethod`
- `0x93147`: `incomingemailfilteringmethod`
- `0x933d2`: `usecrmformfortask`
- `0x933e0`: `usecrmformfortask`
- `0x933f5`: `synccontactcompany`
- `0x93403`: `synccontactcompany`
- `0x93553`: `autocreatecontactonpromote`
- `0x93560`: `autocreatecontactonpromote`

## pseudocode

```c

```

## disassembly

```asm
0x92f80  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x92f85  ldarg.0
0x92f86  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.UserData::get_OrganizationId()
0x92f8b  ldarg.2
0x92f8c  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x92f91  stloc.0
0x92f92  ldarg.1
0x92f93  ldstr    aUilanguageid// "uilanguageid"
0x92f98  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92f9d  brtrue.s loc_92FCA
0x92f9f  ldarg.1
0x92fa0  ldstr    aUilanguageid// "uilanguageid"
0x92fa5  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92faa  unbox.any [mscorlib]System.Int32
0x92faf  ldc.i4.0
0x92fb0  ble.s    loc_92FCA
0x92fb2  ldarg.0
0x92fb3  ldarg.1
0x92fb4  ldstr    aUilanguageid// "uilanguageid"
0x92fb9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92fbe  unbox.any [mscorlib]System.Int32
0x92fc3  call     instance void Microsoft.Crm.Caching.UserData::set_LanguageId(int32 value)
0x92fc8  br.s     loc_92FD6
0x92fca  ldarg.0
0x92fcb  ldloc.0
0x92fcc  callvirt instance int32 Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x92fd1  call     instance void Microsoft.Crm.Caching.UserData::set_LanguageId(int32 value)
0x92fd6  ldarg.1
0x92fd7  ldstr    aUilanguageid// "uilanguageid"
0x92fdc  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92fe1  brtrue.s loc_9300E
0x92fe3  ldarg.1
0x92fe4  ldstr    aUilanguageid// "uilanguageid"
0x92fe9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92fee  unbox.any [mscorlib]System.Int32
0x92ff3  ldc.i4.m1
0x92ff4  ble.s    loc_9300E
0x92ff6  ldarg.0
0x92ff7  ldarg.1
0x92ff8  ldstr    aUilanguageid// "uilanguageid"
0x92ffd  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93002  unbox.any [mscorlib]System.Int32
0x93007  call     instance void Microsoft.Crm.Caching.UserData::set_AppLanguageId(int32 value)
0x9300c  br.s     loc_93015
0x9300e  ldarg.0
0x9300f  ldc.i4.0
0x93010  call     instance void Microsoft.Crm.Caching.UserData::set_AppLanguageId(int32 value)
0x93015  ldarg.1
0x93016  ldstr    aHelplanguageid// "helplanguageid"
0x9301b  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93020  brtrue.s loc_9304C
0x93022  ldarg.1
0x93023  ldstr    aHelplanguageid// "helplanguageid"
0x93028  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9302d  unbox.any [mscorlib]System.Int32
0x93032  brfalse.s loc_9304C
0x93034  ldarg.0
0x93035  ldarg.1
0x93036  ldstr    aHelplanguageid// "helplanguageid"
0x9303b  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93040  unbox.any [mscorlib]System.Int32
0x93045  call     instance void Microsoft.Crm.Caching.UserData::set_HelpLanguageId(int32 value)
0x9304a  br.s     loc_93058
0x9304c  ldarg.0
0x9304d  ldarg.0
0x9304e  call     instance int32 Microsoft.Crm.Caching.UserData::get_AppLanguageId()
0x93053  call     instance void Microsoft.Crm.Caching.UserData::set_HelpLanguageId(int32 value)
0x93058  ldarg.1
0x93059  ldstr    aLocaleid// "localeid"
0x9305e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93063  brtrue.s loc_9307D
0x93065  ldarg.0
0x93066  ldarg.1
0x93067  ldstr    aLocaleid// "localeid"
0x9306c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93071  unbox.any [mscorlib]System.Int32
0x93076  call     instance void Microsoft.Crm.Caching.UserData::set_LocaleId(int32 value)
0x9307b  br.s     loc_93089
0x9307d  ldarg.0
0x9307e  ldarg.0
0x9307f  call     instance int32 Microsoft.Crm.Caching.UserData::get_LanguageId()
0x93084  call     instance void Microsoft.Crm.Caching.UserData::set_LocaleId(int32 value)
0x93089  ldarg.1
0x9308a  ldstr    aAmdesignator// "amdesignator"
0x9308f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93094  brtrue.s loc_930AC
0x93096  ldarg.0
0x93097  ldarg.1
0x93098  ldstr    aAmdesignator// "amdesignator"
0x9309d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x930a2  castclass [mscorlib]System.String
0x930a7  call     instance void Microsoft.Crm.Caching.UserData::set_AMDesignator(string value)
0x930ac  ldarg.1
0x930ad  ldstr    aPmdesignator// "pmdesignator"
0x930b2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x930b7  brtrue.s loc_930CF
0x930b9  ldarg.0
0x930ba  ldarg.1
0x930bb  ldstr    aPmdesignator// "pmdesignator"
0x930c0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x930c5  castclass [mscorlib]System.String
0x930ca  call     instance void Microsoft.Crm.Caching.UserData::set_PMDesignator(string value)
0x930cf  ldarg.1
0x930d0  ldstr    aSelectedglobal// "selectedglobalfilterid"
0x930d5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x930da  brtrue.s loc_930F2
0x930dc  ldarg.0
0x930dd  ldarg.1
0x930de  ldstr    aSelectedglobal// "selectedglobalfilterid"
0x930e3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x930e8  unbox.any [mscorlib]System.Guid
0x930ed  call     instance void Microsoft.Crm.Caching.UserData::set_SelectedGlobalFilterId(valuetype [mscorlib]System.Guid value)
0x930f2  ldarg.1
0x930f3  ldstr    aIsdefaultcount// "isdefaultcountrycodecheckenabled"
0x930f8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x930fd  brtrue.s loc_93115
0x930ff  ldarg.0
0x93100  ldarg.1
0x93101  ldstr    aIsdefaultcount// "isdefaultcountrycodecheckenabled"
0x93106  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9310b  unbox.any [mscorlib]System.Boolean
0x93110  stfld    bool Microsoft.Crm.Caching.UserData::_isDefaultCountryCodeCheckEnabled
0x93115  ldarg.1
0x93116  ldstr    aDefaultcountry// "defaultcountrycode"
0x9311b  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93120  brtrue.s loc_93138
0x93122  ldarg.0
0x93123  ldarg.1
0x93124  ldstr    aDefaultcountry// "defaultcountrycode"
0x93129  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9312e  castclass [mscorlib]System.String
0x93133  stfld    string Microsoft.Crm.Caching.UserData::_defaultCountryCode
0x93138  ldarg.1
0x93139  ldstr    aIncomingemailf// "incomingemailfilteringmethod"
0x9313e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93143  brtrue.s loc_9315B
0x93145  ldarg.0
0x93146  ldarg.1
0x93147  ldstr    aIncomingemailf// "incomingemailfilteringmethod"
0x9314c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93151  unbox.any [mscorlib]System.Int32
0x93156  call     instance void Microsoft.Crm.Caching.UserData::set_IncomingEmailFilteringMethod(int32 value)
0x9315b  ldarg.1
0x9315c  ldstr    aTimezonecode// "timezonecode"
0x93161  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93166  brtrue.s loc_9317E
0x93168  ldarg.0
0x93169  ldarg.1
0x9316a  ldstr    aTimezonecode// "timezonecode"
0x9316f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93174  unbox.any [mscorlib]System.Int32
0x93179  call     instance void Microsoft.Crm.Caching.UserData::set_TimeZoneCode(int32 value)
0x9317e  ldarg.1
0x9317f  ldstr    aTimezonebias// "timezonebias"
0x93184  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93189  brtrue.s loc_931A1
0x9318b  ldarg.0
0x9318c  ldarg.1
0x9318d  ldstr    aTimezonebias// "timezonebias"
0x93192  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93197  unbox.any [mscorlib]System.Int32
0x9319c  call     instance void Microsoft.Crm.Caching.UserData::set_TimeZoneBias(int32 value)
0x931a1  ldarg.1
0x931a2  ldstr    aWorkdaystoptim// "workdaystoptime"
0x931a7  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x931ac  brtrue.s loc_931C4
0x931ae  ldarg.0
0x931af  ldarg.1
0x931b0  ldstr    aWorkdaystoptim// "workdaystoptime"
0x931b5  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x931ba  castclass [mscorlib]System.String
0x931bf  call     instance void Microsoft.Crm.Caching.UserData::set_WorkDayStopTime(string value)
0x931c4  ldarg.1
0x931c5  ldstr    aWorkdaystartti// "workdaystarttime"
0x931ca  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x931cf  brtrue.s loc_931E7
0x931d1  ldarg.0
0x931d2  ldarg.1
0x931d3  ldstr    aWorkdaystartti// "workdaystarttime"
0x931d8  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x931dd  castclass [mscorlib]System.String
0x931e2  call     instance void Microsoft.Crm.Caching.UserData::set_WorkDayStartTime(string value)
0x931e7  ldarg.1
0x931e8  ldstr    aHomepagearea// "homepagearea"
0x931ed  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x931f2  brtrue.s loc_9320A
0x931f4  ldarg.0
0x931f5  ldarg.1
0x931f6  ldstr    aHomepagearea// "homepagearea"
0x931fb  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93200  castclass [mscorlib]System.String
0x93205  call     instance void Microsoft.Crm.Caching.UserData::set_HomePageArea(string value)
0x9320a  ldarg.1
0x9320b  ldstr    aHomepagesubare// "homepagesubarea"
0x93210  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93215  brtrue.s loc_9322D
0x93217  ldarg.0
0x93218  ldarg.1
0x93219  ldstr    aHomepagesubare// "homepagesubarea"
0x9321e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93223  castclass [mscorlib]System.String
0x93228  call     instance void Microsoft.Crm.Caching.UserData::set_HomePageSubArea(string value)
0x9322d  ldarg.1
0x9322e  ldstr    aAdvancedfindst// "advancedfindstartupmode"
0x93233  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93238  brtrue.s loc_93250
0x9323a  ldarg.0
0x9323b  ldarg.1
0x9323c  ldstr    aAdvancedfindst// "advancedfindstartupmode"
0x93241  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93246  unbox.any [mscorlib]System.Int32
0x9324b  call     instance void Microsoft.Crm.Caching.UserData::set_AdvancedFindStartupMode(int32 value)
0x93250  ldarg.1
0x93251  ldstr    aDefaultsearche// "defaultsearchexperience"
0x93256  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x9325b  brtrue.s loc_93273
0x9325d  ldarg.0
0x9325e  ldarg.1
0x9325f  ldstr    aDefaultsearche// "defaultsearchexperience"
0x93264  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93269  unbox.any [mscorlib]System.Int32
0x9326e  call     instance void Microsoft.Crm.Caching.UserData::set_DefaultSearchExperience(int32 value)
0x93273  ldarg.1
0x93274  ldstr    aUseimagestrips// "useimagestrips"
0x93279  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x9327e  brtrue.s loc_93296
0x93280  ldarg.0
0x93281  ldarg.1
0x93282  ldstr    aUseimagestrips// "useimagestrips"
0x93287  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9328c  unbox.any [mscorlib]System.Boolean
0x93291  call     instance void Microsoft.Crm.Caching.UserData::set_UseImageStrips(bool value)
0x93296  ldarg.1
0x93297  ldstr    aOutlooksyncint// "outlooksyncinterval"
0x9329c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x932a1  brtrue.s loc_932B9
0x932a3  ldarg.0
0x932a4  ldarg.1
0x932a5  ldstr    aOutlooksyncint// "outlooksyncinterval"
0x932aa  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x932af  unbox.any [mscorlib]System.Int32
0x932b4  call     instance void Microsoft.Crm.Caching.UserData::set_OutlookSyncInterval(int32 value)
0x932b9  ldarg.1
0x932ba  ldstr    aAddressbooksyn// "addressbooksyncinterval"
0x932bf  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x932c4  brtrue.s loc_932DC
0x932c6  ldarg.0
0x932c7  ldarg.1
0x932c8  ldstr    aAddressbooksyn// "addressbooksyncinterval"
0x932cd  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x932d2  unbox.any [mscorlib]System.Int32
0x932d7  call     instance void Microsoft.Crm.Caching.UserData::set_AddressBookSyncInterval(int32 value)
0x932dc  ldarg.1
0x932dd  ldstr    aOfflinesyncint// "offlinesyncinterval"
0x932e2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x932e7  brtrue.s loc_932FF
0x932e9  ldarg.0
0x932ea  ldarg.1
0x932eb  ldstr    aOfflinesyncint// "offlinesyncinterval"
0x932f0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x932f5  unbox.any [mscorlib]System.Int32
0x932fa  call     instance void Microsoft.Crm.Caching.UserData::set_OfflineSyncInterval(int32 value)
0x932ff  ldarg.1
0x93300  ldstr    aPaginglimit// "paginglimit"
0x93305  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x9330a  brtrue.s loc_93322
0x9330c  ldarg.0
0x9330d  ldarg.1
0x9330e  ldstr    aPaginglimit// "paginglimit"
0x93313  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x93318  unbox.any [mscorlib]System.Int32
0x9331d  call     instance void Microsoft.Crm.Caching.UserData::set_RecordsPerPage(int32 value)
0x93322  ldarg.1
0x93323  ldstr    aDefaultcalenda// "defaultcalendarview"
0x93328  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x9332d  brtrue.s loc_93345
0x9332f  ldarg.0
0x93330  ldarg.1
0x93331  ldstr    aDefaultcalenda// "defaultcalendarview"
0x93336  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9333b  unbox.any [mscorlib]System.Int32
0x93340  call     instance void Microsoft.Crm.Caching.UserData::set_DefaultCalendarView(valuetype Microsoft.Crm.Caching.CalendarViews value)
0x93345  ldarg.1
0x93346  ldstr    aReportscripter// "reportscripterrors"
0x9334b  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93350  brtrue.s loc_93368
0x93352  ldarg.0
0x93353  ldarg.1
0x93354  ldstr    aReportscripter// "reportscripterrors"
0x93359  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9335e  unbox.any [mscorlib]System.Int32
0x93363  call     instance void Microsoft.Crm.Caching.UserData::set_ScriptErrorReportingPreference(valuetype Microsoft.Crm.Caching.ReportingPreference value)
0x93368  ldarg.1
0x93369  ldstr    aUsecrmformforc// "usecrmformforcontact"
0x9336e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x93373  brtrue.s loc_9338B
0x93375  ldarg.0
0x93376  ldarg.1
0x93377  ldstr    aUsecrmformforc// "usecrmformforcontact"
0x9337c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
  ... truncated ...
```
