# Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::ConstructActionSet

- ea: `0x39b20`
- end: `0x39c2e`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::ConstructActionSet`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x355d0`
- `0x35b40`
- `0x35c00`
- `0x35c10`
- `0x36a10`
- `0x37ae0`
- `0x37de0`
- `0x37e70`
- `0x39b20`
- `0x39c30`
- `0x39e50`
- `0x66ae0`
- `0x66ff0`

## string_xrefs

- `0x39b2e`: `Invalid transition for CreateProtectedTransition {0}`
- `0x39b68`: `SolutionLayersToCreate`

## pseudocode

```c

```

## disassembly

```asm
0x39b20  ldarg.s  4
0x39b22  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x39b27  brfalse.s loc_39B58
0x39b29  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39b2e  ldstr    aInvalidTransit_7// "Invalid transition for CreateProtectedT"...
0x39b33  ldc.i4.1
0x39b34  newarr   [mscorlib]System.Object
0x39b39  dup
0x39b3a  ldc.i4.0
0x39b3b  ldarg.s  4
0x39b3d  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x39b42  box      Microsoft.Crm.Platform.ComponentStateNames
0x39b47  stelem.ref
0x39b48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39b4d  ldc.i4   0x80040203
0x39b52  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x39b57  throw
0x39b58  ldarg.s  5
0x39b5a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x39b5f  brfalse.s loc_39B82
0x39b61  ldarg.s  5
0x39b63  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x39b68  ldstr    aSolutionlayers// "SolutionLayersToCreate"
0x39b6d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x39b72  brfalse.s loc_39B82
0x39b74  ldarg.0
0x39b75  ldarg.1
0x39b76  ldarg.2
0x39b77  ldarg.3
0x39b78  ldarg.s  4
0x39b7a  ldarg.s  5
0x39b7c  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::ConstructActionSetForLayering(int32 componentType, valuetype [mscorlib]System.Guid objectId, object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x39b81  ret
0x39b82  ldarg.0
0x39b83  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39b88  ldarg.3
0x39b89  ldarg.0
0x39b8a  ldarg.s  5
0x39b8c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39b91  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::GetComponentStateNames(class [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext context)
0x39b96  ldarg.s  5
0x39b98  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x39b9d  stloc.0
0x39b9e  ldloc.0
0x39b9f  ldarg.s  5
0x39ba1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39ba6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x39bab  ldc.i4.0
0x39bac  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x39bb1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x39bb6  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x39bbb  ldarg.0
0x39bbc  ldarg.1
0x39bbd  ldloc.0
0x39bbe  ldarg.s  5
0x39bc0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39bc5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x39bca  ldloca.s 1
0x39bcc  ldarg.s  5
0x39bce  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::IsParentComponentSolutionEqualToSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, valuetype [mscorlib]System.Guid solutionId, [out] valuetype [mscorlib]System.Guid& parentSolutionId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x39bd3  brtrue.s loc_39C15
0x39bd5  ldarg.0
0x39bd6  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39bdb  ldarg.3
0x39bdc  ldarg.0
0x39bdd  ldarg.s  5
0x39bdf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39be4  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::GetComponentStateNames(class [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext context)
0x39be9  ldarg.s  5
0x39beb  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x39bf0  stloc.2
0x39bf1  ldloc.2
0x39bf2  ldloc.1
0x39bf3  ldc.i4.2
0x39bf4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x39bf9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x39bfe  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x39c03  ldarg.0
0x39c04  ldarg.0
0x39c05  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39c0a  ldloc.2
0x39c0b  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateCreateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x39c10  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x39c15  ldarg.0
0x39c16  ldarg.0
0x39c17  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39c1c  ldloc.0
0x39c1d  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateCreateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x39c22  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x39c27  ldloc.0
0x39c28  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x39c2d  ret
```
