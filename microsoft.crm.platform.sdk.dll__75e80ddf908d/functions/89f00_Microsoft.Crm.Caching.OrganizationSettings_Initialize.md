# Microsoft.Crm.Caching.OrganizationSettings::Initialize

- ea: `0x89f00`
- end: `0x8c55a`
- name: `Microsoft.Crm.Caching.OrganizationSettings::Initialize`
- size: `9818`
- prototype: ``
- caller_count: `0`
- callee_count: `252`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x3700`
- `0x81f50`
- `0x81f60`
- `0x875d0`
- `0x877b0`
- `0x87830`
- `0x87850`
- `0x87870`
- `0x87890`
- `0x878b0`
- `0x878d0`
- `0x878f0`
- `0x87910`
- `0x87930`
- `0x87950`
- `0x87970`
- `0x87990`
- `0x879b0`
- `0x879d0`
- `0x879f0`
- `0x87a10`
- `0x87a30`
- `0x87a50`
- `0x87a70`
- `0x87a90`
- `0x87ab0`
- `0x87af0`
- `0x87b10`
- `0x87b70`
- `0x87b90`
- `0x87bb0`
- `0x87bd0`
- `0x87bf0`
- `0x87c10`
- `0x87c30`
- `0x87c50`
- `0x87c70`
- `0x87cb0`
- `0x87cd0`
- `0x87cf0`
- `0x87d10`
- `0x87d30`
- `0x87d50`
- `0x87d70`
- `0x87d90`
- `0x87db0`
- `0x87dd0`
- `0x87df0`
- `0x87e10`
- `0x87e30`

## string_xrefs

- `0x8c505`: `D:\a\1\s\src\ManagedPlatform\SDK\Caching\CacheData\OrganizationSettings.cs`
- `0x8c539`: `D:\a\1\s\src\ManagedPlatform\SDK\Caching\CacheData\OrganizationSettings.cs`
- `0x8a19f`: `usereadform`
- `0x8a1ad`: `usereadform`
- `0x8a41f`: `useskypeprotocol`
- `0x8a42d`: `useskypeprotocol`
- `0x8a442`: `signupOutlookDownloadFWLink`
- `0x8a450`: `signupoutlookdownloadfwlink`
- `0x8a514`: `createproductswithoutparentinactivestate`
- `0x8a522`: `createproductswithoutparentinactivestate`
- `0x8a78a`: `enablepricingoncreate`
- `0x8a798`: `enablepricingoncreate`
- `0x8a92e`: `acknowledgementtemplateid`
- `0x8a93c`: `acknowledgementtemplateid`
- `0x8aa23`: `allowofflinescheduledsyncs`
- `0x8aa31`: `allowofflinescheduledsyncs`
- `0x8aa8c`: `allowoutlookscheduledsyncs`
- `0x8aa9a`: `allowoutlookscheduledsyncs`
- `0x8aba4`: `tokenexpiry`
- `0x8abb2`: `tokenexpiry`
- `0x8adb1`: `privilegeusergroupid`
- `0x8adbf`: `privilegeusergroupid`
- `0x8af0f`: `incomingEmailExchangeEmailRetrievalBatchSize`
- `0x8af1d`: `incomingEmailExchangeEmailRetrievalBatchSize`
- `0x8b13f`: `isduplicatedetectionenabledforonlinecreateupdate`
- `0x8b14d`: `isduplicatedetectionenabledforonlinecreateupdate`
- `0x8b185`: `isreadauditenabled`
- `0x8b193`: `isreadauditenabled`
- `0x8b1a8`: `isuseraccessauditenabled`
- `0x8b1b6`: `isuseraccessauditenabled`
- `0x8b1cb`: `useraccessauditinginterval`
- `0x8b1d9`: `useraccessauditinginterval`
- `0x8b64a`: `recurrenceexpansionsynchcreatemax`
- `0x8b658`: `recurrenceexpansionsynchcreatemax`
- `0x8b73f`: `restrictstatusupdate`
- `0x8b74d`: `restrictstatusupdate`
- `0x8b762`: `cascadestatusupdate`
- `0x8b770`: `cascadestatusupdate`
- `0x8b7cb`: `autoapplydefaultoncasecreate`
- `0x8b7d9`: `autoapplydefaultoncasecreate`
- `0x8b7ee`: `autoapplydefaultoncaseupdate`
- `0x8b7fc`: `autoapplydefaultoncaseupdate`
- `0x8b8b1`: `isdelegateaccessenabled`
- `0x8b8bf`: `isdelegateaccessenabled`
- `0x8b91a`: `ishierarchicalsecuritymodelenabled`
- `0x8b928`: `ishierarchicalsecuritymodelenabled`
- `0x8b960`: `maxdepthforhierarchicalsecuritymodel`
- `0x8b96e`: `maxdepthforhierarchicalsecuritymodel`
- `0x8b9a6`: `isassignedtaskssyncenabled`
- `0x8b9b4`: `isassignedtaskssyncenabled`
- `0x8babe`: `enforcereadonlyplugins`
- `0x8bacc`: `enforcereadonlyplugins`
- `0x8bc3f`: `isfolderautocreatedonsp`
- `0x8bc4d`: `isfolderautocreatedonsp`
- `0x8bf87`: `yammernetworkpermalink`
- `0x8bf95`: `yammernetworkpermalink`
- `0x8bfcd`: `yammeroauthaccesstokenexpired`
- `0x8bfdb`: `yammeroauthaccesstokenexpired`
- `0x8c162`: `taskbasedflowenabled`
- `0x8c170`: `taskbasedflowenabled`
- `0x8c1ee`: `productrecommendationsenabled`
- `0x8c1fc`: `productrecommendationsenabled`
- `0x8c27a`: `plugintracelogsetting`
- `0x8c288`: `plugintracelogsetting`

## pseudocode

```c

```

## disassembly

```asm
0x89f00  ldarg.1
0x89f01  ldstr    aOrganizationid_1// "organizationid"
0x89f06  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89f0b  brtrue.s loc_89F23
0x89f0d  ldarg.0
0x89f0e  ldarg.1
0x89f0f  ldstr    aOrganizationid_1// "organizationid"
0x89f14  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89f19  unbox.any [mscorlib]System.Guid
0x89f1e  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x89f23  ldarg.1
0x89f24  ldstr    aLanguagecode// "languagecode"
0x89f29  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89f2e  brtrue.s loc_89F46
0x89f30  ldarg.0
0x89f31  ldarg.1
0x89f32  ldstr    aLanguagecode// "languagecode"
0x89f37  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89f3c  unbox.any [mscorlib]System.Int32
0x89f41  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_LanguageCode(int32 value)
0x89f46  ldarg.1
0x89f47  ldstr    aPinpointlangua// "pinpointlanguagecode"
0x89f4c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89f51  brtrue.s loc_89F69
0x89f53  ldarg.0
0x89f54  ldarg.1
0x89f55  ldstr    aPinpointlangua// "pinpointlanguagecode"
0x89f5a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89f5f  unbox.any [mscorlib]System.Int32
0x89f64  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_PinpointLanguageCode(int32 value)
0x89f69  ldarg.1
0x89f6a  ldstr    aLocaleid// "localeid"
0x89f6f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89f74  brtrue.s loc_89F8C
0x89f76  ldarg.0
0x89f77  ldarg.1
0x89f78  ldstr    aLocaleid// "localeid"
0x89f7d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89f82  unbox.any [mscorlib]System.Int32
0x89f87  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_LocaleId(int32 value)
0x89f8c  ldarg.1
0x89f8d  ldstr    aCalendartype// "calendartype"
0x89f92  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89f97  brtrue.s loc_89FAF
0x89f99  ldarg.0
0x89f9a  ldarg.1
0x89f9b  ldstr    aCalendartype// "calendartype"
0x89fa0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89fa5  unbox.any [mscorlib]System.Int32
0x89faa  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_CalendarType(int32 value)
0x89faf  ldarg.1
0x89fb0  ldstr    aDateseparator// "dateseparator"
0x89fb5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89fba  brtrue.s loc_89FD2
0x89fbc  ldarg.0
0x89fbd  ldarg.1
0x89fbe  ldstr    aDateseparator// "dateseparator"
0x89fc3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89fc8  castclass [mscorlib]System.String
0x89fcd  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_DateSeparator(string value)
0x89fd2  ldarg.1
0x89fd3  ldstr    aTimeseparator// "timeseparator"
0x89fd8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x89fdd  brtrue.s loc_89FF5
0x89fdf  ldarg.0
0x89fe0  ldarg.1
0x89fe1  ldstr    aTimeseparator// "timeseparator"
0x89fe6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x89feb  castclass [mscorlib]System.String
0x89ff0  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_TimeSeparator(string value)
0x89ff5  ldarg.1
0x89ff6  ldstr    aLongdateformat// "longdateformatcode"
0x89ffb  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a000  brtrue.s loc_8A018
0x8a002  ldarg.0
0x8a003  ldarg.1
0x8a004  ldstr    aLongdateformat// "longdateformatcode"
0x8a009  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a00e  unbox.any [mscorlib]System.Int32
0x8a013  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_LongDateFormatCode(int32 value)
0x8a018  ldarg.1
0x8a019  ldstr    aAmdesignator// "amdesignator"
0x8a01e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a023  brtrue.s loc_8A03B
0x8a025  ldarg.0
0x8a026  ldarg.1
0x8a027  ldstr    aAmdesignator// "amdesignator"
0x8a02c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a031  castclass [mscorlib]System.String
0x8a036  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_AMDesignator(string value)
0x8a03b  ldarg.1
0x8a03c  ldstr    aPmdesignator// "pmdesignator"
0x8a041  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a046  brtrue.s loc_8A05E
0x8a048  ldarg.0
0x8a049  ldarg.1
0x8a04a  ldstr    aPmdesignator// "pmdesignator"
0x8a04f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a054  castclass [mscorlib]System.String
0x8a059  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_PMDesignator(string value)
0x8a05e  ldarg.1
0x8a05f  ldstr    aSelectedglobal// "selectedglobalfilterid"
0x8a064  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a069  brtrue.s loc_8A081
0x8a06b  ldarg.0
0x8a06c  ldarg.1
0x8a06d  ldstr    aSelectedglobal// "selectedglobalfilterid"
0x8a072  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a077  unbox.any [mscorlib]System.Guid
0x8a07c  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_SelectedGlobalFilterId(valuetype [mscorlib]System.Guid value)
0x8a081  ldarg.1
0x8a082  ldstr    aCurrencydecima// "currencydecimalprecision"
0x8a087  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a08c  brtrue.s loc_8A0A4
0x8a08e  ldarg.0
0x8a08f  ldarg.1
0x8a090  ldstr    aCurrencydecima// "currencydecimalprecision"
0x8a095  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a09a  unbox.any [mscorlib]System.Int32
0x8a09f  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_CurrencyDecimalPrecision(int32 value)
0x8a0a4  ldarg.1
0x8a0a5  ldstr    aNumberseparato// "numberseparator"
0x8a0aa  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a0af  brtrue.s loc_8A0C7
0x8a0b1  ldarg.0
0x8a0b2  ldarg.1
0x8a0b3  ldstr    aNumberseparato// "numberseparator"
0x8a0b8  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a0bd  castclass [mscorlib]System.String
0x8a0c2  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_NumberSeparator(string value)
0x8a0c7  ldarg.1
0x8a0c8  ldstr    aDecimalsymbol// "decimalsymbol"
0x8a0cd  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a0d2  brtrue.s loc_8A0EA
0x8a0d4  ldarg.0
0x8a0d5  ldarg.1
0x8a0d6  ldstr    aDecimalsymbol// "decimalsymbol"
0x8a0db  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a0e0  castclass [mscorlib]System.String
0x8a0e5  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_DecimalSymbol(string value)
0x8a0ea  ldarg.1
0x8a0eb  ldstr    aNumbergroupfor// "numbergroupformat"
0x8a0f0  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a0f5  brtrue.s loc_8A10D
0x8a0f7  ldarg.0
0x8a0f8  ldarg.1
0x8a0f9  ldstr    aNumbergroupfor// "numbergroupformat"
0x8a0fe  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a103  castclass [mscorlib]System.String
0x8a108  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_NumberGroupFormat(string value)
0x8a10d  ldarg.1
0x8a10e  ldstr    aYearstartweekc// "yearstartweekcode"
0x8a113  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a118  brtrue.s loc_8A130
0x8a11a  ldarg.0
0x8a11b  ldarg.1
0x8a11c  ldstr    aYearstartweekc// "yearstartweekcode"
0x8a121  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a126  unbox.any [mscorlib]System.Int32
0x8a12b  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_YearStartWeekCode(int32 value)
0x8a130  ldarg.1
0x8a131  ldstr    aWeekstartdayco// "weekstartdaycode"
0x8a136  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a13b  brtrue.s loc_8A153
0x8a13d  ldarg.0
0x8a13e  ldarg.1
0x8a13f  ldstr    aWeekstartdayco// "weekstartdaycode"
0x8a144  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a149  unbox.any [mscorlib]System.Int32
0x8a14e  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_WeekStartDayCode(int32 value)
0x8a153  ldarg.1
0x8a154  ldstr    aWebresourcehas// "webresourcehash"
0x8a159  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a15e  brtrue.s loc_8A176
0x8a160  ldarg.0
0x8a161  ldarg.1
0x8a162  ldstr    aWebresourcehas// "webresourcehash"
0x8a167  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a16c  castclass [mscorlib]System.String
0x8a171  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_WebResourceHash(string value)
0x8a176  ldarg.1
0x8a177  ldstr    aAllowuserformm// "allowuserformmodepreference"
0x8a17c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a181  brtrue.s loc_8A19E
0x8a183  ldarg.0
0x8a184  ldarg.1
0x8a185  ldstr    aAllowuserformm// "allowuserformmodepreference"
0x8a18a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a18f  unbox.any [mscorlib]System.Boolean
0x8a194  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x8a199  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_AllowUserFormModePreference(valuetype [mscorlib]System.Nullable`1<bool> value)
0x8a19e  ldarg.1
0x8a19f  ldstr    aUsereadform// "usereadform"
0x8a1a4  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a1a9  brtrue.s loc_8A1C6
0x8a1ab  ldarg.0
0x8a1ac  ldarg.1
0x8a1ad  ldstr    aUsereadform// "usereadform"
0x8a1b2  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a1b7  unbox.any [mscorlib]System.Boolean
0x8a1bc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x8a1c1  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_UseReadForm(valuetype [mscorlib]System.Nullable`1<bool> value)
0x8a1c6  ldarg.1
0x8a1c7  ldstr    aQuickfindrecor// "quickfindrecordlimitenabled"
0x8a1cc  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a1d1  brtrue.s loc_8A1EE
0x8a1d3  ldarg.0
0x8a1d4  ldarg.1
0x8a1d5  ldstr    aQuickfindrecor// "quickfindrecordlimitenabled"
0x8a1da  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a1df  unbox.any [mscorlib]System.Boolean
0x8a1e4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x8a1e9  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_QuickFindRecordLimitEnabled(valuetype [mscorlib]System.Nullable`1<bool> value)
0x8a1ee  ldarg.1
0x8a1ef  ldstr    aIsfulltextsear// "isfulltextsearchenabled"
0x8a1f4  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a1f9  brtrue.s loc_8A211
0x8a1fb  ldarg.0
0x8a1fc  ldarg.1
0x8a1fd  ldstr    aIsfulltextsear// "isfulltextsearchenabled"
0x8a202  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a207  unbox.any [mscorlib]System.Boolean
0x8a20c  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_IsFullTextSearchEnabled(bool value)
0x8a211  ldarg.1
0x8a212  ldstr    aIsexternalsear// "isexternalsearchindexenabled"
0x8a217  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a21c  brtrue.s loc_8A234
0x8a21e  ldarg.0
0x8a21f  ldarg.1
0x8a220  ldstr    aIsexternalsear// "isexternalsearchindexenabled"
0x8a225  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a22a  unbox.any [mscorlib]System.Boolean
0x8a22f  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_IsElasticsearchEnabled(bool value)
0x8a234  ldarg.1
0x8a235  ldstr    aIsexternalfile// "isexternalfilestorageenabled"
0x8a23a  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a23f  brtrue.s loc_8A257
0x8a241  ldarg.0
0x8a242  ldarg.1
0x8a243  ldstr    aIsexternalfile// "isexternalfilestorageenabled"
0x8a248  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a24d  unbox.any [mscorlib]System.Boolean
0x8a252  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_IsExternalFileStorageEnabled(bool value)
0x8a257  ldarg.1
0x8a258  ldstr    aIsmobileofflin// "ismobileofflineenabled"
0x8a25d  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a262  brtrue.s loc_8A27A
0x8a264  ldarg.0
0x8a265  ldarg.1
0x8a266  ldstr    aIsmobileofflin// "ismobileofflineenabled"
0x8a26b  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a270  unbox.any [mscorlib]System.Boolean
0x8a275  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_IsMobileOfflineEnabled(bool value)
0x8a27a  ldarg.1
0x8a27b  ldstr    aMobileofflines// "mobileOfflineSyncInterval"
0x8a280  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a285  brtrue.s loc_8A29D
0x8a287  ldarg.0
0x8a288  ldarg.1
0x8a289  ldstr    aMobileofflines// "mobileOfflineSyncInterval"
0x8a28e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a293  unbox.any [mscorlib]System.Int32
0x8a298  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_MobileOfflineSyncInterval(int32 value)
0x8a29d  ldarg.1
0x8a29e  ldstr    aDateformatstri// "dateformatstring"
0x8a2a3  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a2a8  brtrue.s loc_8A2C0
0x8a2aa  ldarg.0
0x8a2ab  ldarg.1
0x8a2ac  ldstr    aDateformatstri// "dateformatstring"
0x8a2b1  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a2b6  castclass [mscorlib]System.String
0x8a2bb  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_DateFormatString(string value)
0x8a2c0  ldarg.1
0x8a2c1  ldstr    aTimeformatstri// "timeformatstring"
0x8a2c6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a2cb  brtrue.s loc_8A2E3
0x8a2cd  ldarg.0
0x8a2ce  ldarg.1
0x8a2cf  ldstr    aTimeformatstri// "timeformatstring"
0x8a2d4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a2d9  castclass [mscorlib]System.String
0x8a2de  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_TimeFormatString(string value)
0x8a2e3  ldarg.1
0x8a2e4  ldstr    aName_0// "name"
0x8a2e9  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a2ee  brtrue.s loc_8A306
0x8a2f0  ldarg.0
0x8a2f1  ldarg.1
0x8a2f2  ldstr    aName_0// "name"
0x8a2f7  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8a2fc  castclass [mscorlib]System.String
0x8a301  call     instance void Microsoft.Crm.Caching.OrganizationSettings::set_Name(string value)
0x8a306  ldarg.1
0x8a307  ldstr    aCurrencysymbol_0// "currencysymbol"
0x8a30c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8a311  brtrue.s loc_8A329
0x8a313  ldarg.0
0x8a314  ldarg.1
0x8a315  ldstr    aCurrencysymbol_0// "currencysymbol"
  ... truncated ...
```
