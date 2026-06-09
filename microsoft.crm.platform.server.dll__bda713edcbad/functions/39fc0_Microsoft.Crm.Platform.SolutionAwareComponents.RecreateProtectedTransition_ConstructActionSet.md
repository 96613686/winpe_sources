# Microsoft.Crm.Platform.SolutionAwareComponents.RecreateProtectedTransition::ConstructActionSet

- ea: `0x39fc0`
- end: `0x3a0c7`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.RecreateProtectedTransition::ConstructActionSet`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x355f0`
- `0x35680`
- `0x356e0`
- `0x35b40`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35c00`
- `0x36a10`
- `0x36a80`
- `0x37e00`
- `0x37e50`
- `0x39fc0`

## string_xrefs

- `0x39fdb`: `Invalid component state for RecreateProtectedTransition {0}`
- `0x3a03d`: `Invalid number of instances for a RecreateProtectedTransition {0}`

## pseudocode

```c

```

## disassembly

```asm
0x39fc0  ldarg.0
0x39fc1  ldc.i4.2
0x39fc2  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidSolutionOperationContext(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext operationContext)
0x39fc7  ldarg.s  4
0x39fc9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x39fce  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x39fd3  ldc.i4.2
0x39fd4  beq.s    loc_3A00A
0x39fd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39fdb  ldstr    aInvalidCompone_0// "Invalid component state for RecreatePro"...
0x39fe0  ldc.i4.1
0x39fe1  newarr   [mscorlib]System.Object
0x39fe6  dup
0x39fe7  ldc.i4.0
0x39fe8  ldarg.s  4
0x39fea  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x39fef  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x39ff4  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x39ff9  stelem.ref
0x39ffa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39fff  ldc.i4   0x80040203
0x3a004  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a009  throw
0x3a00a  ldnull
0x3a00b  stloc.0
0x3a00c  ldarg.s  4
0x3a00e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3a013  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3a018  ldc.i4.1
0x3a019  ble.s    loc_3A038
0x3a01b  ldarg.s  4
0x3a01d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3a022  ldarg.s  4
0x3a024  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3a029  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3a02e  ldc.i4.2
0x3a02f  sub
0x3a030  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3a035  stloc.0
0x3a036  br.s     loc_3A06C
0x3a038  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a03d  ldstr    aInvalidNumberO// "Invalid number of instances for a Recre"...
0x3a042  ldc.i4.1
0x3a043  newarr   [mscorlib]System.Object
0x3a048  dup
0x3a049  ldc.i4.0
0x3a04a  ldarg.s  4
0x3a04c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3a051  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3a056  box      [mscorlib]System.Int32
0x3a05b  stelem.ref
0x3a05c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a061  ldc.i4   0x80040203
0x3a066  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a06b  throw
0x3a06c  ldloc.0
0x3a06d  ldloc.0
0x3a06e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3a073  ldloc.0
0x3a074  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3a079  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3a07e  ldloc.0
0x3a07f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3a084  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3a089  ldarg.0
0x3a08a  ldarg.0
0x3a08b  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3a090  ldarg.s  4
0x3a092  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3a097  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3a09c  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3a0a1  ldarg.0
0x3a0a2  ldarg.0
0x3a0a3  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3a0a8  ldloc.0
0x3a0a9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3a0ae  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3a0b3  ldarg.s  4
0x3a0b5  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3a0ba  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3a0bf  ldloc.0
0x3a0c0  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3a0c5  or
0x3a0c6  ret
```
