# Microsoft.Crm.Platform.SolutionAwareComponents.UninstallUpdateProtectedTransition::ConstructActionSet

- ea: `0x3ca50`
- end: `0x3cc41`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UninstallUpdateProtectedTransition::ConstructActionSet`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callees

- `0x355d0`
- `0x355f0`
- `0x35680`
- `0x356e0`
- `0x35730`
- `0x35b40`
- `0x35b60`
- `0x35b70`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x35c00`
- `0x35c10`
- `0x36a10`
- `0x36a20`
- `0x37590`
- `0x377c0`
- `0x37df0`
- `0x37e10`
- `0x37e50`
- `0x37e70`
- `0x3ca50`
- `0x66ae0`

## string_xrefs

- `0x3ca6b`: `Invalid operation context for transition.	Expected: Uninstall, Received: {0}`
- `0x3cc10`: `No component rows were found that matched the solution id of {0}.\nCurrent state:\n{1}`

## pseudocode

```c

```

## disassembly

```asm
0x3ca50  ldarg.0
0x3ca51  ldc.i4.1
0x3ca52  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidProtection(bool isProtected)
0x3ca57  ldarg.s  5
0x3ca59  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ca5e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3ca63  ldc.i4.2
0x3ca64  beq.s    loc_3CA9A
0x3ca66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ca6b  ldstr    aInvalidOperati_5// "Invalid operation context for transitio"...
0x3ca70  ldc.i4.1
0x3ca71  newarr   [mscorlib]System.Object
0x3ca76  dup
0x3ca77  ldc.i4.0
0x3ca78  ldarg.s  5
0x3ca7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ca7f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3ca84  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext
0x3ca89  stelem.ref
0x3ca8a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ca8f  ldc.i4   0x80040203
0x3ca94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3ca99  throw
0x3ca9a  ldarg.s  5
0x3ca9c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3caa1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3caa6  ldarg.s  4
0x3caa8  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3caad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3cab2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3cab7  brfalse  loc_3CBF2
0x3cabc  ldarg.s  4
0x3cabe  ldarg.s  5
0x3cac0  call     class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::RetrieveSharedPublisherInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState componentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3cac5  stloc.2
0x3cac6  ldloc.2
0x3cac7  brfalse  loc_3CBF2
0x3cacc  ldarg.0
0x3cacd  ldarg.s  4
0x3cacf  ldarg.s  4
0x3cad1  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3cad6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3cadb  ldnull
0x3cadc  ldloc.2
0x3cadd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3cae2  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ProcessActiveRows(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, valuetype [mscorlib]System.Guid solutionId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> deletedInstances, valuetype [mscorlib]System.Guid alternateSolutionId)
0x3cae7  stloc.3
0x3cae8  ldarg.0
0x3cae9  ldarg.0
0x3caea  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3caef  ldarg.s  4
0x3caf1  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3caf6  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3cafb  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3cb00  ldarg.s  4
0x3cb02  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3cb07  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3cb0c  ldc.i4.2
0x3cb0d  ble      loc_3CBEA
0x3cb12  ldarg.0
0x3cb13  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3cb18  ldarg.3
0x3cb19  ldloc.2
0x3cb1a  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3cb1f  ldarg.s  5
0x3cb21  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3cb26  stloc.s  4
0x3cb28  ldloc.s  4
0x3cb2a  ldloc.2
0x3cb2b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3cb30  ldloc.2
0x3cb31  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3cb36  ldarg.s  4
0x3cb38  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3cb3d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3cb42  ldloc.2
0x3cb43  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3cb48  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3cb4d  ldloc.s  4
0x3cb4f  ldloc.2
0x3cb50  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3cb55  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x3cb5a  ldarg.0
0x3cb5b  ldarg.0
0x3cb5c  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3cb61  ldloc.s  4
0x3cb63  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateFullComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3cb68  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3cb6d  ldloc.2
0x3cb6e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3cb73  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x3cb78  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3cb7d  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3cb82  brfalse.s loc_3CBEA
0x3cb84  ldloc.3
0x3cb85  brfalse.s loc_3CB99
0x3cb87  ldarg.0
0x3cb88  ldarg.0
0x3cb89  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3cb8e  ldloc.3
0x3cb8f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3cb94  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3cb99  ldarg.0
0x3cb9a  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3cb9f  ldarg.3
0x3cba0  ldloc.2
0x3cba1  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3cba6  ldc.i4.4
0x3cba7  or
0x3cba8  ldarg.s  5
0x3cbaa  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3cbaf  stloc.s  5
0x3cbb1  ldloc.s  5
0x3cbb3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3cbb8  ldloc.2
0x3cbb9  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3cbbe  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3cbc3  ldloc.2
0x3cbc4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3cbc9  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3cbce  ldarg.0
0x3cbcf  ldarg.0
0x3cbd0  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3cbd5  ldloc.s  5
0x3cbd7  ldarg.s  4
0x3cbd9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3cbde  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateMergeComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance lastNonOverwrittenInstance)
0x3cbe3  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3cbe8  ldc.i4.6
0x3cbe9  ret
0x3cbea  ldarg.s  4
0x3cbec  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3cbf1  ret
0x3cbf2  ldc.i4.0
0x3cbf3  stloc.0
0x3cbf4  ldarg.0
0x3cbf5  ldarg.s  4
0x3cbf7  ldarg.1
0x3cbf8  ldarg.s  5
0x3cbfa  ldloca.s 0
0x3cbfc  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::TryDeleteComponentRows(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, int32 componentType, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] bool& deletionOccurred)
0x3cc01  stloc.1
0x3cc02  ldloc.0
0x3cc03  brfalse.s loc_3CC07
0x3cc05  ldloc.1
0x3cc06  ret
0x3cc07  ldarg.s  5
0x3cc09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3cc0e  ldc.i4.s 0x14
0x3cc10  ldstr    aNoComponentRow// "No component rows were found that match"...
0x3cc15  ldc.i4.2
0x3cc16  newarr   [mscorlib]System.Object
0x3cc1b  dup
0x3cc1c  ldc.i4.0
0x3cc1d  ldarg.s  5
0x3cc1f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3cc24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3cc29  box      [mscorlib]System.Guid
0x3cc2e  stelem.ref
0x3cc2f  dup
0x3cc30  ldc.i4.1
0x3cc31  ldarg.s  4
0x3cc33  stelem.ref
0x3cc34  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3cc39  ldarg.s  4
0x3cc3b  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3cc40  ret
```
