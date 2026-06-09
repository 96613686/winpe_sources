# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::Render

- ea: `0xfaf0`
- end: `0xff10`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::Render`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `broker_com_uri`

## callees

- `0x2c40`
- `0x2c80`
- `0x2ca0`
- `0x2cc0`
- `0x2d20`
- `0x2d80`
- `0x2da0`
- `0x2dc0`
- `0x2de0`
- `0x2e00`
- `0x2e20`
- `0x2e40`
- `0x2e60`
- `0x2e80`
- `0x2f20`
- `0x2f40`
- `0x2f60`
- `0x2f80`
- `0x2fe0`
- `0x8e30`
- `0x8e50`
- `0x8e60`
- `0x91b0`
- `0xf390`
- `0xf490`
- `0xf520`
- `0xf5f0`
- `0xf6b0`
- `0xfaf0`
- `0x10640`

## string_xrefs

- `0xfb23`: `associatedLinkControlId`
- `0xfbca`: `ShowAsBreadcrumbControl`
- `0xfbe9`: `showGlobalQuickCreate`
- `0xfc08`: `openFullForm`

## pseudocode

```c

```

## disassembly

```asm
0xfaf0  ldarg.0
0xfaf1  newobj   instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::.ctor(class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper readFormControl)
0xfaf6  stloc.0
0xfaf7  ldarg.0
0xfaf8  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_InlineViewIds()
0xfafd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfb02  brtrue.s loc_FB15
0xfb04  ldloc.0
0xfb05  ldstr    aInlineviewids// "inlineViewIds"
0xfb0a  ldarg.0
0xfb0b  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_InlineViewIds()
0xfb10  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfb15  ldarg.0
0xfb16  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_AssociatedLinkControlId()
0xfb1b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfb20  brtrue.s loc_FB33
0xfb22  ldloc.0
0xfb23  ldstr    aAssociatedlink// "associatedLinkControlId"
0xfb28  ldarg.0
0xfb29  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_AssociatedLinkControlId()
0xfb2e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfb33  ldloc.0
0xfb34  ldstr    aIsinline// "isInline"
0xfb39  ldstr    aTrue// "true"
0xfb3e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfb43  ldloc.0
0xfb44  ldstr    aLookupstyle// "lookupstyle"
0xfb49  ldarg.0
0xfb4a  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupStyle()
0xfb4f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfb54  ldarg.0
0xfb55  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupBrowse()
0xfb5a  stloc.3
0xfb5b  ldloca.s 3
0xfb5d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xfb62  brfalse.s loc_FB8B
0xfb64  ldloc.0
0xfb65  ldstr    aLookupbrowse// "lookupbrowse"
0xfb6a  ldarg.0
0xfb6b  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupBrowse()
0xfb70  stloc.3
0xfb71  ldloca.s 3
0xfb73  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xfb78  brtrue.s loc_FB81
0xfb7a  ldstr    a0// "0"
0xfb7f  br.s     loc_FB86
0xfb81  ldstr    a1_0// "1"
0xfb86  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfb8b  ldloc.0
0xfb8c  ldstr    aLookupdialogmu// "lookupDialogMultipleSelect"
0xfb91  ldarg.0
0xfb92  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupDialogMultipleSelect()
0xfb97  brtrue.s loc_FBA0
0xfb99  ldstr    a0// "0"
0xfb9e  br.s     loc_FBA5
0xfba0  ldstr    a1_0// "1"
0xfba5  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfbaa  ldloc.0
0xfbab  ldstr    aIsinlinenewena// "isInlineNewEnabled"
0xfbb0  ldarg.0
0xfbb1  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_IsInlineNewEnabled()
0xfbb6  brtrue.s loc_FBBF
0xfbb8  ldstr    a0// "0"
0xfbbd  br.s     loc_FBC4
0xfbbf  ldstr    a1_0// "1"
0xfbc4  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfbc9  ldloc.0
0xfbca  ldstr    aShowasbreadcru// "ShowAsBreadcrumbControl"
0xfbcf  ldarg.0
0xfbd0  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_ShowAsBreadcrumbControl()
0xfbd5  brtrue.s loc_FBDE
0xfbd7  ldstr    a0// "0"
0xfbdc  br.s     loc_FBE3
0xfbde  ldstr    a1_0// "1"
0xfbe3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfbe8  ldloc.0
0xfbe9  ldstr    aShowglobalquic// "showGlobalQuickCreate"
0xfbee  ldarg.0
0xfbef  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_ShowGlobalQuickCreate()
0xfbf4  brtrue.s loc_FBFD
0xfbf6  ldstr    a0// "0"
0xfbfb  br.s     loc_FC02
0xfbfd  ldstr    a1_0// "1"
0xfc02  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc07  ldloc.0
0xfc08  ldstr    aOpenfullform// "openFullForm"
0xfc0d  ldarg.0
0xfc0e  ldfld    bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_openFullForm
0xfc13  brtrue.s loc_FC1C
0xfc15  ldstr    a0// "0"
0xfc1a  br.s     loc_FC21
0xfc1c  ldstr    a1_0// "1"
0xfc21  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc26  ldloc.0
0xfc27  ldstr    aAddlookupimage// "addLookupImageButton"
0xfc2c  ldarg.0
0xfc2d  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_addLookupImageButton
0xfc32  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc37  ldloc.0
0xfc38  ldstr    aRole// "role"
0xfc3d  ldstr    aApplication// "application"
0xfc42  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc47  ldarg.0
0xfc48  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_ShowAsBreadcrumbControl()
0xfc4d  brfalse.s loc_FC71
0xfc4f  ldloc.0
0xfc50  ldstr    aPrimaryfieldna// "primaryfieldname"
0xfc55  ldarg.0
0xfc56  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_PrimaryFieldName()
0xfc5b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc60  ldloc.0
0xfc61  ldstr    aPrimarykeyname// "primarykeyname"
0xfc66  ldarg.0
0xfc67  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_PrimaryKeyName()
0xfc6c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfc71  ldsfld   string [mscorlib]System.String::Empty
0xfc76  stloc.1
0xfc77  ldsfld   string [mscorlib]System.String::Empty
0xfc7c  stloc.2
0xfc7d  ldarg.0
0xfc7e  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_EntityLogicalName()
0xfc83  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfc88  brtrue.s loc_FCE3
0xfc8a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfc8f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfc94  ldarg.0
0xfc95  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_EntityLogicalName()
0xfc9a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfc9f  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xfca4  ldc.i4.1
0xfca5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xfcaa  dup
0xfcab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xfcb0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xfcb5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xfcba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfcbf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfcc4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xfcc9  stloc.1
0xfcca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xfccf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0xfcd4  stloc.s  4
0xfcd6  ldloca.s 4
0xfcd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfcdd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xfce2  stloc.2
0xfce3  ldloc.0
0xfce4  ldstr    aEntitylogicaln// "entityLogicalName"
0xfce9  ldarg.0
0xfcea  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_EntityLogicalName()
0xfcef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfcf4  brtrue.s loc_FCFE
0xfcf6  ldarg.0
0xfcf7  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_EntityLogicalName()
0xfcfc  br.s     loc_FD03
0xfcfe  ldsfld   string [mscorlib]System.String::Empty
0xfd03  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd08  ldloc.0
0xfd09  ldstr    aEntitydisplayn// "entityDisplayName"
0xfd0e  ldloc.1
0xfd0f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd14  ldloc.0
0xfd15  ldstr    aEntitytypecode// "entityTypeCode"
0xfd1a  ldloc.2
0xfd1b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd20  ldloc.0
0xfd21  ldstr    aAllowfilteroff// "allowFilterOff"
0xfd26  ldarg.0
0xfd27  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_AllowFilterOff()
0xfd2c  brtrue.s loc_FD35
0xfd2e  ldstr    a0// "0"
0xfd33  br.s     loc_FD3A
0xfd35  ldstr    a1_0// "1"
0xfd3a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd3f  ldloc.0
0xfd40  ldstr    aDisablequickfi// "disableQuickFind"
0xfd45  ldarg.0
0xfd46  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DisableQuickFind()
0xfd4b  brtrue.s loc_FD54
0xfd4d  ldstr    a0// "0"
0xfd52  br.s     loc_FD59
0xfd54  ldstr    a1_0// "1"
0xfd59  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd5e  ldloc.0
0xfd5f  ldstr    aDisableviewpic// "disableViewPicker"
0xfd64  ldarg.0
0xfd65  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DisableViewPicker()
0xfd6a  brtrue.s loc_FD73
0xfd6c  ldstr    a0// "0"
0xfd71  br.s     loc_FD78
0xfd73  ldstr    a1_0// "1"
0xfd78  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd7d  ldloc.0
0xfd7e  ldstr    aDisablemru// "disableMru"
0xfd83  ldarg.0
0xfd84  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DisableMru()
0xfd89  brtrue.s loc_FD92
0xfd8b  ldstr    a0// "0"
0xfd90  br.s     loc_FD97
0xfd92  ldstr    a1_0// "1"
0xfd97  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfd9c  ldloc.0
0xfd9d  ldstr    aIsdeduplookup// "isDeDupLookup"
0xfda2  ldarg.0
0xfda3  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_IsDeDupLookup()
0xfda8  brtrue.s loc_FDB1
0xfdaa  ldstr    a0// "0"
0xfdaf  br.s     loc_FDB6
0xfdb1  ldstr    a1_0// "1"
0xfdb6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfdbb  ldloc.0
0xfdbc  ldstr    aAvailableviewi// "availableViewIds"
0xfdc1  ldarg.0
0xfdc2  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_AvailableViewIds()
0xfdc7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfdcc  ldloc.0
0xfdcd  ldstr    aResolveemailad// "resolveEmailAddress"
0xfdd2  ldarg.0
0xfdd3  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_ResolveEmailAddress()
0xfdd8  brtrue.s loc_FDE1
0xfdda  ldstr    a0// "0"
0xfddf  br.s     loc_FDE6
0xfde1  ldstr    a1_0// "1"
0xfde6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfdeb  ldloc.0
0xfdec  ldstr    aAllowunresolve// "allowUnresolvedPartiesOnEmailSend"
0xfdf1  ldarg.0
0xfdf2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::get_OrganizationContext()
0xfdf7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfdfc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsUnresolvedPartiesOnEmailSendAllowed()
0xfe01  brtrue.s loc_FE0A
0xfe03  ldstr    a0// "0"
0xfe08  br.s     loc_FE0F
0xfe0a  ldstr    a1_0// "1"
0xfe0f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfe14  ldarg.0
0xfe15  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DefaultViewId()
0xfe1a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfe1f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xfe24  brfalse.s loc_FE2C
0xfe26  ldarg.0
0xfe27  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetDefaultViewId()
0xfe2c  ldarg.0
0xfe2d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DefaultViewId()
0xfe32  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfe37  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xfe3c  brfalse.s loc_FE54
0xfe3e  ldloc.0
0xfe3f  ldstr    aDefaultviewid// "DefaultViewId"
0xfe44  ldarg.0
0xfe45  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DefaultViewId()
0xfe4a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xfe4f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfe54  ldarg.0
0xfe55  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_FilterRelationshipName()
0xfe5a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfe5f  brtrue.s loc_FECB
0xfe61  ldarg.0
0xfe62  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DependentAttributeName()
0xfe67  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfe6c  brtrue.s loc_FECB
0xfe6e  ldarg.0
0xfe6f  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DependentAttributeType()
0xfe74  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfe79  brtrue.s loc_FECB
0xfe7b  ldloc.0
0xfe7c  ldstr    aRelationshipid// "RelationshipId"
0xfe81  ldarg.0
0xfe82  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_FilterRelationshipName()
0xfe87  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfe8c  ldloc.0
0xfe8d  ldstr    aDependantattri// "DependantAttributeName"
0xfe92  ldarg.0
0xfe93  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DependentAttributeName()
0xfe98  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfe9d  ldloc.0
0xfe9e  ldstr    aDependantattri_0// "DependantAttributeType"
0xfea3  ldarg.0
0xfea4  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_DependentAttributeType()
0xfea9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfeae  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfeb3  call     instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xfeb8  stloc.s  4
0xfeba  ldloca.s 4
0xfebc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfec1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xfec6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xfecb  ldloc.0
0xfecc  ldarg.1
0xfecd  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::BeginRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xfed2  ldarg.0
0xfed3  ldarg.1
0xfed4  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xfed9  ldloc.0
0xfeda  ldarg.1
0xfedb  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::EndRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xfee0  ldarg.0
0xfee1  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_EntityLogicalName()
0xfee6  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xfeeb  brtrue.s loc_FF0F
  ... truncated ...
```
