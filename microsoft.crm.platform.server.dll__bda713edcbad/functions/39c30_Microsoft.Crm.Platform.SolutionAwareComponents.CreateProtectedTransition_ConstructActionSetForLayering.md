# Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::ConstructActionSetForLayering

- ea: `0x39c30`
- end: `0x39e4d`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::ConstructActionSetForLayering`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x39b20`

## callees

- `0x35b40`
- `0x35c00`
- `0x36a10`
- `0x37de0`
- `0x37e70`
- `0x39c30`
- `0x39e50`
- `0x66ae0`
- `0x66ff0`

## string_xrefs

- `0x39c39`: `SolutionLayersToCreate`
- `0x39c4c`: `CreatedProctedLayeredTransition::ConstructActionSet, org {0} - the SolutionLayersToCreate InternalContextVariable must be set to use this transition`
- `0x39c80`: `CreatedProctedLayeredTransition::ConstructActionSet, org {0} - Solution operation CreateProtectedLayeredTransition was called with an InternalContextVariable named SolutionLayersToCreate but the type was not a Dictionary<Guid, DateTime> but is instead {1}`
- `0x39ce7`: `CreatedProctedLayeredTransition::ConstructActionSet, org {0} - solution id {1} is a system solution and cannot be provided as a layered solution`
- `0x39d2f`: `CreatedProctedLayeredTransition::ConstructActionSet, org {0} - Solution layer with solution id {1} was provided an OverwriteTime of {2} that is not unique within the given solution layers and therefore is invalid`
- `0x39e19`: `CreatedProctedLayeredTransition::ConstructActionSet, org {0} - No solution layer had an OverwriteTime of {1}, which would lead to invalid solution layering`

## pseudocode

```c

```

## disassembly

```asm
0x39c30  ldnull
0x39c31  stloc.0
0x39c32  ldarg.s  5
0x39c34  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x39c39  ldstr    aSolutionlayers// "SolutionLayersToCreate"
0x39c3e  ldloca.s 0
0x39c40  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x39c45  brtrue.s loc_39C71
0x39c47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39c4c  ldstr    aCreatedprocted// "CreatedProctedLayeredTransition::Constr"...
0x39c51  ldc.i4.1
0x39c52  newarr   [mscorlib]System.Object
0x39c57  dup
0x39c58  ldc.i4.0
0x39c59  ldarg.s  5
0x39c5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x39c60  box      [mscorlib]System.Guid
0x39c65  stelem.ref
0x39c66  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39c6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39c70  throw
0x39c71  ldloc.0
0x39c72  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>
0x39c77  stloc.1
0x39c78  ldloc.1
0x39c79  brtrue.s loc_39CB3
0x39c7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39c80  ldstr    aCreatedprocted_0// "CreatedProctedLayeredTransition::Constr"...
0x39c85  ldc.i4.2
0x39c86  newarr   [mscorlib]System.Object
0x39c8b  dup
0x39c8c  ldc.i4.0
0x39c8d  ldarg.s  5
0x39c8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x39c94  box      [mscorlib]System.Guid
0x39c99  stelem.ref
0x39c9a  dup
0x39c9b  ldc.i4.1
0x39c9c  ldloc.0
0x39c9d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x39ca2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x39ca7  stelem.ref
0x39ca8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39cad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39cb2  throw
0x39cb3  ldc.i4.0
0x39cb4  stloc.2
0x39cb5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.DateTime>::.ctor()
0x39cba  stloc.3
0x39cbb  ldc.i4.0
0x39cbc  stloc.s  4
0x39cbe  ldloc.1
0x39cbf  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::GetEnumerator()
0x39cc4  stloc.s  5
0x39cc6  br       loc_39DF4
0x39ccb  ldloca.s 5
0x39ccd  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Current()
0x39cd2  stloc.s  6
0x39cd4  ldloca.s 6
0x39cd6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Key()
0x39cdb  call     bool [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::IsSystemSolution(valuetype [mscorlib]System.Guid)
0x39ce0  brfalse.s loc_39D1B
0x39ce2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39ce7  ldstr    aCreatedprocted_1// "CreatedProctedLayeredTransition::Constr"...
0x39cec  ldc.i4.2
0x39ced  newarr   [mscorlib]System.Object
0x39cf2  dup
0x39cf3  ldc.i4.0
0x39cf4  ldarg.s  5
0x39cf6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x39cfb  box      [mscorlib]System.Guid
0x39d00  stelem.ref
0x39d01  dup
0x39d02  ldc.i4.1
0x39d03  ldloca.s 6
0x39d05  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Key()
0x39d0a  box      [mscorlib]System.Guid
0x39d0f  stelem.ref
0x39d10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39d15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39d1a  throw
0x39d1b  ldloc.3
0x39d1c  ldloca.s 6
0x39d1e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x39d23  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.DateTime>::Contains(var<u1>)
0x39d28  brfalse.s loc_39D7B
0x39d2a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39d2f  ldstr    aCreatedprocted_2// "CreatedProctedLayeredTransition::Constr"...
0x39d34  ldc.i4.3
0x39d35  newarr   [mscorlib]System.Object
0x39d3a  dup
0x39d3b  ldc.i4.0
0x39d3c  ldarg.s  5
0x39d3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x39d43  box      [mscorlib]System.Guid
0x39d48  stelem.ref
0x39d49  dup
0x39d4a  ldc.i4.1
0x39d4b  ldloca.s 6
0x39d4d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Key()
0x39d52  box      [mscorlib]System.Guid
0x39d57  stelem.ref
0x39d58  dup
0x39d59  ldc.i4.2
0x39d5a  ldloca.s 6
0x39d5c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x39d61  stloc.s  8
0x39d63  ldloca.s 8
0x39d65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39d6a  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x39d6f  stelem.ref
0x39d70  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39d75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39d7a  throw
0x39d7b  ldloca.s 6
0x39d7d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x39d82  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x39d87  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x39d8c  brfalse.s loc_39D91
0x39d8e  ldc.i4.1
0x39d8f  stloc.s  4
0x39d91  ldarg.0
0x39d92  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39d97  ldarg.3
0x39d98  ldarg.0
0x39d99  ldarg.s  5
0x39d9b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39da0  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.CreateProtectedTransition::GetComponentStateNames(class [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext context)
0x39da5  ldarg.s  5
0x39da7  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x39dac  stloc.s  7
0x39dae  ldloc.s  7
0x39db0  ldloca.s 6
0x39db2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Key()
0x39db7  ldc.i4.0
0x39db8  ldloca.s 6
0x39dba  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x39dbf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x39dc4  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x39dc9  ldarg.0
0x39dca  ldarg.0
0x39dcb  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x39dd0  ldloc.s  7
0x39dd2  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateCreateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x39dd7  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x39ddc  ldloc.3
0x39ddd  ldloca.s 6
0x39ddf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x39de4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.DateTime>::Add(var<u1>)
0x39de9  pop
0x39dea  ldloc.2
0x39deb  ldloc.s  7
0x39ded  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x39df2  or
0x39df3  stloc.2
0x39df4  ldloca.s 5
0x39df6  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::MoveNext()
0x39dfb  brtrue   loc_39CCB
0x39e00  leave.s  loc_39E10
0x39e02  ldloca.s 5
0x39e04  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>
0x39e0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39e0f  endfinally
0x39e10  ldloc.s  4
0x39e12  brtrue.s loc_39E4B
0x39e14  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39e19  ldstr    aCreatedprocted_3// "CreatedProctedLayeredTransition::Constr"...
0x39e1e  ldc.i4.2
0x39e1f  newarr   [mscorlib]System.Object
0x39e24  dup
0x39e25  ldc.i4.0
0x39e26  ldarg.s  5
0x39e28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x39e2d  box      [mscorlib]System.Guid
0x39e32  stelem.ref
0x39e33  dup
0x39e34  ldc.i4.1
0x39e35  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x39e3a  box      [mscorlib]System.DateTime
0x39e3f  stelem.ref
0x39e40  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39e45  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39e4a  throw
0x39e4b  ldloc.2
0x39e4c  ret
```
