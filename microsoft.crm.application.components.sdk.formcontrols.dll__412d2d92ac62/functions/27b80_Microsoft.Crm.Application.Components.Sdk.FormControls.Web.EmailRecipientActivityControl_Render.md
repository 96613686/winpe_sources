# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::Render

- ea: `0x27b80`
- end: `0x27e90`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::Render`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x27b60`
- `0x27b80`
- `0x28240`
- `0x28280`

## string_xrefs

- `0x27c95`: `<div id = "EmailOpened" tabindex="{0}" class="EmailActivityChildContainer">`
- `0x27cab`: `<div class="ms-crm-div-NotVisible" id="EmailOpenedJawsReader"></div>`
- `0x27cb6`: `<span id = "EmailopendCount">`
- `0x27ccc`: `<span id="EmailopendImage" class="EmailRecipientActivityImage"></ span >`
- `0x27cd7`: `<div class="EmailRecipientActivityText" id="EmailopendText">`
- `0x27ce1`: `CustomControl_EmailEngagment_Opened`
- `0x27d1c`: `<div class="ms-crm-div-NotVisible" id="AttachmentViewedJawsReader"></div>`
- `0x27d6c`: `<div id = "LinkClicked" tabindex="{0}" class="EmailActivityChildContainer">`
- `0x27d82`: `<div class="ms-crm-div-NotVisible" id="LinkClickedJawsReader"></div>`
- `0x27da3`: `<div class="EmailRecipientActivityText" id="LinkClickedText">`
- `0x27dad`: `EmailEngagment_LinksViewed_Text`
- `0x27de8`: `<div class="ms-crm-div-NotVisible" id="EmailRepliedJawsReader"></div>`

## pseudocode

```c

```

## disassembly

```asm
0x27b80  ldarg.0
0x27b81  call     instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x27b86  ldsfld   string [mscorlib]System.String::Empty
0x27b8b  stloc.0
0x27b8c  ldc.i4.0
0x27b8d  stloc.1
0x27b8e  ldc.i4.0
0x27b8f  stloc.2
0x27b90  ldarg.1
0x27b91  ldstr    aDivId0ClassRec// "<div id=\"{0}\" class=\"RecipientActivi"...
0x27b96  ldarg.0
0x27b97  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x27b9c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x27ba1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27ba6  ldarg.1
0x27ba7  ldstr    asc_3033C// ">"
0x27bac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27bb1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x27bb6  brfalse.s loc_27BC1
0x27bb8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x27bbd  brtrue.s loc_27BC1
0x27bbf  ldc.i4.1
0x27bc0  stloc.2
0x27bc1  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::IsEmailEngagementFeatureEnabled()
0x27bc6  brfalse  loc_27E84
0x27bcb  ldloc.2
0x27bcc  brtrue   loc_27E84
0x27bd1  ldarg.0
0x27bd2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::get_CurrentForm()
0x27bd7  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x27bdc  brfalse  loc_27E84
0x27be1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x27be6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27beb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x27bf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27bf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x27bfa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x27bff  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x27c04  stloc.3
0x27c05  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x27c0a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x27c0f  ldc.i4.2
0x27c10  bne.un.s loc_27C49
0x27c12  ldloc.3
0x27c13  brfalse.s loc_27C25
0x27c15  ldloc.3
0x27c16  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableBingMapsIntegration()
0x27c1b  brtrue.s loc_27C25
0x27c1d  ldsfld   string [mscorlib]System.String::Empty
0x27c22  stloc.0
0x27c23  br.s     loc_27C36
0x27c25  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x27c2a  ldstr    aBingmapsapikey// "BingMapsApiKey"
0x27c2f  ldc.i4.0
0x27c30  callvirt T0x2B000008
0x27c35  stloc.0
0x27c36  ldloc.3
0x27c37  brfalse.s loc_27C45
0x27c39  ldloc.3
0x27c3a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableBingMapsIntegration()
0x27c3f  brfalse.s loc_27C45
0x27c41  ldc.i4.1
0x27c42  stloc.1
0x27c43  br.s     loc_27C5D
0x27c45  ldc.i4.0
0x27c46  stloc.1
0x27c47  br.s     loc_27C5D
0x27c49  ldloc.3
0x27c4a  brfalse.s loc_27C5D
0x27c4c  ldloc.3
0x27c4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableBingMapsIntegration()
0x27c52  brfalse.s loc_27C5D
0x27c54  ldloc.3
0x27c55  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_BingMapsApiKey()
0x27c5a  stloc.0
0x27c5b  ldc.i4.1
0x27c5c  stloc.1
0x27c5d  ldarg.1
0x27c5e  ldstr    aDivIdEmailreci// "<div id=\"EmailRecipientActivityTitle\""...
0x27c63  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c68  ldarg.1
0x27c69  ldstr    aH3IdEmailrecip// "<h3 id=\"EmailRecipientActivityHeader\""...
0x27c6e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c73  ldarg.1
0x27c74  ldstr    aH3// "</h3>"
0x27c79  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c7e  ldarg.1
0x27c7f  ldstr    aDiv_0// "</div>"
0x27c84  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c89  ldarg.1
0x27c8a  ldstr    aDivIdEmailreci_0// "<div id=\"EmailRecipentActivityViewCont"...
0x27c8f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c94  ldarg.1
0x27c95  ldstr    aDivIdEmailopen// "<div id = \"EmailOpened\" tabindex=\"{0"...
0x27c9a  ldarg.0
0x27c9b  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::getCurrentTabIndex()
0x27ca0  box      [mscorlib]System.Int32
0x27ca5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27caa  ldarg.1
0x27cab  ldstr    aDivClassMsCrmD_1// "<div class=\"ms-crm-div-NotVisible\" id"...
0x27cb0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27cb5  ldarg.1
0x27cb6  ldstr    aSpanIdEmailope// "<span id = \"EmailopendCount\">"
0x27cbb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27cc0  ldarg.1
0x27cc1  ldstr    aSpan_5// "</span >"
0x27cc6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27ccb  ldarg.1
0x27ccc  ldstr    aSpanIdEmailope_0// "<span id=\"EmailopendImage\" class=\"Em"...
0x27cd1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27cd6  ldarg.1
0x27cd7  ldstr    aDivClassEmailr// "<div class=\"EmailRecipientActivityText"...
0x27cdc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27ce1  ldstr    aCustomcontrolE// "CustomControl_EmailEngagment_Opened"
0x27ce6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27ceb  ldstr    aDiv_0// "</div>"
0x27cf0  call     string [mscorlib]System.String::Concat(string, string, string)
0x27cf5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27cfa  ldarg.1
0x27cfb  ldstr    aDiv_0// "</div>"
0x27d00  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d05  ldarg.1
0x27d06  ldstr    aDivIdAttachmen// "<div id=\"AttachmentViewed\" tabindex="...
0x27d0b  ldarg.0
0x27d0c  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::getCurrentTabIndex()
0x27d11  box      [mscorlib]System.Int32
0x27d16  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27d1b  ldarg.1
0x27d1c  ldstr    aDivClassMsCrmD_2// "<div class=\"ms-crm-div-NotVisible\" id"...
0x27d21  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d26  ldarg.1
0x27d27  ldstr    aSpanIdEmailatt// "<span id = \"EmailAttachmentViewCount\""...
0x27d2c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d31  ldarg.1
0x27d32  ldstr    aSpanIdEmailatt_0// "<span id=\"EmailAttachmentViewImage\" c"...
0x27d37  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d3c  ldarg.1
0x27d3d  ldstr    aDivClassEmailr_0// "<div class=\"EmailRecipientActivityText"...
0x27d42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27d47  ldstr    aEmailengagment// "EmailEngagment_AttachmentViewed_Text"
0x27d4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27d51  ldstr    aDiv_0// "</div>"
0x27d56  call     string [mscorlib]System.String::Concat(string, string, string)
0x27d5b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d60  ldarg.1
0x27d61  ldstr    aDiv_0// "</div>"
0x27d66  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d6b  ldarg.1
0x27d6c  ldstr    aDivIdLinkclick// "<div id = \"LinkClicked\" tabindex=\"{0"...
0x27d71  ldarg.0
0x27d72  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::getCurrentTabIndex()
0x27d77  box      [mscorlib]System.Int32
0x27d7c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27d81  ldarg.1
0x27d82  ldstr    aDivClassMsCrmD_3// "<div class=\"ms-crm-div-NotVisible\" id"...
0x27d87  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d8c  ldarg.1
0x27d8d  ldstr    aSpanIdEmailcli// "<span id = \"EmailClickedCount\"> </spa"...
0x27d92  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d97  ldarg.1
0x27d98  ldstr    aSpanIdEmailcli_0// "<span id=\"EmailClickedImage\" class=\""...
0x27d9d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27da2  ldarg.1
0x27da3  ldstr    aDivClassEmailr_1// "<div class=\"EmailRecipientActivityText"...
0x27da8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27dad  ldstr    aEmailengagment_0// "EmailEngagment_LinksViewed_Text"
0x27db2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27db7  ldstr    aDiv_0// "</div>"
0x27dbc  call     string [mscorlib]System.String::Concat(string, string, string)
0x27dc1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27dc6  ldarg.1
0x27dc7  ldstr    aDiv_0// "</div>"
0x27dcc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27dd1  ldarg.1
0x27dd2  ldstr    aDivIdEmailrepl// "<div id = \"EmailReplied\" tabindex=\"{"...
0x27dd7  ldarg.0
0x27dd8  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::getCurrentTabIndex()
0x27ddd  box      [mscorlib]System.Int32
0x27de2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27de7  ldarg.1
0x27de8  ldstr    aDivClassMsCrmD_4// "<div class=\"ms-crm-div-NotVisible\" id"...
0x27ded  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27df2  ldarg.1
0x27df3  ldstr    aSpanIdEmailrep// "<span id = \"EmailRepliedCount\"> </spa"...
0x27df8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27dfd  ldarg.1
0x27dfe  ldstr    aSpanIdEmailrep_0// "<span id=\"EmailRepliedImage\" class=\""...
0x27e03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e08  ldarg.1
0x27e09  ldstr    aDivClassEmailr_2// "<div class=\"EmailRecipientActivityText"...
0x27e0e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27e13  ldstr    aEmailengagment_1// "EmailEngagment_Replied_Text"
0x27e18  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27e1d  ldstr    aDiv_0// "</div>"
0x27e22  call     string [mscorlib]System.String::Concat(string, string, string)
0x27e27  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e2c  ldarg.1
0x27e2d  ldstr    aDiv_0// "</div>"
0x27e32  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e37  ldarg.1
0x27e38  ldstr    aDiv_0// "</div>"
0x27e3d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e42  ldarg.1
0x27e43  ldc.i4.5
0x27e44  newarr   [mscorlib]System.String
0x27e49  dup
0x27e4a  ldc.i4.0
0x27e4b  ldstr    aDivIdInteracti// "<div id=\"InteractionViewMainContainerC"...
0x27e50  stelem.ref
0x27e51  dup
0x27e52  ldc.i4.1
0x27e53  ldloc.0
0x27e54  stelem.ref
0x27e55  dup
0x27e56  ldc.i4.2
0x27e57  ldstr    aDataBingmapena// "\"  data-bingmapEnabledAttr=\""
0x27e5c  stelem.ref
0x27e5d  dup
0x27e5e  ldc.i4.3
0x27e5f  ldloca.s 1
0x27e61  call     instance string [mscorlib]System.Boolean::ToString()
0x27e66  stelem.ref
0x27e67  dup
0x27e68  ldc.i4.4
0x27e69  ldstr    asc_319EC// "\">"
0x27e6e  stelem.ref
0x27e6f  call     string [mscorlib]System.String::Concat(string[])
0x27e74  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e79  ldarg.1
0x27e7a  ldstr    aDiv_0// "</div>"
0x27e7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e84  ldarg.1
0x27e85  ldstr    aDiv_0// "</div>"
0x27e8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e8f  ret
```
