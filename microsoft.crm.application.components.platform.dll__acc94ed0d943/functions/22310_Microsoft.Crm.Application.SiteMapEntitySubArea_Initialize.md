# Microsoft.Crm.Application.SiteMapEntitySubArea::Initialize

- ea: `0x22310`
- end: `0x22526`
- name: `Microsoft.Crm.Application.SiteMapEntitySubArea::Initialize`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x22230`

## callees

- `0x6a70`
- `0x11760`
- `0x22310`
- `0x22530`
- `0x24c10`
- `0x24c70`
- `0x25020`
- `0x25030`
- `0x25050`
- `0x25060`
- `0x250a0`
- `0x250d0`
- `0x25dc0`
- `0x260b0`
- `0x2fb90`
- `0x2fbc0`
- `0x30260`
- `0x39f50`
- `0x3aa00`

## string_xrefs

- `0x223b8`: `Flushed the LabelCache and MetadataCache as title was not found for Entity: {0}`
- `0x22440`: `Title was not found for Entity: {0} , set default value. IsCacheSharingEnabled:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x22310  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x22315  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2231a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2231f  stloc.0
0x22320  ldarg.0
0x22321  ldarg.1
0x22322  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x22327  ldarg.0
0x22328  call     instance class Microsoft.Crm.Application.PrivilegeIdDictionary Microsoft.Crm.Application.MasterSiteMapSubArea::get_Privileges()
0x2232d  ldarg.0
0x2232e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x22333  ldc.i4.1
0x22334  callvirt instance void Microsoft.Crm.Application.PrivilegeIdDictionary::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, valuetype Microsoft.Crm.Application.Types.PrivilegeId value)
0x22339  ldarg.0
0x2233a  ldarg.0
0x2233b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x22340  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x22345  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetEntityName(string entityName)
0x2234a  ldarg.2
0x2234b  brfalse  loc_2246E
0x22350  ldarg.0
0x22351  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x22356  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedCollectionName()
0x2235b  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x22360  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x22365  ldloc.0
0x22366  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2236b  stloc.1
0x2236c  ldloc.1
0x2236d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22372  brfalse  loc_22467
0x22377  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0x2237c  ldloc.0
0x2237d  ldc.i4.1
0x2237e  ldc.i4.0
0x2237f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool, bool)
0x22384  ldloc.0
0x22385  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2238a  ldarg.0
0x2238b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x22390  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedCollectionName()
0x22395  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2239a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2239f  ldloc.0
0x223a0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x223a5  stloc.1
0x223a6  ldstr    aTitle_0// "title"
0x223ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x223b0  ldloc.0
0x223b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x223b6  ldc.i4.s 0x14
0x223b8  ldstr    aFlushedTheLabe// "Flushed the LabelCache and MetadataCach"...
0x223bd  ldc.i4.1
0x223be  newarr   [mscorlib]System.Object
0x223c3  dup
0x223c4  ldc.i4.0
0x223c5  ldarg.0
0x223c6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x223cb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x223d0  stelem.ref
0x223d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x223d6  ldloc.1
0x223d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x223dc  brfalse  loc_22467
0x223e1  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x223e6  ldstr    aDependencyType// "Dependency_Type_Unknown"
0x223eb  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x223f0  stloc.1
0x223f1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCache::Instance()
0x223f6  ldloc.0
0x223f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x223fc  ldloc.0
0x223fd  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData>>::LookupEntry(void, var<u1>)
0x22402  stloc.2
0x22403  ldloc.2
0x22404  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x22409  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2240e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData>::ContainsKey(var<u1>)
0x22413  brtrue.s loc_22418
0x22415  ldc.i4.0
0x22416  br.s     loc_2242D
0x22418  ldloc.2
0x22419  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2241e  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x22423  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData>::get_Item(void)
0x22428  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData::get_IsCacheSharingEnabled()
0x2242d  stloc.3
0x2242e  ldstr    aTitle_0// "title"
0x22433  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22438  ldloc.0
0x22439  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2243e  ldc.i4.s 0x14
0x22440  ldstr    aTitleWasNotFou// "Title was not found for Entity: {0} , s"...
0x22445  ldc.i4.2
0x22446  newarr   [mscorlib]System.Object
0x2244b  dup
0x2244c  ldc.i4.0
0x2244d  ldarg.0
0x2244e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x22453  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x22458  stelem.ref
0x22459  dup
0x2245a  ldc.i4.1
0x2245b  ldloc.3
0x2245c  box      [mscorlib]System.Boolean
0x22461  stelem.ref
0x22462  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22467  ldarg.0
0x22468  ldloc.1
0x22469  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x2246e  ldarg.3
0x2246f  brfalse.s loc_22489
0x22471  ldarg.0
0x22472  ldarg.0
0x22473  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x22478  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2247d  ldc.i4.2
0x2247e  ldloc.0
0x2247f  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.IconUtil::GetIconPath(int32 objectTypeCode, valuetype Microsoft.Crm.IconType iconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22484  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x22489  ldarg.s  4
0x2248b  brfalse.s loc_224A6
0x2248d  ldarg.0
0x2248e  ldarg.0
0x2248f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x22494  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x22499  ldc.i4.s 9
0x2249b  ldloc.0
0x2249c  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.IconUtil::GetIconPath(int32 objectTypeCode, valuetype Microsoft.Crm.IconType iconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x224a1  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetVectorIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x224a6  ldarg.s  5
0x224a8  brfalse.s loc_224C2
0x224aa  ldarg.0
0x224ab  ldarg.0
0x224ac  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x224b1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x224b6  ldc.i4.3
0x224b7  ldloc.0
0x224b8  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.IconUtil::GetIconPath(int32 objectTypeCode, valuetype Microsoft.Crm.IconType iconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x224bd  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetOutlookShortcutIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x224c2  ldarg.s  6
0x224c4  brfalse.s loc_224F5
0x224c6  ldarg.0
0x224c7  ldstr    aRootHomepageAs// "/_root/homepage.aspx?etc="
0x224cc  ldarg.0
0x224cd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::_entity
0x224d2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x224d7  stloc.s  4
0x224d9  ldloca.s 4
0x224db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x224e0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x224e5  call     string [mscorlib]System.String::Concat(string, string)
0x224ea  ldloc.0
0x224eb  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x224f0  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetUrl(class Microsoft.Crm.Application.Utility.CrmUri value)
0x224f5  ldarg.s  7
0x224f7  brfalse.s loc_2251A
0x224f9  ldarg.0
0x224fa  ldarg.0
0x224fb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMapEntitySubArea::get_Entity()
0x22500  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Description()
0x22505  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2250a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2250f  ldloc.0
0x22510  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22515  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetDescription(string value)
0x2251a  ldarg.s  8
0x2251c  brfalse.s loc_22525
0x2251e  ldarg.0
0x2251f  ldc.i4.0
0x22520  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetPassParameters(bool value)
0x22525  ret
```
