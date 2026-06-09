# Microsoft.Crm.Platform.SolutionAwareComponents.UndeleteInternalHelper::ConstructUndeleteActionSet

- ea: `0x3f170`
- end: `0x3f27e`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UndeleteInternalHelper::ConstructUndeleteActionSet`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x3f0e0`
- `0x3f130`

## callees

- `0x35680`
- `0x35690`
- `0x356e0`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35c00`
- `0x37e00`
- `0x37e50`
- `0x3f170`

## string_xrefs

- `0x3f191`: `Invalid component state for UndeleteAndUpgradeTransition {0}`
- `0x3f1ef`: `Invalid number of instances for a UndeleteAndUpgradeTransition {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3f170  ldarg.3
0x3f171  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3f176  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3f17b  ldc.i4.2
0x3f17c  beq.s    loc_3F1BF
0x3f17e  ldarg.3
0x3f17f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3f184  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3f189  ldc.i4.3
0x3f18a  beq.s    loc_3F1BF
0x3f18c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f191  ldstr    aInvalidCompone_1// "Invalid component state for UndeleteAnd"...
0x3f196  ldc.i4.1
0x3f197  newarr   [mscorlib]System.Object
0x3f19c  dup
0x3f19d  ldc.i4.0
0x3f19e  ldarg.3
0x3f19f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3f1a4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3f1a9  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3f1ae  stelem.ref
0x3f1af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f1b4  ldc.i4   0x80040203
0x3f1b9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3f1be  throw
0x3f1bf  ldnull
0x3f1c0  stloc.0
0x3f1c1  ldarg.3
0x3f1c2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f1c7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3f1cc  ldc.i4.1
0x3f1cd  ble.s    loc_3F1EA
0x3f1cf  ldarg.3
0x3f1d0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f1d5  ldarg.3
0x3f1d6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f1db  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3f1e0  ldc.i4.2
0x3f1e1  sub
0x3f1e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3f1e7  stloc.0
0x3f1e8  br.s     loc_3F21D
0x3f1ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f1ef  ldstr    aInvalidNumberO_0// "Invalid number of instances for a Undel"...
0x3f1f4  ldc.i4.1
0x3f1f5  newarr   [mscorlib]System.Object
0x3f1fa  dup
0x3f1fb  ldc.i4.0
0x3f1fc  ldarg.3
0x3f1fd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f202  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3f207  box      [mscorlib]System.Int32
0x3f20c  stelem.ref
0x3f20d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f212  ldc.i4   0x80040203
0x3f217  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3f21c  throw
0x3f21d  ldloc.0
0x3f21e  ldloc.0
0x3f21f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3f224  ldloc.0
0x3f225  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3f22a  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3f22f  ldloc.0
0x3f230  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3f235  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3f23a  ldarg.s  4
0x3f23c  ldarg.s  5
0x3f23e  ldarg.3
0x3f23f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3f244  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3f249  callvirt instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction>::Invoke(var<u1>)
0x3f24e  ldarg.s  4
0x3f250  ldarg.s  5
0x3f252  ldloc.0
0x3f253  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3f258  callvirt instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction>::Invoke(var<u1>)
0x3f25d  ldarg.3
0x3f25e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f263  ldarg.3
0x3f264  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3f269  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3f26e  ldc.i4.1
0x3f26f  sub
0x3f270  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::RemoveAt(int32)
0x3f275  ldarg.3
0x3f276  ldloc.0
0x3f277  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::set_TopInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance value)
0x3f27c  ldarg.3
0x3f27d  ret
```
