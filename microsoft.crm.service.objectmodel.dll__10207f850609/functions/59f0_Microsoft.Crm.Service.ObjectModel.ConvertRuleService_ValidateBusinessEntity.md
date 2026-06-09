# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ValidateBusinessEntity

- ea: `0x59f0`
- end: `0x5abf`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ValidateBusinessEntity`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x59f0`
- `0x5af0`
- `0x5da0`
- `0x5e90`
- `0x6010`
- `0x89f0`

## pseudocode

```c

```

## disassembly

```asm
0x59f0  ldarg.0
0x59f1  ldarg.1
0x59f2  ldarg.2
0x59f3  ldarg.3
0x59f4  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ValidateSourceTypeCode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59f9  ldarg.2
0x59fa  brfalse.s loc_5A05
0x59fc  ldarg.2
0x59fd  ldarg.1
0x59fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::Merge(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5a03  br.s     loc_5A06
0x5a05  ldarg.1
0x5a06  stloc.0
0x5a07  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5a0c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5a11  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x5a16  ldarg.3
0x5a17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a1c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x5a21  ldarg.3
0x5a22  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a27  ldarg.3
0x5a28  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x5a2d  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x5a32  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x5a37  brfalse.s loc_5AB7
0x5a39  ldarg.2
0x5a3a  brfalse.s loc_5AB7
0x5a3c  ldarg.0
0x5a3d  ldarg.2
0x5a3e  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a43  call     instance bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::IsAttributeValueNull(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName)
0x5a48  brtrue.s loc_5AB7
0x5a4a  ldarg.0
0x5a4b  ldarg.1
0x5a4c  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a51  call     instance bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::IsAttributeValueNull(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName)
0x5a56  brtrue.s loc_5A8F
0x5a58  ldarg.1
0x5a59  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a5e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5a63  brtrue.s loc_5AB7
0x5a65  ldarg.2
0x5a66  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a6b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5a70  brtrue.s loc_5AB7
0x5a72  ldarg.1
0x5a73  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a78  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x5a7d  ldarg.2
0x5a7e  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a83  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x5a88  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x5a8d  brtrue.s loc_5AB7
0x5a8f  ldarg.0
0x5a90  ldarg.2
0x5a91  ldstr    aChannelpropert// "channelpropertygroupid"
0x5a96  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x5a9b  unbox.any [mscorlib]System.Guid
0x5aa0  ldloc.0
0x5aa1  ldarg.0
0x5aa2  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x5aa7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::GetAttributeValue(string)
0x5aac  unbox.any [mscorlib]System.Guid
0x5ab1  ldarg.3
0x5ab2  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ValidateForChannelPropertyReference(valuetype [mscorlib]System.Guid channelPropertyGroupId, valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5ab7  ldarg.0
0x5ab8  ldloc.0
0x5ab9  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::ThrowIfInvalidAutoResponseSettings(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity postImage)
0x5abe  ret
```
