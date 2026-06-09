# Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::InitializeResolveToControls

- ea: `0xf2f0`
- end: `0xf48c`
- name: `Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::InitializeResolveToControls`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf200`

## callees

- `0xf2f0`
- `0xf490`

## pseudocode

```c

```

## disassembly

```asm
0xf2f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf2f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf2fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf2ff  stloc.0
0xf300  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xf305  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf30a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf30f  ldloc.0
0xf310  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xf315  stloc.1
0xf316  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xf31b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xf320  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SSSReliability()
0xf325  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf32a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf32f  brfalse.s loc_F339
0xf331  ldloc.1
0xf332  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_UnresolveEmailAddressIfMultipleMatch()
0xf337  br.s     loc_F33A
0xf339  ldc.i4.0
0xf33a  stloc.2
0xf33b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0xf340  stloc.3
0xf341  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf346  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf34b  ldstr    aEmail// "email"
0xf350  ldc.i4.1
0xf351  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xf356  ldstr    aTo// "to"
0xf35b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xf360  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xf365  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xf36a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::GetEnumerator()
0xf36f  stloc.s  4
0xf371  br       loc_F40C
0xf376  ldloc.s  4
0xf378  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0xf37d  stloc.s  5
0xf37f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf384  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf389  ldloc.s  5
0xf38b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf390  stloc.s  6
0xf392  ldloc.s  6
0xf394  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivityParty()
0xf399  brfalse.s loc_F40C
0xf39b  ldloc.s  6
0xf39d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasEmailAddresses()
0xf3a2  brfalse.s loc_F40C
0xf3a4  ldloc.s  5
0xf3a6  ldc.i4   0x7DC
0xf3ab  beq.s    loc_F40C
0xf3ad  ldloc.s  6
0xf3af  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf3b4  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::IsEntityListedForEmailDisabled(string)
0xf3b9  brtrue.s loc_F40C
0xf3bb  ldloc.3
0xf3bc  ldloc.s  5
0xf3be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0xf3c3  ldloc.s  5
0xf3c5  ldc.i4.8
0xf3c6  beq.s    loc_F40C
0xf3c8  newobj   instance void [System]System.Collections.Specialized.ListDictionary::.ctor()
0xf3cd  stloc.s  7
0xf3cf  ldloc.s  7
0xf3d1  ldstr    aPrimaryemail// "primaryemail"
0xf3d6  ldloc.s  6
0xf3d8  call     string Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::GetPrimaryEmailAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0xf3dd  callvirt instance void [System]System.Collections.Specialized.ListDictionary::Add(object, object)
0xf3e2  ldloc.s  5
0xf3e4  ldc.i4.1
0xf3e5  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xf3ea  stloc.s  8
0xf3ec  ldarg.0
0xf3ed  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::selectQuickCreate
0xf3f2  ldloc.s  8
0xf3f4  ldloca.s 5
0xf3f6  ldstr    aD// "D"
0xf3fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf400  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xf405  ldloc.s  7
0xf407  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string, class [System]System.Collections.Specialized.ListDictionary)
0xf40c  ldloc.s  4
0xf40e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf413  brtrue   loc_F376
0xf418  leave.s  loc_F426
0xf41a  ldloc.s  4
0xf41c  brfalse.s loc_F425
0xf41e  ldloc.s  4
0xf420  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf425  endfinally
0xf426  ldarg.0
0xf427  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::crmExistingLookup
0xf42c  ldloc.3
0xf42d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int32>::ToArray()
0xf432  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xf437  ldarg.0
0xf438  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::selectQuickCreate
0xf43d  ldc.i4.2
0xf43e  stloc.s  9
0xf440  ldloca.s 9
0xf442  ldstr    aD// "D"
0xf447  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf44c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xf451  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0xf456  ldarg.0
0xf457  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::crmExistingLookup
0xf45c  ldc.i4.2
0xf45d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32)
0xf462  ldloc.2
0xf463  brfalse.s loc_F48B
0xf465  ldarg.0
0xf466  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::crmExistingLookup
0xf46b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_Items()
0xf470  ldarg.0
0xf471  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::txtName
0xf476  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0xf47b  ldarg.0
0xf47c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Common.Web.Controls.PartyList.PartyListResolvePage::txtName
0xf481  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0xf486  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection::Add(string, string)
0xf48b  ret
```
