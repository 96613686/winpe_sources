# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::Create

- ea: `0x4fe0`
- end: `0x50f2`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::Create`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4fe0`
- `0x5140`
- `0x5f90`
- `0x8a20`
- `0x8a30`
- `0x8f40`

## string_xrefs

- `0x5078`: `A case creation rule for the specified channel and queue already exists. You can't create another one.`
- `0x50c4`: `Please select either a global or case template.`

## pseudocode

```c

```

## disassembly

```asm
0x4fe0  ldarg.1
0x4fe1  ldstr    aEntity// "entity"
0x4fe6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4feb  ldarg.2
0x4fec  ldstr    aContext// "context"
0x4ff1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ff6  ldarg.0
0x4ff7  ldarg.1
0x4ff8  ldnull
0x4ff9  ldarg.2
0x4ffa  callvirt instance void Microsoft.Crm.Service.ObjectModel.RuleServiceBase::ValidateBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4fff  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5004  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5009  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x500e  ldarg.2
0x500f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5014  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x5019  ldarg.2
0x501a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x501f  ldarg.2
0x5020  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x5025  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x502a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x502f  brfalse.s loc_506D
0x5031  ldarg.1
0x5032  ldstr    aChannelpropert// "channelpropertygroupid"
0x5037  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x503c  brtrue.s loc_5088
0x503e  ldarg.0
0x503f  ldarg.1
0x5040  ldarg.2
0x5041  call     instance int32 Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RetrievePropertyBagSourceType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5046  ldarg.1
0x5047  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x504c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5051  unbox.any [mscorlib]System.Int32
0x5056  beq.s    loc_5088
0x5058  ldc.i4   0x800608EA
0x505d  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x5062  ldc.i4   0x800608EA
0x5067  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x506c  throw
0x506d  ldarg.0
0x506e  ldarg.1
0x506f  ldnull
0x5070  ldarg.2
0x5071  call     instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsRuleExistsForSameQueueAndChannel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5076  brfalse.s loc_5088
0x5078  ldstr    aACaseCreationR// "A case creation rule for the specified "...
0x507d  ldc.i4   0x8004F884
0x5082  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5087  throw
0x5088  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x508d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5092  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x5097  ldarg.2
0x5098  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x509d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x50a2  ldarg.2
0x50a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x50a8  ldarg.2
0x50a9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x50ae  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x50b3  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x50b8  brtrue.s loc_50D4
0x50ba  ldarg.0
0x50bb  ldarg.1
0x50bc  ldarg.2
0x50bd  callvirt instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsResponseTemplateValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50c2  brtrue.s loc_50D4
0x50c4  ldstr    aPleaseSelectEi// "Please select either a global or case t"...
0x50c9  ldc.i4   0x80060730
0x50ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x50d3  throw
0x50d4  ldarg.1
0x50d5  ldstr    aRecordversion// "recordversion"
0x50da  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x50df  brfalse.s loc_50E9
0x50e1  ldarg.0
0x50e2  ldarg.1
0x50e3  ldarg.2
0x50e4  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetRecordVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50e9  ldarg.0
0x50ea  ldarg.1
0x50eb  ldarg.2
0x50ec  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x50f1  ret
```
