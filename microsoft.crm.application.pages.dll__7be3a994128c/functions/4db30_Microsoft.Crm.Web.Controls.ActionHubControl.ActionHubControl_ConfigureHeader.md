# Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::ConfigureHeader

- ea: `0x4db30`
- end: `0x4ddb5`
- name: `Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::ConfigureHeader`
- size: `645`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4db30`

## string_xrefs

- `0x4dcb6`: `/_static/_common/scripts/CommandBarActions.js`
- `0x4db86`: `ActionCard.CFC.Common.NoCardsTitle`
- `0x4dc83`: `USE_SKYPE_PROTOCOL`
- `0x4dccb`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x4dce0`: `/_static/_common/scripts/Wall.Control.js`
- `0x4dd34`: `/_static/_common/scripts/react.js`
- `0x4dd6e`: `/_common/windowinformation/windowinformation.js.aspx`
- `0x4dd92`: `cc_MscrmControls.ActionCards.ActionCardCommands/RelationshipAssistantCommands.js`

## pseudocode

```c

```

## disassembly

```asm
0x4db30  ldarg.0
0x4db31  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::ConfigureHeader()
0x4db36  ldarg.0
0x4db37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4db3c  ldc.i4.0
0x4db3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_UseBundling(bool)
0x4db42  ldarg.0
0x4db43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4db48  ldc.i4.1
0x4db49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x4db4e  ldarg.0
0x4db4f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4db54  ldc.i4.1
0x4db55  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x4db5a  ldarg.0
0x4db5b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4db60  ldc.i4.1
0x4db61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJSRender(bool)
0x4db66  ldarg.0
0x4db67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4db6c  ldstr    aDelveactionhub// "DelveActionHub.NoRecordsMessage"
0x4db71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4db76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4db7b  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::emptyCardMessage
0x4db80  ldarg.0
0x4db81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4db86  ldstr    aActioncardCfcC// "ActionCard.CFC.Common.NoCardsTitle"
0x4db8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4db90  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4db95  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::emptyCardMessageHeader
0x4db9a  ldarg.0
0x4db9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dba0  ldstr    aDelveactionhub_0// "DelveActionHub.Preview"
0x4dba5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dbaa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4dbaf  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::imageTitle
0x4dbb4  ldarg.0
0x4dbb5  ldfld    bool Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::isCarouselView
0x4dbba  brfalse.s loc_4DBD3
0x4dbbc  ldarg.0
0x4dbbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dbc2  ldstr    aActioncardRela// "ActionCard.RelationshipAssistance.Title"
0x4dbc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dbcc  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceTitle
0x4dbd1  br.s     loc_4DBE8
0x4dbd3  ldarg.0
0x4dbd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dbd9  ldstr    aActioncardRela_0// "ActionCard.RelationshipAssistance.Assis"...
0x4dbde  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dbe3  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceTitle
0x4dbe8  ldarg.0
0x4dbe9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dbee  ldstr    aActioncardRela_1// "ActionCard.RelationshipAssistance.Feedb"...
0x4dbf3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dbf8  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceFeedbackTitle
0x4dbfd  ldarg.0
0x4dbfe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dc03  ldstr    aActioncardRela_2// "ActionCard.RelationshipAssistance.Custo"...
0x4dc08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dc0d  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceCustomizeTitle
0x4dc12  ldarg.0
0x4dc13  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dc18  ldstr    aActioncardRela_3// "ActionCard.RelationshipAssistance.Previ"...
0x4dc1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dc22  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistancePreviousTitle
0x4dc27  ldarg.0
0x4dc28  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dc2d  ldstr    aActioncardRela_4// "ActionCard.RelationshipAssistance.Next."...
0x4dc32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dc37  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceNextTitle
0x4dc3c  ldarg.0
0x4dc3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4dc42  ldstr    aDelveactionhub_1// "DelveActionHub.Refreshwall"
0x4dc47  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4dc4c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4dc51  stfld    string Microsoft.Crm.Web.Controls.ActionHubControl.ActionHubControl::relationshipAssistanceHeaderRefreshTitle
0x4dc56  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.DefaultCountryCodeHelper::get_CountryCode()
0x4dc5b  stloc.0
0x4dc5c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x4dc61  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_UseSkypeProtocol()
0x4dc66  stloc.1
0x4dc67  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x4dc6c  ldc.i4.1
0x4dc6d  newarr   [mscorlib]System.Char
0x4dc72  dup
0x4dc73  ldc.i4.0
0x4dc74  ldc.i4.s 0x2F
0x4dc76  stelem.i2
0x4dc77  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x4dc7c  pop
0x4dc7d  ldarg.0
0x4dc7e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dc83  ldstr    aUseSkypeProtoc// "USE_SKYPE_PROTOCOL"
0x4dc88  ldloc.1
0x4dc89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x4dc8e  ldarg.0
0x4dc8f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dc94  ldstr    aPhoneNumberDef// "PHONE_NUMBER_DEFAULT_COUNTRY_CODE"
0x4dc99  ldloc.0
0x4dc9a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x4dc9f  ldarg.0
0x4dca0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dca5  ldstr    aIsflatuipage// "_ISFLATUIPAGE"
0x4dcaa  ldc.i4.1
0x4dcab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x4dcb0  ldarg.0
0x4dcb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dcb6  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0x4dcbb  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dcc0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dcc5  ldarg.0
0x4dcc6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dccb  ldstr    aStaticCommonSc_26// "/_static/_common/scripts/Wall.Interface"...
0x4dcd0  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dcd5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dcda  ldarg.0
0x4dcdb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dce0  ldstr    aStaticCommonSc_27// "/_static/_common/scripts/Wall.Control.j"...
0x4dce5  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dcea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dcef  ldarg.0
0x4dcf0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dcf5  ldstr    aStaticFormsAct// "/_static/_forms/actionhubcontrol.js"
0x4dcfa  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dcff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dd04  ldarg.0
0x4dd05  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd0a  ldstr    aStaticActiviti// "/_static/activities/email.js"
0x4dd0f  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dd14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dd19  ldarg.0
0x4dd1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd1f  ldstr    aStaticControls_15// "/_static/_controls/actionhubcontrol/rx."...
0x4dd24  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dd29  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dd2e  ldarg.0
0x4dd2f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd34  ldstr    aStaticCommonSc_28// "/_static/_common/scripts/react.js"
0x4dd39  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dd3e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dd43  ldarg.0
0x4dd44  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd49  ldstr    aStaticControls_16// "/_static/_controls/actionhubcontrol/act"...
0x4dd4e  ldstr    aRelationshipin// "RelationshipIntelligenceBundle"
0x4dd53  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string, string)
0x4dd58  ldarg.0
0x4dd59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd5e  ldstr    aControlsAction// "/_controls/ActionHubControl/actionhubco"...
0x4dd63  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x4dd68  ldarg.0
0x4dd69  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4dd6e  ldstr    aCommonWindowin_0// "/_common/windowinformation/windowinform"...
0x4dd73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4dd78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dd7d  ldstr    a01_3// "{0}{1}"
0x4dd82  ldc.i4.2
0x4dd83  newarr   [mscorlib]System.Object
0x4dd88  dup
0x4dd89  ldc.i4.0
0x4dd8a  ldstr    aWebresource_0// "$webresource:"
0x4dd8f  stelem.ref
0x4dd90  dup
0x4dd91  ldc.i4.1
0x4dd92  ldstr    aCcMscrmcontrol// "cc_MscrmControls.ActionCards.ActionCard"...
0x4dd97  stelem.ref
0x4dd98  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4dd9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4dda2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4dda7  stloc.2
0x4dda8  ldarg.0
0x4dda9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4ddae  ldloc.2
0x4ddaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x4ddb4  ret
```
