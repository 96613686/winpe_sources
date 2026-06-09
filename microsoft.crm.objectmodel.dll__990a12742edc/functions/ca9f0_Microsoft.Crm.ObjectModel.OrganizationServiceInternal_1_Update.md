# Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1::Update

- ea: `0xca9f0`
- end: `0xcb99d`
- name: `Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1::Update`
- size: `4013`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x15bc0`
- `0x15be0`
- `0x5e780`
- `0x5e790`
- `0x700b0`
- `0x731b0`
- `0x73260`
- `0x732e0`
- `0x73350`
- `0x83720`
- `0x862b0`
- `0x862d0`
- `0x862e0`
- `0x86340`
- `0xca9f0`
- `0x12ec50`
- `0x131310`
- `0x131380`
- `0x131430`
- `0x131460`
- `0x17dd60`
- `0x17f840`
- `0x1d0940`
- `0x1d0eb0`
- `0x1f4750`
- `0x208a40`
- `0x208db0`
- `0x20de20`
- `0x20e210`

## string_xrefs

- `0xcae6e`: `Update`
- `0xcaef1`: `Update`
- `0xcaf74`: `Update`
- `0xcab8d`: `maxdepthforhierarchicalsecuritymodel`
- `0xcab9a`: `maxdepthforhierarchicalsecuritymodel`
- `0xcabbb`: `MaxDepthforHierarchicalSecuritymodel value cannot be less than {0} or greater than {1}`
- `0xcae73`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationService.cs`
- `0xcaef6`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationService.cs`
- `0xcaf79`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationService.cs`
- `0xcb13f`: `Unable to update Organization Setting for isactioncardenabled. Value for isRelationshipInsightsEnabled: {0}, isRASolutionInstalled: {1}`
- `0xcb15c`: `Relationship Insights feature is not enabled or solution is not installed.`
- `0xcb315`: `Relationship Insights feature is not enabled or solution is not installed.`
- `0xcb602`: `Relationship Insights feature is not enabled or solution is not installed.`
- `0xcb187`: `OrganizationServiceInternal.Update`
- `0xcb622`: `OrganizationServiceInternal.Update`
- `0xcb653`: `OrganizationServiceInternal.Update`
- `0xcb240`: `OrganizationService.Update`
- `0xcb26f`: `OrganizationService.Update`
- `0xcb297`: `OrganizationService.Update`
- `0xcb4e9`: `OrganizationService.Update`
- `0xcb549`: `OrganizationService.Update`
- `0xcb5a1`: `OrganizationService.Update`
- `0xcb3d6`: `Relationship Analytics organization settings can be enabled only if Relationship Analytics solution is installed`
- `0xcb3ed`: `msdyn_activityanalysisconfig`
- `0xcb401`: `msdyn_activityanalysisconfigid`
- `0xcb518`: `OrganizationService.Update - using Graph Api`
- `0xcb53e`: `S2SNotConfigured`
- `0xcb579`: `OrganizationService.Update - using SharePoint`
- `0xcb6a2`: `This operation couldn�t be completed because featureSet xml is invalid`
- `0xcb6ec`: `This operation couldn't be completed because one of the domains is not valid`

## pseudocode

```c

```

## disassembly

```asm
0xca9f0  ldarg.1
0xca9f1  ldstr    aOrganization_0// "organization"
0xca9f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xca9fb  ldarg.2
0xca9fc  ldstr    aContext// "context"
0xcaa01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcaa06  ldarg.0
0xcaa07  ldarg.1
0xcaa08  call     instance bool class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::TokenSettingsUpdated(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xcaa0d  brfalse.s loc_CAA26
0xcaa0f  ldarg.0
0xcaa10  ldarg.1
0xcaa11  ldstr    aOrganizationid_1// "organizationid"
0xcaa16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcaa1b  unbox.any [mscorlib]System.Guid
0xcaa20  ldarg.2
0xcaa21  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::CheckAdminRights(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcaa26  ldarg.0
0xcaa27  ldarg.1
0xcaa28  ldarg.2
0xcaa29  call     instance bool class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::IsEnforceReadOnlyPluginsUpdatedToEnabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcaa2e  brfalse.s loc_CAA37
0xcaa30  ldarg.0
0xcaa31  ldarg.2
0xcaa32  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::CheckForIncompatibleSteps(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcaa37  ldarg.0
0xcaa38  ldarg.1
0xcaa39  call     instance bool class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::OrgDBOrgSettingsUpdated(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xcaa3e  brfalse.s loc_CAA77
0xcaa40  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xcaa45  brfalse.s loc_CAA58
0xcaa47  ldc.i4   0x80048515
0xcaa4c  ldc.i4.0
0xcaa4d  newarr   [mscorlib]System.Object
0xcaa52  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcaa57  throw
0xcaa58  ldarg.0
0xcaa59  ldarg.1
0xcaa5a  ldstr    aOrganizationid_1// "organizationid"
0xcaa5f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcaa64  unbox.any [mscorlib]System.Guid
0xcaa69  ldarg.2
0xcaa6a  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::CheckAdminRights(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcaa6f  ldarg.0
0xcaa70  ldarg.1
0xcaa71  ldarg.2
0xcaa72  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::ValidateAndGetUpdateXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcaa77  ldnull
0xcaa78  stloc.0
0xcaa79  ldnull
0xcaa7a  stloc.1
0xcaa7b  ldnull
0xcaa7c  stloc.2
0xcaa7d  ldarg.2
0xcaa7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xcaa83  stloc.3
0xcaa84  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xcaa89  ldloc.3
0xcaa8a  ldarg.2
0xcaa8b  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xcaa90  stloc.s  4
0xcaa92  ldloc.s  4
0xcaa94  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsElasticsearchEnabled()
0xcaa99  stloc.s  5
0xcaa9b  ldarg.1
0xcaa9c  ldarg.2
0xcaa9d  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchOptInService::GetNewExternalSearchEnabledFlag(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity organization, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcaaa2  stloc.s  6
0xcaaa4  ldloc.s  4
0xcaaa6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsExternalFileStorageEnabled()
0xcaaab  stloc.s  7
0xcaaad  ldarg.1
0xcaaae  ldloc.s  7
0xcaab0  ldarg.2
0xcaab1  call     valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.ObjectModel.ExternalFileStorage.ExternalFileStorageOptInService::GetNewExternalFileStorageEnabledFlag(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity organization, bool cachedExternalFileStorageEnabled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcaab6  stloc.s  8
0xcaab8  ldloc.s  4
0xcaaba  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LocaleId()
0xcaabf  stloc.s  9
0xcaac1  ldc.i4.0
0xcaac2  stloc.s  0xA
0xcaac4  ldarg.1
0xcaac5  ldstr    aLocaleid// "localeid"
0xcaaca  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcaacf  brtrue.s loc_CAB02
0xcaad1  ldarg.1
0xcaad2  ldstr    aLocaleid// "localeid"
0xcaad7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcaadc  unbox.any [mscorlib]System.Int32
0xcaae1  ldloc.s  9
0xcaae3  beq.s    loc_CAB02
0xcaae5  ldarg.1
0xcaae6  ldstr    aLocaleid// "localeid"
0xcaaeb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcaaf0  unbox.any [mscorlib]System.Int32
0xcaaf5  stloc.s  9
0xcaaf7  ldarg.1
0xcaaf8  ldloc.s  9
0xcaafa  call     void Microsoft.Crm.ObjectModel.SettingsValidator::PopulateNullFieldsWithLocaleDefaults(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 lcid)
0xcaaff  ldc.i4.1
0xcab00  stloc.s  0xA
0xcab02  ldarg.0
0xcab03  ldarg.1
0xcab04  ldarg.2
0xcab05  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::HandleFiscalCalendarStartDate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcab0a  ldarg.1
0xcab0b  ldstr    aIsduplicatedet// "isduplicatedetectionenabled"
0xcab10  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcab15  brtrue.s loc_CAB29
0xcab17  ldarg.1
0xcab18  ldstr    aIsduplicatedet// "isduplicatedetectionenabled"
0xcab1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcab22  unbox.any [mscorlib]System.Boolean
0xcab27  br.s     loc_CAB2A
0xcab29  ldc.i4.0
0xcab2a  brfalse.s loc_CAB8C
0xcab2c  ldloc.2
0xcab2d  brtrue.s loc_CAB73
0xcab2f  ldarg.1
0xcab30  ldstr    aOrganizationid_1// "organizationid"
0xcab35  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcab3a  unbox.any [mscorlib]System.Guid
0xcab3f  ldarg.0
0xcab40  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xcab45  ldarg.2
0xcab46  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcab4b  stloc.0
0xcab4c  ldarg.0
0xcab4d  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xcab52  ldarg.2
0xcab53  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xcab58  stloc.1
0xcab59  ldloc.1
0xcab5a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xcab5f  ldstr    aIsduplicatedet// "isduplicatedetectionenabled"
0xcab64  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcab69  ldarg.0
0xcab6a  ldloc.0
0xcab6b  ldloc.1
0xcab6c  ldarg.2
0xcab6d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcab72  stloc.2
0xcab73  ldloc.2
0xcab74  ldstr    aIsduplicatedet// "isduplicatedetectionenabled"
0xcab79  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcab7e  unbox.any [mscorlib]System.Boolean
0xcab83  brtrue.s loc_CAB8C
0xcab85  ldarg.0
0xcab86  ldarg.2
0xcab87  call     instance void class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::EnsureNoPublishedOrPublishingRules(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcab8c  ldarg.1
0xcab8d  ldstr    aMaxdepthforhie// "maxdepthforhierarchicalsecuritymodel"
0xcab92  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcab97  brtrue.s loc_CABE4
0xcab99  ldarg.1
0xcab9a  ldstr    aMaxdepthforhie// "maxdepthforhierarchicalsecuritymodel"
0xcab9f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcaba4  unbox.any [mscorlib]System.Int32
0xcaba9  stloc.s  0xC
0xcabab  ldloc.s  0xC
0xcabad  ldc.i4.0
0xcabae  blt.s    loc_CABB6
0xcabb0  ldloc.s  0xC
0xcabb2  ldc.i4.s 0x64
0xcabb4  ble.s    loc_CABE4
0xcabb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcabbb  ldstr    aMaxdepthforhie_0// "MaxDepthforHierarchicalSecuritymodel va"...
0xcabc0  ldc.i4.2
0xcabc1  newarr   [mscorlib]System.Object
0xcabc6  dup
0xcabc7  ldc.i4.0
0xcabc8  ldc.i4.0
0xcabc9  box      [mscorlib]System.Int32
0xcabce  stelem.ref
0xcabcf  dup
0xcabd0  ldc.i4.1
0xcabd1  ldc.i4.s 0x64
0xcabd3  box      [mscorlib]System.Int32
0xcabd8  stelem.ref
0xcabd9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcabde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xcabe3  throw
0xcabe4  ldarg.1
0xcabe5  ldstr    aNumbergroupfor// "numbergroupformat"
0xcabea  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcabef  brtrue.s loc_CAC1F
0xcabf1  ldarg.0
0xcabf2  ldfld    class [System]System.Text.RegularExpressions.Regex class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<var<u1>>::_intergerRegex
0xcabf7  ldarg.1
0xcabf8  ldstr    aNumbergroupfor// "numbergroupformat"
0xcabfd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcac02  castclass [mscorlib]System.String
0xcac07  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0xcac0c  brtrue.s loc_CAC1F
0xcac0e  ldc.i4   0x80043700
0xcac13  ldc.i4.0
0xcac14  newarr   [mscorlib]System.Object
0xcac19  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcac1e  throw
0xcac1f  ldloc.s  9
0xcac21  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0xcac26  stloc.s  0xB
0xcac28  ldarg.1
0xcac29  ldstr    aDateformatcode// "dateformatcode"
0xcac2e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcac33  ldc.i4.0
0xcac34  ceq
0xcac36  ldloc.s  0xA
0xcac38  or
0xcac39  brfalse  loc_CACC8
0xcac3e  ldc.i4.5
0xcac3f  ldloc.s  0xB
0xcac41  ldloca.s 0xD
0xcac43  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleValues::GetAllDateFormats(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleSetting, class [mscorlib]System.Globalization.CultureInfo, int32&)
0xcac48  stloc.s  0xE
0xcac4a  ldarg.1
0xcac4b  ldstr    aDateformatcode// "dateformatcode"
0xcac50  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcac55  brfalse.s loc_CAC70
0xcac57  ldc.i4.5
0xcac58  ldloc.s  0xB
0xcac5a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xcac5f  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleValues::GetDefaultLocaleValue(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleSetting, int32)
0xcac64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcac69  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xcac6e  br.s     loc_CAC80
0xcac70  ldarg.1
0xcac71  ldstr    aDateformatcode// "dateformatcode"
0xcac76  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcac7b  unbox.any [mscorlib]System.Int32
0xcac80  stloc.s  0xF
0xcac82  ldloc.s  0xE
0xcac84  ldloc.s  0xF
0xcac86  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0xcac8b  brfalse.s loc_CACA3
0xcac8d  ldarg.1
0xcac8e  ldstr    aDateformatstri// "dateformatstring"
0xcac93  ldloc.s  0xE
0xcac95  ldloc.s  0xF
0xcac97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0xcac9c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcaca1  br.s     loc_CACC8
0xcaca3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcaca8  ldstr    aUnknownDateFor// "Unknown date format code specified: ({0"...
0xcacad  ldc.i4.1
0xcacae  newarr   [mscorlib]System.Object
0xcacb3  dup
0xcacb4  ldc.i4.0
0xcacb5  ldloc.s  0xF
0xcacb7  box      [mscorlib]System.Int32
0xcacbc  stelem.ref
0xcacbd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcacc2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xcacc7  throw
0xcacc8  ldarg.1
0xcacc9  ldstr    aTimeformatcode// "timeformatcode"
0xcacce  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcacd3  ldc.i4.0
0xcacd4  ceq
0xcacd6  ldloc.s  0xA
0xcacd8  or
0xcacd9  brfalse  loc_CADB6
0xcacde  ldloc.s  0xB
0xcace0  ldloca.s 0x10
0xcace2  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleValues::GetAllTimeFormats(class [mscorlib]System.Globalization.CultureInfo, int32&)
0xcace7  stloc.s  0x11
0xcace9  ldarg.1
0xcacea  ldstr    aTimeformatcode// "timeformatcode"
0xcacef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcacf4  brfalse.s loc_CAD0F
0xcacf6  ldc.i4.4
0xcacf7  ldloc.s  0xB
0xcacf9  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xcacfe  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleValues::GetDefaultLocaleValue(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleSetting, int32)
0xcad03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcad08  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xcad0d  br.s     loc_CAD1F
0xcad0f  ldarg.1
0xcad10  ldstr    aTimeformatcode// "timeformatcode"
0xcad15  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcad1a  unbox.any [mscorlib]System.Int32
0xcad1f  stloc.s  0x12
0xcad21  ldloc.s  0xA
0xcad23  brfalse.s loc_CAD3A
0xcad25  ldarg.1
0xcad26  ldstr    aTimeformatstri// "timeformatstring"
0xcad2b  ldloc.s  0x11
0xcad2d  ldc.i4.0
0xcad2e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0xcad33  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcad38  br.s     loc_CADB6
0xcad3a  ldloc.s  0x11
0xcad3c  ldloc.s  0x12
0xcad3e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0xcad43  brfalse.s loc_CAD91
0xcad45  ldarg.1
0xcad46  ldstr    aTimeformatstri// "timeformatstring"
0xcad4b  ldloc.s  0x11
0xcad4d  ldloc.s  0x12
0xcad4f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
  ... truncated ...
```
