# Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoUpdate

- ea: `0x5c450`
- end: `0x5c799`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoUpdate`
- size: `841`
- prototype: ``
- caller_count: `4`
- callee_count: `39`
- tags: `installer_update, broker_com_uri`

## callers

- `0x55590`
- `0x598a0`
- `0x5cc40`
- `0x8bf60`

## callees

- `0x7690`
- `0x18550`
- `0x18800`
- `0x2ec00`
- `0x2ef10`
- `0x2efe0`
- `0x2f2f0`
- `0x2f330`
- `0x30fb0`
- `0x313e0`
- `0x34f50`
- `0x355d0`
- `0x35680`
- `0x35850`
- `0x35b80`
- `0x35bc0`
- `0x36170`
- `0x367e0`
- `0x368a0`
- `0x39480`
- `0x3b4b0`
- `0x3b510`
- `0x3b590`
- `0x3b620`
- `0x54660`
- `0x5b500`
- `0x5ba40`
- `0x5c450`
- `0x5c7a0`
- `0x5ddd0`
- `0x5e120`
- `0x66ae0`
- `0x66c80`
- `0x67590`
- `0x68780`
- `0x6b620`
- `0x7f3a0`
- `0x8b390`
- `0x8b3e0`

## string_xrefs

- `0x5c78e`: `Update`
- `0x5c47e`: `DoUpdate`
- `0x5c558`: `Attempting to update an UnpublishedDelete component: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5c450  ldarg.1
0x5c451  ldstr    aEntity_0// "entity"
0x5c456  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c45b  ldarg.2
0x5c45c  ldstr    aFilter// "filter"
0x5c461  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c466  ldarg.3
0x5c467  ldstr    aContext// "context"
0x5c46c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c471  ldc.i4.1
0x5c472  ldarg.3
0x5c473  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5c478  ldarg.1
0x5c479  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c47e  ldstr    aDoupdate// "DoUpdate"
0x5c483  ldc.i4.0
0x5c484  ldnull
0x5c485  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::CaptureQueryDetailsUsingEntityMetadata(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType initiator, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string operationName, [opt] bool isLeadingWildCardQuery, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> securityQueryDetails)
0x5c48a  ldarg.3
0x5c48b  ldarg.1
0x5c48c  call     void Microsoft.Crm.Platform.RequiredFieldValidator::ValidateForUpdate(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x5c491  ldsfld   class Microsoft.Crm.BusinessEntities.LocalizedLabelValidator Microsoft.Crm.BusinessEntities.LocalizedLabelValidator::Instance
0x5c496  ldarg.3
0x5c497  ldarg.1
0x5c498  callvirt instance void Microsoft.Crm.BusinessEntities.LocalizedLabelValidator::ValidateForUpdate(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x5c49d  ldarg.1
0x5c49e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5c4a3  stloc.0
0x5c4a4  ldarg.0
0x5c4a5  ldfld    class PreUpdateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreUpdateInPipeline
0x5c4aa  brfalse.s loc_5C4C2
0x5c4ac  ldarg.0
0x5c4ad  ldfld    class PreUpdateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreUpdateInPipeline
0x5c4b2  ldarg.0
0x5c4b3  ldnull
0x5c4b4  ldloc.0
0x5c4b5  ldnull
0x5c4b6  ldnull
0x5c4b7  ldarg.3
0x5c4b8  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c4bd  callvirt instance void PreUpdateInPipelineEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5c4c2  ldloc.0
0x5c4c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone()
0x5c4c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity
0x5c4cd  stloc.1
0x5c4ce  ldc.i4.0
0x5c4cf  stloc.2
0x5c4d0  ldc.i4.0
0x5c4d1  stloc.3
0x5c4d2  ldarg.0
0x5c4d3  ldarg.1
0x5c4d4  ldarg.3
0x5c4d5  ldloca.s 3
0x5c4d7  ldloca.s 2
0x5c4d9  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::HandleStateAndSecurityAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] bool& doSetStateOperation, [out] bool& doAssignOperation)
0x5c4de  ldc.i4.1
0x5c4df  stloc.s  4
0x5c4e1  ldarg.1
0x5c4e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c4e7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0x5c4ec  brfalse  loc_5C6A1
0x5c4f1  ldarg.1
0x5c4f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c4f7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5c4fc  ldc.i4.0
0x5c4fd  call     int32 Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrieveComponentType(string platformName, bool isMetadata)
0x5c502  stloc.s  7
0x5c504  ldarg.1
0x5c505  ldarg.1
0x5c506  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c50b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5c510  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x5c515  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5c51a  unbox.any [mscorlib]System.Guid
0x5c51f  stloc.s  8
0x5c521  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::.ctor()
0x5c526  ldloc.s  7
0x5c528  ldloc.s  8
0x5c52a  ldc.i4.1
0x5c52b  ldarg.3
0x5c52c  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c531  stloc.s  9
0x5c533  ldloc.s  9
0x5c535  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x5c53a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x5c53f  ldc.i4.3
0x5c540  bne.un.s loc_5C587
0x5c542  ldarg.3
0x5c543  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c548  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x5c54d  brtrue.s loc_5C587
0x5c54f  ldnull
0x5c550  ldarg.3
0x5c551  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5c556  ldc.i4.s 0x14
0x5c558  ldstr    aAttemptingToUp// "Attempting to update an UnpublishedDele"...
0x5c55d  ldc.i4.1
0x5c55e  newarr   [mscorlib]System.Object
0x5c563  dup
0x5c564  ldc.i4.0
0x5c565  ldarg.1
0x5c566  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c56b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5c570  stelem.ref
0x5c571  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c576  ldc.i4   0x8004F00F
0x5c57b  ldc.i4.0
0x5c57c  newarr   [mscorlib]System.Object
0x5c581  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5c586  throw
0x5c587  ldarg.1
0x5c588  ldc.i4.1
0x5c589  ldloc.s  9
0x5c58b  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x5c590  ldarg.3
0x5c591  call     class Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInputFactory::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype Microsoft.Crm.Platform.ComponentOperation operation, valuetype Microsoft.Crm.Platform.ComponentStateNames currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c596  stloc.s  0xA
0x5c598  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5c59d  ldc.i4.s 0x14
0x5c59f  ldstr    aUpdating0WithI// "Updating {0} with id {1}"
0x5c5a4  ldc.i4.2
0x5c5a5  newarr   [mscorlib]System.Object
0x5c5aa  dup
0x5c5ab  ldc.i4.0
0x5c5ac  ldarg.1
0x5c5ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5c5b2  stelem.ref
0x5c5b3  dup
0x5c5b4  ldc.i4.1
0x5c5b5  ldarg.1
0x5c5b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5c5bb  stelem.ref
0x5c5bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c5c1  ldarg.1
0x5c5c2  ldarg.3
0x5c5c3  ldloc.0
0x5c5c4  ldloc.s  9
0x5c5c6  ldloc.s  0xA
0x5c5c8  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::TakeSnapshot(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity businessEntity, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states, class Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput input)
0x5c5cd  ldsfld   class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionFactory Microsoft.Crm.BusinessEntities.BusinessProcessObject::_componentTransitionFactory
0x5c5d2  ldloc.s  0xA
0x5c5d4  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessProcessObjectComponentStateTransitionActionFactory::.ctor()
0x5c5d9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionFactory::CreateStateTransition(class Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x5c5de  ldloc.s  0xA
0x5c5e0  callvirt instance int32 Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_ComponentType()
0x5c5e5  ldarg.1
0x5c5e6  ldarg.1
0x5c5e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c5ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5c5f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x5c5f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5c5fb  unbox.any [mscorlib]System.Guid
0x5c600  ldloc.0
0x5c601  ldloc.s  9
0x5c603  ldarg.3
0x5c604  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::Execute(int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c609  pop
0x5c60a  ldarg.3
0x5c60b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c610  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x5c615  stloc.s  0xB
0x5c617  ldloc.s  0xA
0x5c619  callvirt instance valuetype [Microsoft.Crm.Constants]Microsoft.Crm.ComponentSolutionType Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_SolutionType()
0x5c61e  ldc.i4.4
0x5c61f  bne.un.s loc_5C638
0x5c621  ldarg.3
0x5c622  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c627  ldloc.s  9
0x5c629  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x5c62e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x5c633  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_SolutionId(valuetype [mscorlib]System.Guid)
0x5c638  ldloc.s  7
0x5c63a  ldloc.s  8
0x5c63c  ldloca.s 0xC
0x5c63e  ldloca.s 0xD
0x5c640  ldarg.3
0x5c641  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedPublisherOption Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::IsSharedComponent(int32 componentType, valuetype [mscorlib]System.Guid id, [out] valuetype [mscorlib]System.Guid& baseSolutionId, [out] valuetype [mscorlib]System.Guid& topSolutionId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c646  stloc.s  0xE
0x5c648  ldarg.3
0x5c649  ldc.i4.1
0x5c64a  ldarg.1
0x5c64b  ldarg.1
0x5c64c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c651  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5c656  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x5c65b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5c660  unbox.any [mscorlib]System.Guid
0x5c665  ldloc.s  0xA
0x5c667  callvirt instance int32 Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_ComponentType()
0x5c66c  ldloc.s  0xE
0x5c66e  ldloc.s  0xC
0x5c670  ldloc.s  0xD
0x5c672  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType type, valuetype [mscorlib]System.Guid componentId, int32 componentType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedPublisherOption spOption, valuetype [mscorlib]System.Guid baseSolutionId, valuetype [mscorlib]System.Guid topSolutionId)
0x5c677  ldarg.3
0x5c678  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5c67d  ldloc.s  0xB
0x5c67f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_SolutionId(valuetype [mscorlib]System.Guid)
0x5c684  ldloc.s  0xA
0x5c686  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_FinalComponentState()
0x5c68b  brfalse.s loc_5C699
0x5c68d  ldloc.s  0xA
0x5c68f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.FactoryInput::get_FinalComponentState()
0x5c694  ldc.i4.5
0x5c695  ceq
0x5c697  br.s     loc_5C69A
0x5c699  ldc.i4.1
0x5c69a  stloc.s  4
0x5c69c  br       loc_5C73F
0x5c6a1  ldarg.1
0x5c6a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c6a7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsShareableAcrossOrgs()
0x5c6ac  brfalse  loc_5C737
0x5c6b1  ldarg.1
0x5c6b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Moniker()
0x5c6b7  stloc.s  0xF
0x5c6b9  ldloc.s  0xF
0x5c6bb  brtrue.s loc_5C6D6
0x5c6bd  ldarg.1
0x5c6be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5c6c3  unbox.any [mscorlib]System.Guid
0x5c6c8  ldarg.1
0x5c6c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5c6ce  ldarg.3
0x5c6cf  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c6d4  stloc.s  0xF
0x5c6d6  newobj   instance void Microsoft.Crm.Platform.MultipleRowEntities.BusinessEntityStateLoader::.ctor()
0x5c6db  ldarg.1
0x5c6dc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5c6e1  ldloc.s  0xF
0x5c6e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5c6e8  ldc.i4.0
0x5c6e9  ldarg.3
0x5c6ea  callvirt instance class Microsoft.Crm.Platform.MultipleRowEntities.EntityState Microsoft.Crm.Platform.MultipleRowEntities.EntityStateLoader::Load(string entityName, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.MultipleRowEntities.EntityStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c6ef  stloc.s  0x10
0x5c6f1  ldsfld   class Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionFactory Microsoft.Crm.BusinessEntities.BusinessProcessObject::_transitionFactory
0x5c6f6  ldc.i4.1
0x5c6f7  ldarg.0
0x5c6f8  ldarg.1
0x5c6f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c6fe  call     instance valuetype Microsoft.Crm.Platform.EntityType Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetEntityType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x5c703  ldarg.3
0x5c704  callvirt instance valuetype Microsoft.Crm.Platform.OperationContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_OperationContext()
0x5c709  ldloc.s  0x10
0x5c70b  callvirt instance valuetype Microsoft.Crm.Platform.EntityStateNames Microsoft.Crm.Platform.MultipleRowEntities.EntityState::get_Name()
0x5c710  newobj   instance void Microsoft.Crm.Platform.MultipleRowEntities.BusinessProcessObjectStateTransitionActionFactory::.ctor()
0x5c715  callvirt instance class Microsoft.Crm.Platform.MultipleRowEntities.StateTransition Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionFactory::CreateStateTransition(valuetype Microsoft.Crm.Platform.EntityOperation operation, valuetype Microsoft.Crm.Platform.EntityType entityType, valuetype Microsoft.Crm.Platform.OperationContext context, valuetype Microsoft.Crm.Platform.EntityStateNames currentState, class Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionActionFactory actionFactory)
0x5c71a  ldarg.1
0x5c71b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5c720  ldarg.1
0x5c721  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5c726  unbox.any [mscorlib]System.Guid
0x5c72b  ldarg.1
0x5c72c  ldloc.s  0x10
0x5c72e  ldarg.3
0x5c72f  callvirt instance valuetype Microsoft.Crm.Platform.EntityStateNames Microsoft.Crm.Platform.MultipleRowEntities.StateTransition::Execute(string entityName, valuetype [mscorlib]System.Guid entityId, object operationParameter, class Microsoft.Crm.Platform.MultipleRowEntities.EntityState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c734  pop
0x5c735  br.s     loc_5C73F
0x5c737  ldarg.1
0x5c738  ldarg.2
0x5c739  ldarg.3
0x5c73a  call     void Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.Query.FilterExpression filter, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c73f  ldarg.0
0x5c740  ldarg.1
0x5c741  ldloc.1
0x5c742  ldloc.3
0x5c743  ldloc.2
0x5c744  ldarg.3
0x5c745  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteUpdateViaOperations(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity clonedEntity, bool doSetStateOperation, bool doAssignOperation, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c74a  ldarg.1
0x5c74b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5c750  ldarg.3
0x5c751  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x5c756  stloc.s  5
0x5c758  ldloc.s  5
0x5c75a  ldarg.2
0x5c75b  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_Criteria(class Microsoft.Crm.Query.FilterExpression value)
0x5c760  ldnull
0x5c761  ldarg.1
0x5c762  ldnull
0x5c763  ldloc.s  5
0x5c765  ldarg.3
0x5c766  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c76b  stloc.s  6
0x5c76d  ldarg.0
0x5c76e  ldfld    class PostUpdateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostUpdateInPipeline
0x5c773  brfalse.s loc_5C783
0x5c775  ldarg.0
0x5c776  ldfld    class PostUpdateInPipelineEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostUpdateInPipeline
0x5c77b  ldarg.0
0x5c77c  ldloc.s  6
0x5c77e  callvirt instance void PostUpdateInPipelineEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x5c783  ldloc.s  4
0x5c785  brfalse.s loc_5C798
0x5c787  ldarg.3
0x5c788  ldarg.1
0x5c789  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5c78e  ldstr    aUpdate// "Update"
0x5c793  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, [opt] string messageName)
0x5c798  ret
```
