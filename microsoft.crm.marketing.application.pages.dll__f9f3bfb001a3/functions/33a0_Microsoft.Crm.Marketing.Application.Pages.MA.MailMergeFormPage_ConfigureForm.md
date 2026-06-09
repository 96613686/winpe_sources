# Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::ConfigureForm

- ea: `0x33a0`
- end: `0x356a`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::ConfigureForm`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3210`
- `0x3230`
- `0x3250`
- `0x3270`
- `0x32c0`
- `0x33a0`
- `0x3570`

## string_xrefs

- `0x34ab`: `MailMerge_Button_Label_ViewOrUpdateColumns`

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarg.0
0x33a1  ldarg.0
0x33a2  ldarg.0
0x33a3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x33a8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x33ad  ldstr    aObjecttypecode_0// "objectTypeCode"
0x33b2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33bc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x33c1  dup
0x33c2  stloc.0
0x33c3  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectTypeCode
0x33c8  ldloc.0
0x33c9  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x33ce  ldarg.0
0x33cf  ldarg.0
0x33d0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x33d5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x33da  ldstr    aObjectid_0// "objectId"
0x33df  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33e4  stfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x33e9  ldarg.0
0x33ea  ldfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x33ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33f4  brtrue.s loc_340D
0x33f6  ldarg.0
0x33f7  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::AdditionalProcessing()
0x33fc  ldarg.0
0x33fd  ldarg.0
0x33fe  ldfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x3403  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3408  stfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x340d  ldarg.0
0x340e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3413  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3418  ldarg.0
0x3419  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x341e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3423  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3428  stfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeName
0x342d  ldarg.0
0x342e  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_GlobalLookup()
0x3433  ldstr    aSingle// "single"
0x3438  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x343d  ldarg.0
0x343e  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_GlobalLookup()
0x3443  ldc.i4.1
0x3444  newarr   [mscorlib]System.Int32
0x3449  dup
0x344a  ldc.i4.0
0x344b  ldc.i4   0x2392
0x3450  stelem.i4
0x3451  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x3456  ldarg.0
0x3457  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_GlobalLookup()
0x345c  ldc.i4   0x2392
0x3461  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32)
0x3466  ldarg.0
0x3467  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_PersonalLookup()
0x346c  ldstr    aSingle// "single"
0x3471  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0x3476  ldarg.0
0x3477  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_PersonalLookup()
0x347c  ldc.i4.1
0x347d  newarr   [mscorlib]System.Int32
0x3482  dup
0x3483  ldc.i4.0
0x3484  ldc.i4   0x2392
0x3489  stelem.i4
0x348a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x348f  ldarg.0
0x3490  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_PersonalLookup()
0x3495  ldc.i4   0x2392
0x349a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32)
0x349f  ldarg.0
0x34a0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_ViewOrUpdateButton()
0x34a5  ldarg.0
0x34a6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x34ab  ldstr    aMailmergeButto_0// "MailMerge_Button_Label_ViewOrUpdateColu"...
0x34b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x34b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Text(string)
0x34ba  ldarg.0
0x34bb  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_MailMerge()
0x34c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x34c5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x34ca  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::set_CanMailMerge(bool value)
0x34cf  ldarg.0
0x34d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x34d5  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ApplicationLanguage::GetProvisionedLanguages(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x34da  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::get_Count()
0x34df  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::languageCount
0x34e4  ldarg.0
0x34e5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x34ea  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x34ef  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::defaultLanguage
0x34f4  ldarg.0
0x34f5  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::languageCount
0x34fa  ldc.i4.1
0x34fb  ble.s    loc_3541
0x34fd  ldarg.0
0x34fe  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_Language()
0x3503  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3508  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x350d  ldc.i4   0x96
0x3512  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3517  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x351c  ldstr    aUilanguageid// "uilanguageid"
0x3521  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x3526  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x352b  ldarg.0
0x352c  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::get_Language()
0x3531  ldarg.0
0x3532  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::defaultLanguage
0x3537  box      [mscorlib]System.Int32
0x353c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x3541  ldarg.0
0x3542  ldarg.0
0x3543  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x3548  ldarg.0
0x3549  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x354e  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.ViewUtility::MailMergeRetrieveEntitiesXml(int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0x3553  stfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::_entitiesXml
0x3558  ldarg.0
0x3559  ldarg.0
0x355a  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x355f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.ViewUtility::MailMergeRetrieveDefaultGridXml(int32)
0x3564  stfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::_defaultGridXml
0x3569  ret
```
