# Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeAddSentinelRowForComponentTransition::ConstructActionSet

- ea: `0x3ef10`
- end: `0x3f070`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeAddSentinelRowForComponentTransition::ConstructActionSet`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x355d0`
- `0x355f0`
- `0x356e0`
- `0x35b40`
- `0x35b80`
- `0x35bc0`
- `0x35c00`
- `0x36a10`
- `0x36a20`
- `0x37a50`
- `0x37ae0`
- `0x37df0`
- `0x37e70`
- `0x3ef10`
- `0x66ae0`

## string_xrefs

- `0x3ef2a`: `Invalid operation context for transition.  Expected: Upgrade, Uninstall, or Install, Received: {0}`
- `0x3ef6e`: `Invalid solution component type ({0}) for transition. Component must use sentinel row for base solution`

## pseudocode

```c

```

## disassembly

```asm
0x3ef10  ldarg.0
0x3ef11  ldc.i4.1
0x3ef12  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidProtection(bool isProtected)
0x3ef17  ldarg.s  5
0x3ef19  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ef1e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3ef23  brtrue.s loc_3EF59
0x3ef25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ef2a  ldstr    aInvalidOperati_6// "Invalid operation context for transitio"...
0x3ef2f  ldc.i4.1
0x3ef30  newarr   [mscorlib]System.Object
0x3ef35  dup
0x3ef36  ldc.i4.0
0x3ef37  ldarg.s  5
0x3ef39  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ef3e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3ef43  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext
0x3ef48  stelem.ref
0x3ef49  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ef4e  ldc.i4   0x80040203
0x3ef53  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3ef58  throw
0x3ef59  ldarg.0
0x3ef5a  ldarg.1
0x3ef5b  ldarg.s  4
0x3ef5d  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3ef62  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::UseSentinelRowInBaseSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3ef67  brtrue.s loc_3EF92
0x3ef69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ef6e  ldstr    aInvalidSolutio_2// "Invalid solution component type ({0}) f"...
0x3ef73  ldc.i4.1
0x3ef74  newarr   [mscorlib]System.Object
0x3ef79  dup
0x3ef7a  ldc.i4.0
0x3ef7b  ldarg.1
0x3ef7c  box      [mscorlib]System.Int32
0x3ef81  stelem.ref
0x3ef82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ef87  ldc.i4   0x80040203
0x3ef8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3ef91  throw
0x3ef92  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ef97  stloc.0
0x3ef98  ldarg.0
0x3ef99  ldarg.1
0x3ef9a  ldarg.s  4
0x3ef9c  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3efa1  ldarg.s  4
0x3efa3  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3efa8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3efad  ldloca.s 0
0x3efaf  ldarg.s  5
0x3efb1  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::IsParentComponentSolutionEqualToSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, valuetype [mscorlib]System.Guid solutionId, [out] valuetype [mscorlib]System.Guid& parentSolutionId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3efb6  brfalse.s loc_3EFC0
0x3efb8  ldarg.s  4
0x3efba  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3efbf  ret
0x3efc0  ldc.i4.0
0x3efc1  stloc.1
0x3efc2  ldarg.s  4
0x3efc4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3efc9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3efce  stloc.s  4
0x3efd0  br.s     loc_3EFF2
0x3efd2  ldloca.s 4
0x3efd4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3efd9  stloc.s  5
0x3efdb  ldloc.s  5
0x3efdd  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3efe2  brfalse.s loc_3EFEE
0x3efe4  ldc.i4.2
0x3efe5  ldloc.s  5
0x3efe7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3efec  bne.un.s loc_3EFF2
0x3efee  ldc.i4.1
0x3efef  stloc.1
0x3eff0  leave.s  loc_3F00B
0x3eff2  ldloca.s 4
0x3eff4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3eff9  brtrue.s loc_3EFD2
0x3effb  leave.s  loc_3F00B
0x3effd  ldloca.s 4
0x3efff  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3f005  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f00a  endfinally
0x3f00b  ldloc.1
0x3f00c  brtrue.s loc_3F016
0x3f00e  ldarg.0
0x3f00f  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeAddSentinelRowForComponentTransition::ZeroTime
0x3f014  br.s     loc_3F01C
0x3f016  ldarg.0
0x3f017  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeAddSentinelRowForComponentTransition::OldTime
0x3f01c  stloc.2
0x3f01d  ldarg.0
0x3f01e  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3f023  ldarg.3
0x3f024  ldarg.s  4
0x3f026  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3f02b  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3f030  ldc.i4.2
0x3f031  or
0x3f032  ldarg.s  5
0x3f034  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f039  stloc.3
0x3f03a  ldloc.3
0x3f03b  ldloc.0
0x3f03c  ldc.i4.2
0x3f03d  ldloc.2
0x3f03e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f043  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3f048  ldarg.0
0x3f049  ldarg.0
0x3f04a  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3f04f  ldloc.3
0x3f050  ldarg.s  4
0x3f052  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3f057  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateMergeComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance lastNonOverwrittenInstance)
0x3f05c  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3f061  ldc.i4.2
0x3f062  ldarg.s  4
0x3f064  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3f069  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3f06e  or
0x3f06f  ret
```
