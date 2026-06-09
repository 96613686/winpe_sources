# Microsoft.Crm.Platform.SolutionAwareComponents.UninstallDeleteProtectedTransition::ConstructActionSet

- ea: `0x3b010`
- end: `0x3b1a8`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UninstallDeleteProtectedTransition::ConstructActionSet`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callees

- `0x355d0`
- `0x355f0`
- `0x356e0`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x35c10`
- `0x36a10`
- `0x36a20`
- `0x36ed0`
- `0x37a50`
- `0x37a70`
- `0x37dc0`
- `0x37df0`
- `0x37e50`
- `0x37e70`
- `0x3b010`
- `0x3b210`
- `0x3b270`
- `0x66ae0`

## string_xrefs

- `0x3b02b`: `Invalid operation context for transition.  Expected: Uninstall, Received: {0}`
- `0x3b106`: `Uninstall of base solution row where there is some other solution row that share the same publisher must go through UnistallUpdateStateTransition code path.`

## pseudocode

```c

```

## disassembly

```asm
0x3b010  ldarg.0
0x3b011  ldc.i4.1
0x3b012  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidProtection(bool isProtected)
0x3b017  ldarg.s  5
0x3b019  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3b01e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3b023  ldc.i4.2
0x3b024  beq.s    loc_3B05A
0x3b026  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b02b  ldstr    aInvalidOperati_2// "Invalid operation context for transitio"...
0x3b030  ldc.i4.1
0x3b031  newarr   [mscorlib]System.Object
0x3b036  dup
0x3b037  ldc.i4.0
0x3b038  ldarg.s  5
0x3b03a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3b03f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x3b044  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext
0x3b049  stelem.ref
0x3b04a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b04f  ldc.i4   0x80040203
0x3b054  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3b059  throw
0x3b05a  ldarg.0
0x3b05b  ldarg.1
0x3b05c  ldarg.s  4
0x3b05e  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b063  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::UseSentinelRowInBaseSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3b068  brfalse  loc_3B19C
0x3b06d  ldarg.0
0x3b06e  ldarg.1
0x3b06f  ldarg.s  4
0x3b071  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b076  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AllowDeleteBaseSolutionRowAndFakeDeleteInSolutionUpgrade(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3b07b  brfalse  loc_3B19C
0x3b080  ldarg.s  5
0x3b082  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3b087  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3b08c  ldarg.s  4
0x3b08e  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b093  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3b098  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3b09d  brfalse  loc_3B19C
0x3b0a2  ldc.i4.2
0x3b0a3  ldarg.s  4
0x3b0a5  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b0aa  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3b0af  bne.un   loc_3B19C
0x3b0b4  ldc.i4.2
0x3b0b5  ldarg.s  4
0x3b0b7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3b0bc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3b0c1  bgt      loc_3B19C
0x3b0c6  ldarg.0
0x3b0c7  ldarg.s  4
0x3b0c9  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.UninstallDeleteProtectedTransition::GetActivePublishedInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3b0ce  stloc.0
0x3b0cf  ldloc.0
0x3b0d0  brfalse  loc_3B19C
0x3b0d5  ldarg.0
0x3b0d6  ldarg.1
0x3b0d7  ldarg.s  4
0x3b0d9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b0de  ldloca.s 1
0x3b0e0  ldarg.s  5
0x3b0e2  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.UninstallDeleteProtectedTransition::IsParentComponentBaseSolutionEqualToCurrentBaseSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, [out] valuetype [mscorlib]System.Guid& parentSolutionId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b0e7  brtrue   loc_3B19C
0x3b0ec  ldloc.1
0x3b0ed  ldarg.s  4
0x3b0ef  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3b0f4  ldc.i4.1
0x3b0f5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3b0fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3b0ff  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3b104  brfalse.s loc_3B116
0x3b106  ldstr    aUninstallOfBas// "Uninstall of base solution row where th"...
0x3b10b  ldc.i4   0x80040216
0x3b110  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3b115  throw
0x3b116  ldarg.0
0x3b117  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3b11c  ldarg.3
0x3b11d  ldarg.s  4
0x3b11f  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3b124  ldarg.s  5
0x3b126  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3b12b  stloc.2
0x3b12c  ldloc.2
0x3b12d  ldloc.1
0x3b12e  ldc.i4.2
0x3b12f  ldarg.s  4
0x3b131  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b136  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3b13b  ldarg.s  4
0x3b13d  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b142  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3b147  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3b14c  ldarg.0
0x3b14d  ldarg.0
0x3b14e  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3b153  ldarg.s  4
0x3b155  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b15a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3b15f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3b164  ldarg.0
0x3b165  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3b16a  ldloc.2
0x3b16b  ldarg.s  4
0x3b16d  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3b172  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateMergeComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance lastNonOverwrittenInstance)
0x3b177  stloc.3
0x3b178  ldloc.3
0x3b179  isinst   Microsoft.Crm.Platform.SolutionAwareComponents.IPreloadComponentInstanceAction
0x3b17e  stloc.s  4
0x3b180  ldloc.s  4
0x3b182  brfalse.s loc_3B18D
0x3b184  ldloc.s  4
0x3b186  ldarg.s  5
0x3b188  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.IPreloadComponentInstanceAction::PreloadComponentInstance(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b18d  ldarg.0
0x3b18e  ldloc.3
0x3b18f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3b194  ldarg.s  4
0x3b196  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Name()
0x3b19b  ret
0x3b19c  ldarg.0
0x3b19d  ldarg.s  4
0x3b19f  ldarg.s  5
0x3b1a1  ldc.i4.0
0x3b1a2  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::DeleteAllComponentRows(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool skipValidation)
0x3b1a7  ret
```
