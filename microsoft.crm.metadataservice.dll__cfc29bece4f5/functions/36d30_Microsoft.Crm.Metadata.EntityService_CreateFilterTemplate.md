# Microsoft.Crm.Metadata.EntityService::CreateFilterTemplate

- ea: `0x36d30`
- end: `0x36f08`
- name: `Microsoft.Crm.Metadata.EntityService::CreateFilterTemplate`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36bb0`

## callees

- `0x36d30`
- `0x37070`
- `0x43de0`

## string_xrefs

- `0x36ed2`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x36d30  ldarg.3
0x36d31  ldsfld   string [mscorlib]System.String::Empty
0x36d36  stind.ref
0x36d37  ldarg.s  4
0x36d39  ldsfld   string [mscorlib]System.String::Empty
0x36d3e  stind.ref
0x36d3f  ldarg.s  5
0x36d41  ldarg.0
0x36d42  ldarg.2
0x36d43  call     string Microsoft.Crm.Metadata.EntityService::GenerateFilterTemplateFetchxml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x36d48  stind.ref
0x36d49  ldarg.0
0x36d4a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_OwnershipTypeMask()
0x36d4f  ldc.i4.1
0x36d50  beq.s    loc_36D61
0x36d52  ldarg.0
0x36d53  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_OwnershipTypeMask()
0x36d58  ldc.i4.8
0x36d59  beq.s    loc_36D61
0x36d5b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36d60  ret
0x36d61  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x36d66  ldarg.2
0x36d67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x36d6c  ldarg.2
0x36d6d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x36d72  stloc.0
0x36d73  ldarg.0
0x36d74  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_OwnershipTypeMask()
0x36d79  ldc.i4.1
0x36d7a  bne.un.s loc_36DF9
0x36d7c  ldarg.3
0x36d7d  ldloc.0
0x36d7e  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36d83  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x36d88  ldstr    aMyviewlabel// "MyViewLabel"
0x36d8d  ldloc.0
0x36d8e  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36d93  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36d98  ldc.i4.1
0x36d99  newarr   [mscorlib]System.Object
0x36d9e  dup
0x36d9f  ldc.i4.0
0x36da0  ldarg.1
0x36da1  ldloc.0
0x36da2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x36da7  ldarg.2
0x36da8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36dad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x36db2  stelem.ref
0x36db3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36db8  stind.ref
0x36db9  ldarg.s  4
0x36dbb  ldloc.0
0x36dbc  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36dc1  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x36dc6  ldstr    aMyviewdescript// "MyViewDescription"
0x36dcb  ldloc.0
0x36dcc  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36dd1  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36dd6  ldc.i4.1
0x36dd7  newarr   [mscorlib]System.Object
0x36ddc  dup
0x36ddd  ldc.i4.0
0x36dde  ldarg.1
0x36ddf  ldloc.0
0x36de0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x36de5  ldarg.2
0x36de6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36deb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x36df0  stelem.ref
0x36df1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36df6  stind.ref
0x36df7  br.s     loc_36E4B
0x36df9  ldarg.3
0x36dfa  ldarg.1
0x36dfb  ldloc.0
0x36dfc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x36e01  ldarg.2
0x36e02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36e07  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x36e0c  stind.ref
0x36e0d  ldarg.s  4
0x36e0f  ldloc.0
0x36e10  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36e15  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x36e1a  ldstr    aActiveviewdesc// "ActiveViewDescription"
0x36e1f  ldloc.0
0x36e20  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x36e25  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36e2a  ldc.i4.1
0x36e2b  newarr   [mscorlib]System.Object
0x36e30  dup
0x36e31  ldc.i4.0
0x36e32  ldarg.1
0x36e33  ldloc.0
0x36e34  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x36e39  ldarg.2
0x36e3a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36e3f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x36e44  stelem.ref
0x36e45  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36e4a  stind.ref
0x36e4b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x36e50  stloc.1
0x36e51  ldarg.2
0x36e52  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedQuery::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36e57  stloc.2
0x36e58  ldloc.2
0x36e59  ldstr    aSavedqueryid// "savedqueryid"
0x36e5e  ldloc.1
0x36e5f  box      [mscorlib]System.Guid
0x36e64  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36e69  ldloc.2
0x36e6a  ldstr    aName// "name"
0x36e6f  ldarg.3
0x36e70  ldind.ref
0x36e71  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36e76  ldloc.2
0x36e77  ldstr    aDescription_0// "description"
0x36e7c  ldarg.s  4
0x36e7e  ldind.ref
0x36e7f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36e84  ldloc.2
0x36e85  ldstr    aReturnedtypeco// "returnedtypecode"
0x36e8a  ldarg.0
0x36e8b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x36e90  box      [mscorlib]System.Int32
0x36e95  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36e9a  ldloc.2
0x36e9b  ldstr    aQuerytype// "querytype"
0x36ea0  ldc.i4   0x2000
0x36ea5  box      [mscorlib]System.Int32
0x36eaa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36eaf  ldloc.2
0x36eb0  ldstr    aIsdefault// "isdefault"
0x36eb5  ldc.i4.1
0x36eb6  box      [mscorlib]System.Boolean
0x36ebb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36ec0  ldloc.2
0x36ec1  ldstr    aIscustomizable// "iscustomizable"
0x36ec6  ldc.i4.1
0x36ec7  box      [mscorlib]System.Boolean
0x36ecc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36ed1  ldloc.2
0x36ed2  ldstr    aFetchxml// "fetchxml"
0x36ed7  ldarg.s  5
0x36ed9  ldind.ref
0x36eda  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x36edf  ldarg.2
0x36ee0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.PlatformMessageDispatcher::.ctor()
0x36ee5  callvirt instance class [mscorlib]System.IDisposable [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::SwitchMessageDispatcher(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher)
0x36eea  stloc.3
0x36eeb  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x36ef0  ldloc.2
0x36ef1  ldarg.2
0x36ef2  ldnull
0x36ef3  ldc.i4.0
0x36ef4  ldc.i4.0
0x36ef5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache, bool, bool)
0x36efa  leave.s  loc_36F06
0x36efc  ldloc.3
0x36efd  brfalse.s loc_36F05
0x36eff  ldloc.3
0x36f00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36f05  endfinally
0x36f06  ldloc.1
0x36f07  ret
```
