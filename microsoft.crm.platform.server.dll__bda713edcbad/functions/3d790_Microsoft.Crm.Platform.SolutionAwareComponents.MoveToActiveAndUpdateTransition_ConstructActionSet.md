# Microsoft.Crm.Platform.SolutionAwareComponents.MoveToActiveAndUpdateTransition::ConstructActionSet

- ea: `0x3d790`
- end: `0x3db43`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MoveToActiveAndUpdateTransition::ConstructActionSet`
- size: `947`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x355d0`
- `0x355f0`
- `0x356e0`
- `0x35b40`
- `0x35b60`
- `0x35b70`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x35c10`
- `0x369f0`
- `0x36a10`
- `0x36a80`
- `0x37e10`
- `0x37e50`
- `0x37e70`
- `0x37eb0`
- `0x3ba70`
- `0x3c4a0`
- `0x3d470`
- `0x3d790`
- `0x3db50`

## string_xrefs

- `0x3d87a`: `WARNING AS ERROR: Found a snapshot solution with id {0} and name {1} while performing MoveToActiveAndUpdateTransition for object {2} of type {3} in state {4}.`
- `0x3d8e5`: `WARNING AS ERROR: Unable to find solution with id {0} while performing MoveToActiveAndUpdateTransition for object {1} of type {2} in state {3}.`
- `0x3d960`: `ERROR: The MoveToActiveAndUpdateTransition cannot be used for components that have custom solution rows. For component: {0} of type {1} in state {2}, found the following custom solution rows {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x3d790  ldarg.0
0x3d791  ldc.i4.8
0x3d792  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidSolutionOperationContext(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext operationContext)
0x3d797  ldarg.1
0x3d798  ldarg.2
0x3d799  ldarg.3
0x3d79a  ldarg.s  4
0x3d79c  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.MoveAndUpdateTransition::IsComponentSystemOwned(int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3d7a1  brfalse.s loc_3D7EC
0x3d7a3  ldarg.s  4
0x3d7a5  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d7aa  ldc.i4.s 9
0x3d7ac  bne.un.s loc_3D7CD
0x3d7ae  ldarg.0
0x3d7af  ldarg.0
0x3d7b0  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3d7b5  ldarg.0
0x3d7b6  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3d7bb  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveModifiedToNoneTransition::.ctor(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x3d7c0  ldarg.1
0x3d7c1  ldarg.2
0x3d7c2  ldarg.3
0x3d7c3  ldarg.s  4
0x3d7c5  ldarg.s  5
0x3d7c7  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ConstructChildActionSet(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition transition, int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3d7cc  ret
0x3d7cd  ldarg.0
0x3d7ce  ldarg.0
0x3d7cf  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3d7d4  ldarg.0
0x3d7d5  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3d7da  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveTransition::.ctor(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x3d7df  ldarg.1
0x3d7e0  ldarg.2
0x3d7e1  ldarg.3
0x3d7e2  ldarg.s  4
0x3d7e4  ldarg.s  5
0x3d7e6  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ConstructChildActionSet(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition transition, int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3d7eb  ret
0x3d7ec  ldarg.s  4
0x3d7ee  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3d7f3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3d7f8  ldc.i4.1
0x3d7f9  ble      loc_3D9B8
0x3d7fe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3d803  stloc.2
0x3d804  ldarg.s  4
0x3d806  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3d80b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3d810  stloc.3
0x3d811  br       loc_3D927
0x3d816  ldloca.s 3
0x3d818  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3d81d  stloc.s  4
0x3d81f  ldloc.s  4
0x3d821  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d826  ldarg.s  5
0x3d828  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsSystemOrInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d82d  brtrue   loc_3D927
0x3d832  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3d837  ldloc.s  4
0x3d839  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d83e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3d843  brfalse  loc_3D927
0x3d848  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x3d84d  ldloc.s  4
0x3d84f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d854  ldarg.s  5
0x3d856  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x3d85b  stloc.s  5
0x3d85d  ldloc.s  5
0x3d85f  brfalse.s loc_3D8D3
0x3d861  ldloc.s  5
0x3d863  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.SolutionType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_SolutionType()
0x3d868  ldc.i4.1
0x3d869  bne.un.s loc_3D8C6
0x3d86b  ldnull
0x3d86c  ldarg.s  5
0x3d86e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d873  ldc.i4.s 0x14
0x3d875  ldc.i4   0x3E7
0x3d87a  ldstr    aWarningAsError// "WARNING AS ERROR: Found a snapshot solu"...
0x3d87f  ldc.i4.5
0x3d880  newarr   [mscorlib]System.Object
0x3d885  dup
0x3d886  ldc.i4.0
0x3d887  ldloc.s  4
0x3d889  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d88e  box      [mscorlib]System.Guid
0x3d893  stelem.ref
0x3d894  dup
0x3d895  ldc.i4.1
0x3d896  ldloc.s  5
0x3d898  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x3d89d  stelem.ref
0x3d89e  dup
0x3d89f  ldc.i4.2
0x3d8a0  ldarg.2
0x3d8a1  box      [mscorlib]System.Guid
0x3d8a6  stelem.ref
0x3d8a7  dup
0x3d8a8  ldc.i4.3
0x3d8a9  ldarg.1
0x3d8aa  box      [mscorlib]System.Int32
0x3d8af  stelem.ref
0x3d8b0  dup
0x3d8b1  ldc.i4.4
0x3d8b2  ldarg.s  4
0x3d8b4  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d8b9  box      Microsoft.Crm.Platform.ComponentStateNames
0x3d8be  stelem.ref
0x3d8bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x3d8c4  br.s     loc_3D8D3
0x3d8c6  ldloc.2
0x3d8c7  ldloc.s  5
0x3d8c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x3d8ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d8d3  leave.s  loc_3D927
0x3d8d5  pop
0x3d8d6  ldnull
0x3d8d7  ldarg.s  5
0x3d8d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d8de  ldc.i4.s 0x14
0x3d8e0  ldc.i4   0x3E7
0x3d8e5  ldstr    aWarningAsError_0// "WARNING AS ERROR: Unable to find soluti"...
0x3d8ea  ldc.i4.4
0x3d8eb  newarr   [mscorlib]System.Object
0x3d8f0  dup
0x3d8f1  ldc.i4.0
0x3d8f2  ldloc.s  4
0x3d8f4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d8f9  box      [mscorlib]System.Guid
0x3d8fe  stelem.ref
0x3d8ff  dup
0x3d900  ldc.i4.1
0x3d901  ldarg.2
0x3d902  box      [mscorlib]System.Guid
0x3d907  stelem.ref
0x3d908  dup
0x3d909  ldc.i4.2
0x3d90a  ldarg.1
0x3d90b  box      [mscorlib]System.Int32
0x3d910  stelem.ref
0x3d911  dup
0x3d912  ldc.i4.3
0x3d913  ldarg.s  4
0x3d915  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d91a  box      Microsoft.Crm.Platform.ComponentStateNames
0x3d91f  stelem.ref
0x3d920  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x3d925  leave.s  loc_3D927
0x3d927  ldloca.s 3
0x3d929  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3d92e  brtrue   loc_3D816
0x3d933  leave.s  loc_3D943
0x3d935  ldloca.s 3
0x3d937  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3d93d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d942  endfinally
0x3d943  ldloc.2
0x3d944  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3d949  ldc.i4.0
0x3d94a  ble.s    loc_3D9B8
0x3d94c  ldnull
0x3d94d  ldarg.s  5
0x3d94f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d954  ldc.i4.s 0x14
0x3d956  ldc.i4   0x3E7
0x3d95b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d960  ldstr    aErrorTheMoveto// "ERROR: The MoveToActiveAndUpdateTransit"...
0x3d965  ldc.i4.4
0x3d966  newarr   [mscorlib]System.Object
0x3d96b  dup
0x3d96c  ldc.i4.0
0x3d96d  ldarg.2
0x3d96e  box      [mscorlib]System.Guid
0x3d973  stelem.ref
0x3d974  dup
0x3d975  ldc.i4.1
0x3d976  ldarg.1
0x3d977  box      [mscorlib]System.Int32
0x3d97c  stelem.ref
0x3d97d  dup
0x3d97e  ldc.i4.2
0x3d97f  ldarg.s  4
0x3d981  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d986  box      Microsoft.Crm.Platform.ComponentStateNames
0x3d98b  stelem.ref
0x3d98c  dup
0x3d98d  ldc.i4.3
0x3d98e  ldstr    asc_CC16C// ", "
0x3d993  ldloc.2
0x3d994  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x3d999  stelem.ref
0x3d99a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d99f  ldc.i4.0
0x3d9a0  newarr   [mscorlib]System.Object
0x3d9a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x3d9aa  ldarg.0
0x3d9ab  ldarg.1
0x3d9ac  ldarg.2
0x3d9ad  ldarg.3
0x3d9ae  ldarg.s  4
0x3d9b0  ldarg.s  5
0x3d9b2  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.MoveToActiveAndUpdateTransition::HandleInvalidDBState(int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3d9b7  ret
0x3d9b8  ldarg.s  4
0x3d9ba  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d9bf  stloc.0
0x3d9c0  ldc.i4.0
0x3d9c1  stloc.1
0x3d9c2  ldarg.s  4
0x3d9c4  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3d9c9  ldc.i4.1
0x3d9ca  bne.un   loc_3DA53
0x3d9cf  ldarg.s  4
0x3d9d1  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3d9d6  stloc.s  6
0x3d9d8  ldarg.0
0x3d9d9  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3d9de  ldarg.3
0x3d9df  ldloc.s  6
0x3d9e1  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3d9e6  ldarg.s  5
0x3d9e8  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3d9ed  stloc.s  7
0x3d9ef  ldloc.s  7
0x3d9f1  ldloc.s  6
0x3d9f3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3d9f8  ldloc.s  6
0x3d9fa  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3d9ff  ldloc.s  6
0x3da01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3da06  ldloc.s  6
0x3da08  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3da0d  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3da12  ldloc.s  7
0x3da14  ldloc.s  6
0x3da16  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3da1b  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x3da20  ldarg.0
0x3da21  ldarg.0
0x3da22  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3da27  ldloc.s  7
0x3da29  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateFullComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3da2e  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3da33  ldarg.0
0x3da34  ldarg.0
0x3da35  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3da3a  ldloc.s  7
0x3da3c  ldarg.2
0x3da3d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3da42  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::UpdateSolutionIdAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid newSolutionId)
0x3da47  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3da4c  ldc.i4.1
0x3da4d  stloc.1
0x3da4e  br       loc_3DB39
0x3da53  ldarg.s  4
0x3da55  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3da5a  ldc.i4.5
0x3da5b  bne.un.s loc_3DA9B
0x3da5d  ldarg.0
0x3da5e  ldarg.0
0x3da5f  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3da64  ldarg.0
0x3da65  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3da6a  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveTransition::.ctor(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x3da6f  ldarg.1
0x3da70  ldarg.2
0x3da71  ldarg.3
0x3da72  ldarg.s  4
0x3da74  ldarg.s  5
0x3da76  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ConstructChildActionSet(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition transition, int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3da7b  stloc.0
0x3da7c  ldarg.0
0x3da7d  ldarg.0
0x3da7e  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3da83  ldarg.s  4
0x3da85  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3da8a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3da8f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3da94  ldc.i4.1
0x3da95  stloc.1
0x3da96  br       loc_3DB39
0x3da9b  ldarg.s  4
0x3da9d  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3daa2  ldc.i4.s 9
0x3daa4  bne.un.s loc_3DB10
0x3daa6  ldarg.0
0x3daa7  ldarg.0
0x3daa8  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3daad  ldarg.0
0x3daae  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3dab3  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveModifiedToNoneTransition::.ctor(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput input, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory actionFactory)
0x3dab8  ldarg.1
0x3dab9  ldarg.2
0x3daba  ldarg.3
0x3dabb  ldarg.s  4
0x3dabd  ldarg.s  5
0x3dabf  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ConstructChildActionSet(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition transition, int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
  ... truncated ...
```
