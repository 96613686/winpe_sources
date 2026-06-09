# Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishShared_0

- ea: `0x59ef0`
- end: `0x5a08a`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishShared_0`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x59ee0`

## callees

- `0x18540`
- `0x18550`
- `0x18800`
- `0x1ab10`
- `0x1ae30`
- `0x1af00`
- `0x1af20`
- `0x4ba60`
- `0x4c3c0`
- `0x59330`
- `0x59ef0`
- `0x5b5e0`
- `0x5b700`
- `0x66ae0`
- `0x68780`
- `0x7f3a0`
- `0x8b430`
- `0x8b480`

## string_xrefs

- `0x59f5c`: `componentstate`
- `0x5a066`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x59ef0  ldarg.1
0x59ef1  ldstr    aMoniker// "moniker"
0x59ef6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x59efb  ldarg.1
0x59efc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x59f01  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x59f06  brfalse.s loc_59F15
0x59f08  ldarg.1
0x59f09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x59f0e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsShareableAcrossOrgs()
0x59f13  brtrue.s loc_59F20
0x59f15  ldstr    aPublishOperati// "Publish operation is valid only for ent"...
0x59f1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x59f1f  throw
0x59f20  ldarg.1
0x59f21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x59f26  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x59f2b  ldarg.2
0x59f2c  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x59f31  stloc.0
0x59f32  ldloc.0
0x59f33  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59f38  ldarg.1
0x59f39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x59f3e  box      [mscorlib]System.Guid
0x59f43  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddPrimaryKeyCondition(object primaryKeyValue)
0x59f48  pop
0x59f49  ldarg.1
0x59f4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x59f4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0x59f54  brfalse.s loc_59F82
0x59f56  ldloc.0
0x59f57  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59f5c  ldstr    aComponentstate// "componentstate"
0x59f61  ldc.i4.8
0x59f62  ldc.i4.2
0x59f63  newarr   [mscorlib]System.Object
0x59f68  dup
0x59f69  ldc.i4.0
0x59f6a  ldc.i4.1
0x59f6b  box      [mscorlib]System.Int32
0x59f70  stelem.ref
0x59f71  dup
0x59f72  ldc.i4.1
0x59f73  ldc.i4.3
0x59f74  box      [mscorlib]System.Int32
0x59f79  stelem.ref
0x59f7a  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, class [mscorlib]System.Array values)
0x59f7f  pop
0x59f80  br.s     loc_59F9A
0x59f82  ldloc.0
0x59f83  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59f88  ldstr    aInproduction_0// "inproduction"
0x59f8d  ldc.i4.0
0x59f8e  ldc.i4.0
0x59f8f  box      [mscorlib]System.Boolean
0x59f94  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x59f99  pop
0x59f9a  ldarg.0
0x59f9b  ldloc.0
0x59f9c  ldc.i4.1
0x59f9d  ldarg.2
0x59f9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, bool retrieveDeletedItems, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59fa3  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x59fa8  ldc.i4.0
0x59fa9  ble      loc_5A070
0x59fae  ldarg.2
0x59faf  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryRegisterPostCommitHandler(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59fb4  ldarg.1
0x59fb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x59fba  ldarg.2
0x59fbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x59fc0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x59fc5  stloc.1
0x59fc6  ldloc.1
0x59fc7  ldloc.1
0x59fc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x59fcd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x59fd2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x59fd7  ldarg.1
0x59fd8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x59fdd  box      [mscorlib]System.Guid
0x59fe2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x59fe7  ldloc.1
0x59fe8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x59fed  ldarg.2
0x59fee  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x59ff3  stloc.2
0x59ff4  ldloc.2
0x59ff5  ldloc.1
0x59ff6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x59ffb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5a000  ldarg.2
0x5a001  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x5a006  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_Criteria(class Microsoft.Crm.Query.FilterExpression value)
0x5a00b  ldloc.2
0x5a00c  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a011  ldarg.1
0x5a012  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5a017  box      [mscorlib]System.Guid
0x5a01c  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddPrimaryKeyCondition(object primaryKeyValue)
0x5a021  pop
0x5a022  ldarg.1
0x5a023  ldloc.1
0x5a024  ldnull
0x5a025  ldloc.2
0x5a026  ldarg.2
0x5a027  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5a02c  stloc.3
0x5a02d  ldarg.0
0x5a02e  ldfld    class PrePublishEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PrePublish
0x5a033  brfalse.s loc_5A042
0x5a035  ldarg.0
0x5a036  ldfld    class PrePublishEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PrePublish
0x5a03b  ldarg.0
0x5a03c  ldloc.3
0x5a03d  callvirt instance void PrePublishEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5a042  ldarg.0
0x5a043  ldarg.1
0x5a044  ldarg.2
0x5a045  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoPublish(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5a04a  ldarg.0
0x5a04b  ldfld    class PostPublishEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostPublish
0x5a050  brfalse.s loc_5A05F
0x5a052  ldarg.0
0x5a053  ldfld    class PostPublishEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostPublish
0x5a058  ldarg.0
0x5a059  ldloc.3
0x5a05a  callvirt instance void PostPublishEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5a05f  ldarg.2
0x5a060  ldarg.1
0x5a061  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x5a066  ldstr    aUpdate// "Update"
0x5a06b  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, [opt] string messageName)
0x5a070  ldarg.3
0x5a071  brfalse.s loc_5A089
0x5a073  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::.ctor()
0x5a078  ldarg.1
0x5a079  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5a07e  ldarg.2
0x5a07f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5a084  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishByObjectId(valuetype [mscorlib]System.Guid objectId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x5a089  ret
```
