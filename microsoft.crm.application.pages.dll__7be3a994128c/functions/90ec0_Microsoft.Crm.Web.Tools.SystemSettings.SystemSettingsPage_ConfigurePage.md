# Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePage

- ea: `0x90ec0`
- end: `0x916e0`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePage`
- size: `2080`
- prototype: ``
- caller_count: `0`
- callee_count: `61`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x90ec0`
- `0x916e0`
- `0x918b0`
- `0x92010`
- `0x92340`
- `0x92520`
- `0x92840`
- `0x92900`
- `0x929a0`
- `0x92d60`
- `0x92dd0`
- `0x93000`
- `0x93390`
- `0x93400`
- `0x93470`
- `0x93510`
- `0x935d0`
- `0x93670`
- `0x936b0`
- `0x936e0`
- `0x93750`
- `0x93850`
- `0x93920`
- `0x93dc0`
- `0x93e00`
- `0x93e70`
- `0x93ee0`
- `0x93f50`
- `0x93fc0`
- `0x94070`
- `0x940e0`
- `0x94190`
- `0x94260`
- `0x942d0`
- `0x94340`
- `0x943f0`
- `0x944e0`
- `0x94550`
- `0x94570`
- `0x94690`
- `0x94700`
- `0x947e0`
- `0x94b40`
- `0x94c50`
- `0x94cd0`
- `0x94e00`
- `0x94f60`
- `0x95270`
- `0x95560`
- `0x957e0`

## string_xrefs

- `0x9104d`: `trackingtokenidbase`
- `0x91058`: `trackingtokeniddigits`
- `0x910d1`: `acknowledgementtemplateid`
- `0x910fd`: `allowoutlookscheduledsyncs`
- `0x91134`: `allowofflinescheduledsyncs`
- `0x9127e`: `useskypeprotocol`
- `0x9135a`: `isassignedtaskssyncenabled`
- `0x91386`: `createproductswithoutparentinactivestate`
- `0x9139c`: `plugintracelogsetting`
- `0x913a7`: `taskbasedflowenabled`
- `0x913c8`: `productrecommendationsenabled`

## pseudocode

```c

```

## disassembly

```asm
0x90ec0  ldarg.0
0x90ec1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x90ec6  ldarg.0
0x90ec7  ldc.i4.0
0x90ec8  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_reportCategoryEnabled
0x90ecd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x90ed2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x90ed7  brfalse.s loc_90EE0
0x90ed9  ldarg.0
0x90eda  ldc.i4.1
0x90edb  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_reportCategoryEnabled
0x90ee0  ldarg.0
0x90ee1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x90ee6  brfalse.s loc_90F0B
0x90ee8  call     valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ClientMajorVersion()
0x90eed  stloc.s  5
0x90eef  ldloca.s 5
0x90ef1  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x90ef6  brfalse.s loc_90F0B
0x90ef8  call     valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ClientMajorVersion()
0x90efd  stloc.s  5
0x90eff  ldloca.s 5
0x90f01  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x90f06  ldc.i4.7
0x90f07  clt
0x90f09  br.s     loc_90F0C
0x90f0b  ldc.i4.0
0x90f0c  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::disableSynchronizationTab
0x90f11  ldarg.0
0x90f12  ldarg.0
0x90f13  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsRelationshipAnalyticsEnabled
0x90f18  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsRelationshipIntelligenceEnabled
0x90f1d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnPremise()
0x90f22  ldc.i4.0
0x90f23  ceq
0x90f25  stloc.0
0x90f26  ldarg.0
0x90f27  ldloc.0
0x90f28  brfalse.s loc_90F65
0x90f2a  ldarg.0
0x90f2b  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCortanaProactiveExperienceFeatureEnabled
0x90f30  brtrue.s loc_90F62
0x90f32  ldarg.0
0x90f33  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsRelationshipIntelligenceEnabled
0x90f38  brtrue.s loc_90F62
0x90f3a  ldarg.0
0x90f3b  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsProductRecommendationsFeatureAvailable
0x90f40  brtrue.s loc_90F62
0x90f42  ldarg.0
0x90f43  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ShouldShowTaskBasedFlowItem
0x90f48  brtrue.s loc_90F62
0x90f4a  ldarg.0
0x90f4b  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsTextAnalyticsFeatureAvailable
0x90f50  brtrue.s loc_90F62
0x90f52  ldarg.0
0x90f53  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ShouldShowActionSupportItem
0x90f58  brtrue.s loc_90F62
0x90f5a  ldarg.0
0x90f5b  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsSyncFeatureEnabled
0x90f60  br.s     loc_90F66
0x90f62  ldc.i4.1
0x90f63  br.s     loc_90F66
0x90f65  ldc.i4.0
0x90f66  stfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::EnablePreviewTab
0x90f6b  ldarg.0
0x90f6c  ldarg.0
0x90f6d  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x90f72  ldstr    aFeatureset// "featureset"
0x90f77  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x90f7c  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::FeatureSetString
0x90f81  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x90f86  dup
0x90f87  ldstr    aWeekstartdayco// "weekstartdaycode"
0x90f8c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90f91  dup
0x90f92  ldstr    aTimeformatcode// "timeformatcode"
0x90f97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90f9c  dup
0x90f9d  ldstr    aNumberformat_0// "numberformat"
0x90fa2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fa7  dup
0x90fa8  ldstr    aNegativeformat// "negativeformatcode"
0x90fad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fb2  dup
0x90fb3  ldstr    aLanguagecode// "languagecode"
0x90fb8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fbd  dup
0x90fbe  ldstr    aCalendartype// "calendartype"
0x90fc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fc8  dup
0x90fc9  ldstr    aDateformatcode// "dateformatcode"
0x90fce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fd3  dup
0x90fd4  ldstr    aDateformatstri// "dateformatstring"
0x90fd9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fde  dup
0x90fdf  ldstr    aCurrencysymbol// "currencysymbol"
0x90fe4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fe9  dup
0x90fea  ldstr    aFullnameconven// "fullnameconventioncode"
0x90fef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90ff4  dup
0x90ff5  ldstr    aFiscalperiodty_0// "fiscalperiodtype"
0x90ffa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90fff  dup
0x91000  ldstr    aFiscalcalendar// "fiscalcalendarstart"
0x91005  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9100a  dup
0x9100b  ldstr    aDateseparator// "dateseparator"
0x91010  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91015  dup
0x91016  ldstr    aShowweeknumber// "showweeknumber"
0x9101b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91020  dup
0x91021  ldstr    aCurrencyformat// "currencyformatcode"
0x91026  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9102b  dup
0x9102c  ldstr    aIgnoreinternal// "ignoreinternalemail"
0x91031  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91036  dup
0x91037  ldstr    aTrackingprefix// "trackingprefix"
0x9103c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91041  dup
0x91042  ldstr    aMaximumtrackin// "maximumtrackingnumber"
0x91047  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9104c  dup
0x9104d  ldstr    aTrackingtokeni// "trackingtokenidbase"
0x91052  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91057  dup
0x91058  ldstr    aTrackingtokeni_0// "trackingtokeniddigits"
0x9105d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91062  dup
0x91063  ldstr    aEnablesmartmat// "enablesmartmatching"
0x91068  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9106d  dup
0x9106e  ldstr    aHashfilterkeyw// "hashfilterkeywords"
0x91073  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91078  dup
0x91079  ldstr    aHashmaxcount// "hashmaxcount"
0x9107e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91083  dup
0x91084  ldstr    aHashdeltasubje// "hashdeltasubjectcount"
0x91089  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9108e  dup
0x9108f  ldstr    aHashminaddress// "hashminaddresscount"
0x91094  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91099  dup
0x9109a  ldstr    aPricingdecimal// "pricingdecimalprecision"
0x9109f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910a4  dup
0x910a5  ldstr    aAllowmarketing// "allowmarketingemailexecution"
0x910aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910af  dup
0x910b0  ldstr    aAllowautounsub// "allowautounsubscribe"
0x910b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910ba  dup
0x910bb  ldstr    aAllowautorespo// "allowautoresponsecreation"
0x910c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910c5  dup
0x910c6  ldstr    aAllowautounsub_0// "allowautounsubscribeacknowledgement"
0x910cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910d0  dup
0x910d1  ldstr    aAcknowledgemen// "acknowledgementtemplateid"
0x910d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910db  dup
0x910dc  ldstr    aEmailsendpolli// "emailsendpollingperiod"
0x910e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910e6  dup
0x910e7  ldstr    aTagpollingperi// "tagpollingperiod"
0x910ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910f1  dup
0x910f2  ldstr    aTagmaxaggressi// "tagmaxaggressivecycles"
0x910f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910fc  dup
0x910fd  ldstr    aAllowoutlooksc// "allowoutlookscheduledsyncs"
0x91102  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91107  dup
0x91108  ldstr    aMinoutlooksync// "minoutlooksyncinterval"
0x9110d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91112  dup
0x91113  ldstr    aMinofflinesync// "minofflinesyncinterval"
0x91118  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9111d  dup
0x9111e  ldstr    aAllowaddressbo// "allowaddressbooksyncs"
0x91123  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91128  dup
0x91129  ldstr    aMinaddressbook// "minaddressbooksyncinterval"
0x9112e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91133  dup
0x91134  ldstr    aAllowofflinesc// "allowofflinescheduledsyncs"
0x91139  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9113e  dup
0x9113f  ldstr    aSharetopreviou// "sharetopreviousowneronassign"
0x91144  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91149  dup
0x9114a  ldstr    aCurrencydispla// "currencydisplayoption"
0x9114f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91154  dup
0x91155  ldstr    aIsappmode// "isappmode"
0x9115a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9115f  dup
0x91160  ldstr    aBlockedattachm// "blockedattachments"
0x91165  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9116a  dup
0x9116b  ldstr    aRendersecureif// "rendersecureiframeforemail"
0x91170  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91175  dup
0x91176  ldstr    aMaxappointment// "maxappointmentdurationdays"
0x9117b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91180  dup
0x91181  ldstr    aSchedulingengi// "schedulingengine"
0x91186  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9118b  dup
0x9118c  ldstr    aAllowunresolve// "allowunresolvedpartiesonemailsend"
0x91191  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91196  dup
0x91197  ldstr    aMaxuploadfiles// "maxuploadfilesize"
0x9119c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911a1  dup
0x911a2  ldstr    aLocaleid// "localeid"
0x911a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911ac  dup
0x911ad  ldstr    aAllowclientmes// "allowclientmessagebarad"
0x911b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911b7  dup
0x911b8  ldstr    aIspresenceenab// "ispresenceenabled"
0x911bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911c2  dup
0x911c3  ldstr    aIsautosaveenab// "isautosaveenabled"
0x911c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911cd  dup
0x911ce  ldstr    aQuickfindrecor// "quickfindrecordlimitenabled"
0x911d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911d8  dup
0x911d9  ldstr    aIsfulltextsear// "isfulltextsearchenabled"
0x911de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911e3  dup
0x911e4  ldstr    aIsexternalsear// "isexternalsearchindexenabled"
0x911e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911ee  dup
0x911ef  ldstr    aRequireapprova// "requireapprovalforuseremail"
0x911f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911f9  dup
0x911fa  ldstr    aOrgdborgsettin// "orgdborgsettings"
0x911ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91204  dup
0x91205  ldstr    aRequireapprova_0// "requireapprovalforqueueemail"
0x9120a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9120f  dup
0x91210  ldstr    aGoalrollupexpi// "goalrollupexpirytime"
0x91215  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9121a  dup
0x9121b  ldstr    aGoalrollupfreq// "goalrollupfrequency"
0x91220  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91225  dup
0x91226  ldstr    aGlobalhelpurl// "globalhelpurl"
0x9122b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91230  dup
0x91231  ldstr    aGlobalhelpurle// "globalhelpurlenabled"
0x91236  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9123b  dup
0x9123c  ldstr    aGlobalappendur// "globalappendurlparametersenabled"
0x91241  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91246  dup
0x91247  ldstr    aEnableimmersiv// "enableimmersiveskypeintegration"
0x9124c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91251  dup
0x91252  ldstr    aEnablebingmaps// "enablebingmapsintegration"
0x91257  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9125c  dup
0x9125d  ldstr    aBingmapsapikey// "bingmapsapikey"
0x91262  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91267  dup
0x91268  ldstr    aIsdefaultcount// "isdefaultcountrycodecheckenabled"
0x9126d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91272  dup
0x91273  ldstr    aDefaultcountry_0// "defaultcountrycode"
0x91278  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9127d  dup
0x9127e  ldstr    aUseskypeprotoc// "useskypeprotocol"
0x91283  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91288  dup
0x91289  ldstr    aDefaultemailse// "defaultemailserverprofileid"
0x9128e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91293  dup
0x91294  ldstr    aEmailcorrelati// "emailcorrelationenabled"
0x91299  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9129e  dup
0x9129f  ldstr    aEmailconnectio// "emailconnectionchannel"
0x912a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x912a9  dup
0x912aa  ldstr    aDefaultemailse_0// "defaultemailsettings"
0x912af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x912b4  dup
0x912b5  ldstr    aMaxproductsinb// "maxproductsinbundle"
0x912ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x912bf  dup
0x912c0  ldstr    aUseinbuiltrule// "useinbuiltrulefordefaultpricelistselect"...
0x912c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x912ca  dup
  ... truncated ...
```
