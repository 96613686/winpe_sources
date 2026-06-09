# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::Update

- ea: `0x8a40`
- end: `0x8b0c`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::Update`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5100`

## callees

- `0x89f0`
- `0x8a20`
- `0x8a30`
- `0x8a40`
- `0x8c40`
- `0x8f40`

## string_xrefs

- `0x8ad7`: `A case creation rule for the specified channel and queue already exists. You can't create another one.`
- `0x8af3`: `Please select either a global or case template.`

## pseudocode

```c

```

## disassembly

```asm
0x8a40  ldarg.1
0x8a41  ldstr    aEntity// "entity"
0x8a46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a4b  ldarg.2
0x8a4c  ldstr    aContext// "context"
0x8a51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a56  ldarg.1
0x8a57  ldarg.0
0x8a58  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x8a5d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x8a62  brfalse.s loc_8A75
0x8a64  ldc.i4   0x80040200
0x8a69  ldc.i4.0
0x8a6a  newarr   [mscorlib]System.Object
0x8a6f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8a74  throw
0x8a75  ldarg.0
0x8a76  ldarg.1
0x8a77  ldarg.2
0x8a78  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RuleServiceBase::RetrieveBeforeUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8a7d  stloc.0
0x8a7e  ldarg.0
0x8a7f  ldarg.1
0x8a80  ldloc.0
0x8a81  ldarg.2
0x8a82  callvirt instance void Microsoft.Crm.Service.ObjectModel.RuleServiceBase::ValidateBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8a87  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8a8c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8a91  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x8a96  ldarg.2
0x8a97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8a9c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x8aa1  ldarg.2
0x8aa2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8aa7  ldarg.2
0x8aa8  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x8aad  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x8ab2  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8ab7  dup
0x8ab8  brtrue.s loc_8AE7
0x8aba  ldarg.1
0x8abb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x8ac0  ldstr    aQueueid// "queueid"
0x8ac5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x8aca  brfalse.s loc_8AE7
0x8acc  ldarg.0
0x8acd  ldarg.1
0x8ace  ldloc.0
0x8acf  ldarg.2
0x8ad0  call     instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsRuleExistsForSameQueueAndChannel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ad5  brfalse.s loc_8AE7
0x8ad7  ldstr    aACaseCreationR// "A case creation rule for the specified "...
0x8adc  ldc.i4   0x8004F884
0x8ae1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x8ae6  throw
0x8ae7  brtrue.s loc_8B03
0x8ae9  ldarg.0
0x8aea  ldarg.1
0x8aeb  ldarg.2
0x8aec  callvirt instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsResponseTemplateValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8af1  brtrue.s loc_8B03
0x8af3  ldstr    aPleaseSelectEi// "Please select either a global or case t"...
0x8af8  ldc.i4   0x80060730
0x8afd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x8b02  throw
0x8b03  ldarg.0
0x8b04  ldarg.1
0x8b05  ldarg.2
0x8b06  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8b0b  ret
```
