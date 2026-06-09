# Microsoft.Crm.Controls.Header::.ctor_0

- ea: `0x6c40`
- end: `0x6e31`
- name: `Microsoft.Crm.Controls.Header::.ctor_0`
- size: `497`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6c30`
- `0x85b0`

## callees

- `0x23b0`
- `0x2630`
- `0x2ef0`
- `0x3380`
- `0x33d0`
- `0x3790`
- `0x38d0`
- `0x39f0`
- `0x40f0`
- `0x6c40`
- `0x6e40`
- `0x6fd0`

## string_xrefs

- `0x6d34`: `/_common/global.ashx`
- `0x6c82`: `/_common/styles/fonts.css.aspx`
- `0x6c8d`: `/_common/styles/global.css.aspx`
- `0x6ca8`: `/_common/styles/theme.css.aspx?{0}={1}`
- `0x6d1e`: `THEME_UPDATE_TIMESTAMP`
- `0x6d24`: `updateTimeStamp`
- `0x6d50`: `/_static/_common/scripts/OutlookInterop.js`
- `0x6d5a`: `/_common/windowinformation/windowinformation.js.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x6c40  ldarg.0
0x6c41  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6c46  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.Header::_metaTags
0x6c4b  ldarg.0
0x6c4c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Controls.Header>::.ctor()
0x6c51  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Controls.Header> Microsoft.Crm.Controls.Header::controlHeaderList
0x6c56  ldarg.0
0x6c57  call     instance void Microsoft.Crm.Controls.PageResourceManager::.ctor()
0x6c5c  ldarg.1
0x6c5d  brfalse.s loc_6C6E
0x6c5f  ldarg.0
0x6c60  ldarg.1
0x6c61  stfld    bool Microsoft.Crm.Controls.Header::_isControlHeader
0x6c66  ldarg.0
0x6c67  ldc.i4.0
0x6c68  call     instance void Microsoft.Crm.Controls.Header::set_DeferAllScripts(bool value)
0x6c6d  ret
0x6c6e  ldarg.0
0x6c6f  ldc.i4.1
0x6c70  call     instance void Microsoft.Crm.Controls.PageResourceManager::set_UsePageLoader(bool value)
0x6c75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6c7a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsHierarchyPage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6c7f  brtrue.s loc_6C8C
0x6c81  ldarg.0
0x6c82  ldstr    aCommonStylesFo// "/_common/styles/fonts.css.aspx"
0x6c87  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x6c8c  ldarg.0
0x6c8d  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x6c92  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x6c97  ldarg.0
0x6c98  call     instance bool Microsoft.Crm.Controls.Header::get_IsLayoutPage()
0x6c9d  brtrue   loc_6D33
0x6ca2  ldarg.0
0x6ca3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ca8  ldstr    aCommonStylesTh// "/_common/styles/theme.css.aspx?{0}={1}"
0x6cad  ldc.i4.2
0x6cae  newarr   [mscorlib]System.Object
0x6cb3  dup
0x6cb4  ldc.i4.0
0x6cb5  ldstr    aLcid// "lcid"
0x6cba  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x6cbf  stelem.ref
0x6cc0  dup
0x6cc1  ldc.i4.1
0x6cc2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x6cc7  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x6ccc  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x6cd1  brtrue.s loc_6CDA
0x6cd3  ldstr    aLtr// "ltr"
0x6cd8  br.s     loc_6CDF
0x6cda  ldstr    aRtl// "rtl"
0x6cdf  stelem.ref
0x6ce0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6ce5  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x6cea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6cef  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_IsUserAuthenticated()
0x6cf4  brfalse.s loc_6D01
0x6cf6  ldarg.0
0x6cf7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleSheetUrl()
0x6cfc  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x6d01  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleParameters()
0x6d06  stloc.0
0x6d07  ldarg.0
0x6d08  ldstr    aThemeId// "THEME_ID"
0x6d0d  ldloc.0
0x6d0e  ldstr    aThemeid// "themeId"
0x6d13  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x6d18  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x6d1d  ldarg.0
0x6d1e  ldstr    aThemeUpdateTim// "THEME_UPDATE_TIMESTAMP"
0x6d23  ldloc.0
0x6d24  ldstr    aUpdatetimestam// "updateTimeStamp"
0x6d29  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x6d2e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x6d33  ldarg.0
0x6d34  ldstr    aCommonGlobalAs_0// "/_common/global.ashx"
0x6d39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6d3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6d43  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddObjectTag(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri file)
0x6d48  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x6d4d  brfalse.s loc_6D78
0x6d4f  ldarg.0
0x6d50  ldstr    aStaticCommonSc_18// "/_static/_common/scripts/OutlookInterop"...
0x6d55  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x6d5a  ldstr    aCommonWindowin// "/_common/windowinformation/windowinform"...
0x6d5f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6d64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6d69  stloc.1
0x6d6a  ldloc.1
0x6d6b  ldc.i4.1
0x6d6c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseCssLcid(bool)
0x6d71  ldarg.0
0x6d72  ldloc.1
0x6d73  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri file)
0x6d78  ldarg.0
0x6d79  ldstr    aLocidIpadwincl// "LOCID_IPADWINCLOSED"
0x6d7e  ldarg.0
0x6d7f  ldstr    aWebIpadErrorPa// "Web.ipad.error.parentWindowClosed"
0x6d84  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6d89  ldc.i4.0
0x6d8a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6d8f  ldarg.0
0x6d90  ldstr    aLocidPublishMe// "LOCID_PUBLISH_MESSAGE_SINGLE"
0x6d95  ldarg.0
0x6d96  ldstr    aMessagePublish// "Message_Publish_Record"
0x6d9b  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6da0  ldc.i4.0
0x6da1  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6da6  ldarg.0
0x6da7  ldstr    aLocidPublishMe_0// "LOCID_PUBLISH_MESSAGE_MULTIPLE"
0x6dac  ldarg.0
0x6dad  ldstr    aMessagePublish_0// "Message_Publish_Records"
0x6db2  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6db7  ldc.i4.0
0x6db8  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6dbd  ldarg.0
0x6dbe  ldstr    aLocidMessageUs// "LOCID_MESSAGE_USER_MULTI_PROFILE"
0x6dc3  ldarg.0
0x6dc4  ldstr    aDlgUserAssocia// "Dlg_User_Association_to_Multiple_Profil"...
0x6dc9  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6dce  ldc.i4.0
0x6dcf  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6dd4  ldarg.0
0x6dd5  ldstr    aLocidTitleUser// "LOCID_TITLE_USER_MULTI_PROFILE"
0x6dda  ldarg.0
0x6ddb  ldstr    aDlgUserAssocia_0// "Dlg_User_Association_to_Profile_Title"
0x6de0  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6de5  ldc.i4.0
0x6de6  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6deb  ldarg.0
0x6dec  ldstr    aLocidCloneMess// "LOCID_CLONE_MESSAGE"
0x6df1  ldarg.0
0x6df2  ldstr    aDialogClonemob// "Dialog_CloneMobileOfflineProfile_Descri"...
0x6df7  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6dfc  ldc.i4.0
0x6dfd  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6e02  ldarg.0
0x6e03  ldstr    aLocidCloneTitl// "LOCID_CLONE_TITLE"
0x6e08  ldarg.0
0x6e09  ldstr    aDialogClonemob_0// "Dialog_CloneMobileOfflineProfile_Title"
0x6e0e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6e13  ldc.i4.0
0x6e14  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6e19  ldarg.0
0x6e1a  ldstr    aLocidAnalyzeMe// "LOCID_ANALYZE_MESSAGE"
0x6e1f  ldarg.0
0x6e20  ldstr    aMscrmFormMobil// "Mscrm.Form.mobileofflineprofile.MainTab"...
0x6e25  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x6e2a  ldc.i4.0
0x6e2b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x6e30  ret
```
