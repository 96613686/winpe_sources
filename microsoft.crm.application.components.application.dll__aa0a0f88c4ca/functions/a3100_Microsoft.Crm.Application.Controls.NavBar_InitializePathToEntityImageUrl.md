# Microsoft.Crm.Application.Controls.NavBar::InitializePathToEntityImageUrl

- ea: `0xa3100`
- end: `0xa32a5`
- name: `Microsoft.Crm.Application.Controls.NavBar::InitializePathToEntityImageUrl`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa4b70`

## callees

- `0xa3100`

## string_xrefs

- `0xa3255`: `Templates_32.png`
- `0xa3120`: `/ADMINSECURITY_AREA.ASPX`
- `0xa3125`: `Security_32.png`
- `0xa3150`: `/SERVICEMANAGEMENT.ASPX`
- `0xa3155`: `ServiceManagement_32.png`
- `0xa3190`: `/FWLINK/`
- `0xa31a0`: `/FWLINK/P/`
- `0xa31c5`: `ServiceCalendar_32.png`
- `0xa3225`: `EmailConfiguration_32.png`
- `0xa3250`: `/TEMPLATES.ASPX`
- `0xa3290`: `/UnifiedConfig.html`

## pseudocode

```c

```

## disassembly

```asm
0xa3100  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Controls.NavBar::_pathToEntityImageUrl
0xa3105  brtrue   loc_A32A4
0xa310a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xa310f  dup
0xa3110  ldstr    aAdminAspx// "/ADMIN.ASPX"
0xa3115  ldstr    aAdministration// "Administration_32.png"
0xa311a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa311f  dup
0xa3120  ldstr    aAdminsecurityA// "/ADMINSECURITY_AREA.ASPX"
0xa3125  ldstr    aSecurity32Png// "Security_32.png"
0xa312a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa312f  dup
0xa3130  ldstr    aAuditAreaAspx// "/AUDIT_AREA.ASPX"
0xa3135  ldstr    aAuditing32Png// "Auditing_32.png"
0xa313a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa313f  dup
0xa3140  ldstr    aBusinessAspx// "/BUSINESS.ASPX"
0xa3145  ldstr    aBusinessmanage// "BusinessManagement_32.png"
0xa314a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa314f  dup
0xa3150  ldstr    aServicemanagem// "/SERVICEMANAGEMENT.ASPX"
0xa3155  ldstr    aServicemanagem_0// "ServiceManagement_32.png"
0xa315a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa315f  dup
0xa3160  ldstr    aExternappmanag// "/EXTERNAPPMANAGEMENT.ASPX"
0xa3165  ldstr    aExternappmanag_0// "ExternAppManagement_32.png"
0xa316a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa316f  dup
0xa3170  ldstr    aDatamanagement_0// "/DATAMANAGEMENT.ASPX"
0xa3175  ldstr    aDatabasemanage// "DatabaseManagement_32.png"
0xa317a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa317f  dup
0xa3180  ldstr    aDocumentmanage_1// "/DOCUMENTMANAGEMENT.ASPX"
0xa3185  ldstr    aDocumentmanage_2// "DocumentManagement_32.png"
0xa318a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa318f  dup
0xa3190  ldstr    aFwlink// "/FWLINK/"
0xa3195  ldstr    aHelp32Png// "Help_32.png"
0xa319a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa319f  dup
0xa31a0  ldstr    aFwlinkP// "/FWLINK/P/"
0xa31a5  ldstr    aHelp32Png// "Help_32.png"
0xa31aa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31af  dup
0xa31b0  ldstr    aHomeCalendarAs// "/HOME_CALENDAR.ASPX"
0xa31b5  ldstr    aCalendar32Png// "Calendar_32.png"
0xa31ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31bf  dup
0xa31c0  ldstr    aHomeApptbookAs// "/HOME_APPTBOOK.ASPX"
0xa31c5  ldstr    aServicecalenda// "ServiceCalendar_32.png"
0xa31ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31cf  dup
0xa31d0  ldstr    aHomeAsyncopera// "/HOME_ASYNCOPERATION.ASPX"
0xa31d5  ldstr    aSystemjobs32Pn// "SystemJobs_32.png"
0xa31da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31df  dup
0xa31e0  ldstr    aHomeDashboards// "/HOME_DASHBOARDS.ASPX"
0xa31e5  ldstr    aDashboard32Png// "Dashboard_32.png"
0xa31ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31ef  dup
0xa31f0  ldstr    aHomeDebugAspx// "/HOME_DEBUG.ASPX"
0xa31f5  ldstr    aDebuginfo32Png// "DebugInfo_32.png"
0xa31fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa31ff  dup
0xa3200  ldstr    aPersonalwallHt// "/PERSONALWALL.HTM"
0xa3205  ldstr    aWhatsnew32Png// "WhatsNew_32.png"
0xa320a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa320f  dup
0xa3210  ldstr    aProductcatalog// "/PRODUCTCATALOG.ASPX"
0xa3215  ldstr    aProductcatalog_0// "ProductCatalog_32.png"
0xa321a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa321f  dup
0xa3220  ldstr    aSocialAreaAspx// "/SOCIAL_AREA.ASPX"
0xa3225  ldstr    aEmailconfigura// "EmailConfiguration_32.png"
0xa322a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa322f  dup
0xa3230  ldstr    aSolutionsmarke_0// "/SOLUTIONSMARKETPLACE.ASPX"
0xa3235  ldstr    aDynamicsmarket// "DynamicsMarketplace_32.png"
0xa323a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa323f  dup
0xa3240  ldstr    aSystemcustomiz_19// "/SYSTEMCUSTOMIZATION.ASPX"
0xa3245  ldstr    aCustomizations// "Customizations_32.png"
0xa324a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa324f  dup
0xa3250  ldstr    aTemplatesAspx// "/TEMPLATES.ASPX"
0xa3255  ldstr    aTemplates32Png// "Templates_32.png"
0xa325a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa325f  dup
0xa3260  ldstr    aMobileofflineA// "/MOBILEOFFLINE.ASPX"
0xa3265  ldstr    aMobileofflinep// "MobileOfflineProfile_32.png"
0xa326a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa326f  dup
0xa3270  ldstr    aTracewallAspx// "/TRACEWALL.ASPX"
0xa3275  ldstr    aAlerts32Png// "Alerts_32.png"
0xa327a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa327f  dup
0xa3280  ldstr    aAppforoutlooka// "/APPFOROUTLOOKADMINSETTINGS.ASPX"
0xa3285  ldstr    aCrmAppsIcon80x// "crm_apps_icon_80x80.png"
0xa328a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa328f  dup
0xa3290  ldstr    aUnifiedconfigH// "/UnifiedConfig.html"
0xa3295  ldstr    aRelationshipIn// "Relationship_Intelligence_32.png"
0xa329a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa329f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Controls.NavBar::_pathToEntityImageUrl
0xa32a4  ret
```
