# Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoCreate

- ea: `0x5b740`
- end: `0x5b9e0`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoCreate`
- size: `672`
- prototype: ``
- caller_count: `3`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x55550`
- `0x5b140`
- `0x8baa0`

## callees

- `0x7690`
- `0x2eb30`
- `0x2ee30`
- `0x2ef10`
- `0x2ef20`
- `0x2ef30`
- `0x2ef40`
- `0x2f330`
- `0x30fb0`
- `0x313e0`
- `0x34f50`
- `0x355d0`
- `0x35f10`
- `0x36170`
- `0x36300`
- `0x367e0`
- `0x368a0`
- `0x39480`
- `0x3b4b0`
- `0x3b510`
- `0x3b620`
- `0x515b0`
- `0x54350`
- `0x5b500`
- `0x5b740`
- `0x5b9e0`
- `0x5ba40`
- `0x5d870`
- `0x66ae0`
- `0x66c80`
- `0x67570`
- `0x68780`
- `0x6b5d0`
- `0x7f3a0`
- `0x8af30`
- `0x8af80`

## string_xrefs

- `0x5b763`: `DoCreate`
- `0x5b9d4`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x5b740  ldarg.2
0x5b741  ldstr    aContext// "context"
0x5b746  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5b74b  ldarg.1
0x5b74c  ldstr    aEntity_0// "entity"
0x5b751  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5b756  ldc.i4.1
0x5b757  ldarg.2
0x5b758  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5b75d  ldarg.1
0x5b75e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b763  ldstr    aDocreate// "DoCreate"
0x5b768  ldc.i4.0
0x5b769  ldnull
0x5b76a  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::CaptureQueryDetailsUsingEntityMetadata(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType initiator, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string operationName, [opt] bool isLeadingWildCardQuery, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> securityQueryDetails)
0x5b76f  ldarg.2
0x5b770  ldarg.1
0x5b771  call     void Microsoft.Crm.Platform.RequiredFieldValidator::ValidateForCreate(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x5b776  ldsfld   class Microsoft.Crm.BusinessEntities.LocalizedLabelValidator Microsoft.Crm.BusinessEntities.LocalizedLabelValidator::Instance
0x5b77b  ldarg.2
0x5b77c  ldarg.1
0x5b77d  callvirt instance void Microsoft.Crm.BusinessEntities.LocalizedLabelValidator::ValidateForCreate(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x5b782  ldarg.1
0x5b783  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5b788  stloc.0
0x5b789  ldarg.0
0x5b78a  ldfld    class PreCreateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreCreateInPipeline
0x5b78f  brfalse.s loc_5B7A7
0x5b791  ldarg.0
0x5b792  ldfld    class PreCreateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreCreateInPipeline
0x5b797  ldarg.0
0x5b798  ldnull
0x5b799  ldloc.0
0x5b79a  ldnull
0x5b79b  ldnull
0x5b79c  ldarg.2
0x5b79d  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b7a2  callvirt instance void PreCreateInPipelineEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5b7a7  ldc.i4.1
0x5b7a8  stloc.1
0x5b7a9  ldarg.1
0x5b7aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b7af  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0x5b7b4  brfalse  loc_5B90E
0x5b7b9  ldarg.1
0x5b7ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b7bf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5b7c4  ldc.i4.0
0x5b7c5  call     int32 Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrieveComponentType(string platformName, bool isMetadata)
0x5b7ca  stloc.s  4
0x5b7cc  ldarg.1
0x5b7cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5b7d2  unbox.any [mscorlib]System.Guid
0x5b7d7  ldloc.s  4
0x5b7d9  ldarg.2
0x5b7da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5b7df  call     void Microsoft.Crm.Platform.Server.PostRTMComponentsTracker::TrackPostRTMComponents(valuetype [mscorlib]System.Guid componentId, int32 componentType, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x5b7e4  ldarg.1
0x5b7e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b7ea  ldstr    aIntroducedvers// "introducedversion"
0x5b7ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x5b7f4  brfalse.s loc_5B829
0x5b7f6  ldarg.1
0x5b7f7  ldstr    aIntroducedvers// "introducedversion"
0x5b7fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b801  brtrue.s loc_5B829
0x5b803  ldarg.1
0x5b804  ldstr    aIntroducedvers// "introducedversion"
0x5b809  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x5b80e  ldarg.2
0x5b80f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5b814  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_OriginalSolutionId()
0x5b819  ldarg.2
0x5b81a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x5b81f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_Version()
0x5b824  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x5b829  ldarg.2
0x5b82a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5b82f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x5b834  ldc.i4.2
0x5b835  bne.un.s loc_5B861
0x5b837  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::.ctor()
0x5b83c  ldarg.1
0x5b83d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b842  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5b847  ldc.i4.0
0x5b848  call     int32 Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrieveComponentType(string platformName, bool isMetadata)
0x5b84d  ldarg.1
0x5b84e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Moniker()
0x5b853  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5b858  ldc.i4.0
0x5b859  ldarg.2
0x5b85a  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b85f  br.s     loc_5B872
0x5b861  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::.ctor()
0x5b866  ldloc.0
0x5b867  ldc.i4.0
0x5b868  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType)
0x5b86d  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Create(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x5b872  stloc.s  5
0x5b874  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5b879  ldc.i4.s 0x14
0x5b87b  ldstr    aCreating0WithI// "Creating {0} with id {1}"
0x5b880  ldc.i4.2
0x5b881  newarr   [mscorlib]System.Object
0x5b886  dup
0x5b887  ldc.i4.0
0x5b888  ldarg.1
0x5b889  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5b88e  stelem.ref
0x5b88f  dup
0x5b890  ldc.i4.1
0x5b891  ldarg.1
0x5b892  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5b897  stelem.ref
0x5b898  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5b89d  ldarg.1
0x5b89e  ldc.i4.0
0x5b89f  ldloc.s  5
0x5b8a1  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x5b8a6  ldarg.2
0x5b8a7  call     class Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInputFactory::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype Microsoft.Crm.Platform.ComponentOperation operation, valuetype Microsoft.Crm.Platform.ComponentStateNames currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b8ac  stloc.s  6
0x5b8ae  ldsfld   class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionFactory Microsoft.Crm.BusinessEntities.BusinessProcessObject::_componentTransitionFactory
0x5b8b3  ldloc.s  6
0x5b8b5  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessProcessObjectComponentStateTransitionActionFactory::.ctor()
0x5b8ba  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionFactory::CreateStateTransition(class Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x5b8bf  ldloc.s  6
0x5b8c1  callvirt instance int32 Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_ComponentType()
0x5b8c6  ldarg.1
0x5b8c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5b8cc  unbox.any [mscorlib]System.Guid
0x5b8d1  ldarg.1
0x5b8d2  ldloc.s  5
0x5b8d4  ldarg.2
0x5b8d5  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::Execute(int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b8da  pop
0x5b8db  ldarg.2
0x5b8dc  ldc.i4.0
0x5b8dd  ldarg.1
0x5b8de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5b8e3  unbox.any [mscorlib]System.Guid
0x5b8e8  ldloc.s  6
0x5b8ea  callvirt instance int32 Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_ComponentType()
0x5b8ef  ldc.i4.1
0x5b8f0  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType type, valuetype [mscorlib]System.Guid componentId, int32 componentType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedPublisherOption spOption)
0x5b8f5  ldloc.s  6
0x5b8f7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_FinalComponentState()
0x5b8fc  brfalse.s loc_5B90A
0x5b8fe  ldloc.s  6
0x5b900  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_FinalComponentState()
0x5b905  ldc.i4.5
0x5b906  ceq
0x5b908  br.s     loc_5B90B
0x5b90a  ldc.i4.1
0x5b90b  stloc.1
0x5b90c  br.s     loc_5B98B
0x5b90e  ldarg.1
0x5b90f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b914  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsShareableAcrossOrgs()
0x5b919  brfalse.s loc_5B984
0x5b91b  newobj   instance void Microsoft.Crm.Platform.MultipleRowEntities.EntityState::.ctor()
0x5b920  stloc.s  7
0x5b922  ldloc.s  7
0x5b924  ldc.i4.0
0x5b925  callvirt instance void Microsoft.Crm.Platform.MultipleRowEntities.EntityState::set_Name(valuetype Microsoft.Crm.Platform.EntityStateNames value)
0x5b92a  ldloc.s  7
0x5b92c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Platform.EntityStateNames, class Microsoft.Crm.Platform.MultipleRowEntities.EntityInstance> Microsoft.Crm.Platform.MultipleRowEntities.EntityState::get_Instances()
0x5b931  ldc.i4.0
0x5b932  ldloc.0
0x5b933  ldc.i4.0
0x5b934  newobj   instance void Microsoft.Crm.Platform.MultipleRowEntities.BusinessEntityInstance::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, valuetype Microsoft.Crm.Platform.EntityStateNames instanceType)
0x5b939  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Platform.EntityStateNames, class Microsoft.Crm.Platform.MultipleRowEntities.EntityInstance>::set_Item(var<u1>, !!T0)
0x5b93e  ldsfld   class Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionFactory Microsoft.Crm.BusinessEntities.BusinessProcessObject::_transitionFactory
0x5b943  ldc.i4.0
0x5b944  ldarg.0
0x5b945  ldarg.1
0x5b946  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b94b  call     instance valuetype Microsoft.Crm.Platform.EntityType Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetEntityType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x5b950  ldarg.2
0x5b951  callvirt instance valuetype Microsoft.Crm.Platform.OperationContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_OperationContext()
0x5b956  ldloc.s  7
0x5b958  callvirt instance valuetype Microsoft.Crm.Platform.EntityStateNames Microsoft.Crm.Platform.MultipleRowEntities.EntityState::get_Name()
0x5b95d  newobj   instance void Microsoft.Crm.Platform.MultipleRowEntities.BusinessProcessObjectStateTransitionActionFactory::.ctor()
0x5b962  callvirt instance class Microsoft.Crm.Platform.MultipleRowEntities.StateTransition Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionFactory::CreateStateTransition(valuetype Microsoft.Crm.Platform.EntityOperation operation, valuetype Microsoft.Crm.Platform.EntityType entityType, valuetype Microsoft.Crm.Platform.OperationContext context, valuetype Microsoft.Crm.Platform.EntityStateNames currentState, class Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionActionFactory actionFactory)
0x5b967  ldarg.1
0x5b968  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5b96d  ldarg.1
0x5b96e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5b973  unbox.any [mscorlib]System.Guid
0x5b978  ldarg.1
0x5b979  ldloc.s  7
0x5b97b  ldarg.2
0x5b97c  callvirt instance valuetype Microsoft.Crm.Platform.EntityStateNames Microsoft.Crm.Platform.MultipleRowEntities.StateTransition::Execute(string entityName, valuetype [mscorlib]System.Guid entityId, object operationParameter, class Microsoft.Crm.Platform.MultipleRowEntities.EntityState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b981  pop
0x5b982  br.s     loc_5B98B
0x5b984  ldarg.1
0x5b985  ldarg.2
0x5b986  call     void Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b98b  ldarg.0
0x5b98c  ldarg.1
0x5b98d  ldarg.2
0x5b98e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetMoniker(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5b993  stloc.2
0x5b994  ldloc.2
0x5b995  ldnull
0x5b996  cgt.un
0x5b998  ldstr    aExpectingANonN// "Expecting a non-null moniker"
0x5b99d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5b9a2  ldloc.2
0x5b9a3  ldarg.1
0x5b9a4  ldnull
0x5b9a5  ldnull
0x5b9a6  ldarg.2
0x5b9a7  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b9ac  stloc.3
0x5b9ad  ldarg.1
0x5b9ae  ldarg.2
0x5b9af  ldloc.3
0x5b9b0  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetExtensionArgProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs extensionArgs)
0x5b9b5  ldarg.0
0x5b9b6  ldfld    class PostCreateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostCreateInPipeline
0x5b9bb  brfalse.s loc_5B9CA
0x5b9bd  ldarg.0
0x5b9be  ldfld    class PostCreateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostCreateInPipeline
0x5b9c3  ldarg.0
0x5b9c4  ldloc.3
0x5b9c5  callvirt instance void PostCreateInPipelineEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5b9ca  ldloc.1
0x5b9cb  brfalse.s loc_5B9DE
0x5b9cd  ldarg.2
0x5b9ce  ldarg.1
0x5b9cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b9d4  ldstr    aCreate// "Create"
0x5b9d9  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, [opt] string messageName)
0x5b9de  ldloc.2
0x5b9df  ret
```
