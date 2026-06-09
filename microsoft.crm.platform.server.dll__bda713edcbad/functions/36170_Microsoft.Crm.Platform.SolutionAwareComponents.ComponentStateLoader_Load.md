# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load

- ea: `0x36170`
- end: `0x362fa`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load`
- size: `394`
- prototype: ``
- caller_count: `19`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x35850`
- `0x35980`
- `0x359f0`
- `0x36850`
- `0x37ae0`
- `0x37bf0`
- `0x3b270`
- `0x44b00`
- `0x44ca0`
- `0x44e00`
- `0x44f00`
- `0x451a0`
- `0x4bde0`
- `0x5b5e0`
- `0x5b740`
- `0x5c450`
- `0x5c920`
- `0x5cb50`
- `0x82070`

## callees

- `0x355e0`
- `0x355f0`
- `0x35600`
- `0x35680`
- `0x35690`
- `0x356e0`
- `0x356f0`
- `0x35700`
- `0x35b40`
- `0x35b80`
- `0x35bc0`
- `0x35be0`
- `0x36170`
- `0x36330`
- `0x36390`

## string_xrefs

- `0x36183`: `Component ID cannot be empty`
- `0x3627b`: `ComponentStateLoader's Load method found an invalid state, all component instances are found to be in Snapshot state with no records with Base state, ComponentType: `

## pseudocode

```c

```

## disassembly

```asm
0x36170  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::.ctor()
0x36175  stloc.0
0x36176  ldarg.2
0x36177  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3617c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x36181  brfalse.s loc_36193
0x36183  ldstr    aComponentIdCan// "Component ID cannot be empty"
0x36188  ldc.i4   0x80040203
0x3618d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x36192  throw
0x36193  ldarg.0
0x36194  ldarg.1
0x36195  ldarg.2
0x36196  ldarg.3
0x36197  ldarg.s  4
0x36199  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::LoadComponentInstancesSortedByOverwriteTime(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3619e  stloc.1
0x3619f  ldloc.1
0x361a0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x361a5  brtrue.s loc_361A9
0x361a7  ldloc.0
0x361a8  ret
0x361a9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x361ae  stloc.2
0x361af  ldloc.1
0x361b0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x361b5  stloc.3
0x361b6  br.s     loc_3620E
0x361b8  ldloca.s 3
0x361ba  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x361bf  stloc.s  4
0x361c1  ldloc.s  4
0x361c3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x361c8  ldc.i4.4
0x361c9  bne.un.s loc_361DF
0x361cb  ldloc.0
0x361cc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_SnapshotSolutionIds()
0x361d1  ldloc.s  4
0x361d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x361d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x361dd  br.s     loc_3620E
0x361df  ldloc.s  4
0x361e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x361e6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x361eb  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x361f0  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x361f5  brfalse.s loc_36201
0x361f7  ldloc.2
0x361f8  ldloc.s  4
0x361fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x361ff  br.s     loc_3620E
0x36201  ldloc.0
0x36202  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x36207  ldloc.s  4
0x36209  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3620e  ldloca.s 3
0x36210  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x36215  brtrue.s loc_361B8
0x36217  leave.s  loc_36227
0x36219  ldloca.s 3
0x3621b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x36221  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36226  endfinally
0x36227  ldarg.0
0x36228  ldloc.2
0x36229  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::SortActiveInstancesByComponentState(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> instances)
0x3622e  ldloc.2
0x3622f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x36234  stloc.3
0x36235  br.s     loc_3624D
0x36237  ldloca.s 3
0x36239  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3623e  stloc.s  5
0x36240  ldloc.0
0x36241  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x36246  ldloc.s  5
0x36248  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3624d  ldloca.s 3
0x3624f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x36254  brtrue.s loc_36237
0x36256  leave.s  loc_36266
0x36258  ldloca.s 3
0x3625a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x36260  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36265  endfinally
0x36266  ldloc.0
0x36267  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3626c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x36271  brtrue.s loc_362AB
0x36273  ldc.i4.4
0x36274  newarr   [mscorlib]System.Object
0x36279  dup
0x3627a  ldc.i4.0
0x3627b  ldstr    aComponentstate_2// "ComponentStateLoader's Load method foun"...
0x36280  stelem.ref
0x36281  dup
0x36282  ldc.i4.1
0x36283  ldarg.1
0x36284  box      [mscorlib]System.Int32
0x36289  stelem.ref
0x3628a  dup
0x3628b  ldc.i4.2
0x3628c  ldstr    aGuid// " Guid: "
0x36291  stelem.ref
0x36292  dup
0x36293  ldc.i4.3
0x36294  ldarg.2
0x36295  box      [mscorlib]System.Guid
0x3629a  stelem.ref
0x3629b  call     string [mscorlib]System.String::Concat(object[])
0x362a0  ldc.i4   0x80040233
0x362a5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x362aa  throw
0x362ab  ldloc.0
0x362ac  ldloc.0
0x362ad  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x362b2  ldc.i4.0
0x362b3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x362b8  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::set_BaseInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance value)
0x362bd  ldloc.0
0x362be  ldloc.0
0x362bf  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x362c4  ldloc.0
0x362c5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x362ca  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x362cf  ldc.i4.1
0x362d0  sub
0x362d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x362d6  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::set_TopInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance value)
0x362db  ldloc.0
0x362dc  ldloc.0
0x362dd  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x362e2  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x362e7  ldloc.0
0x362e8  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x362ed  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x362f2  or
0x362f3  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::set_Name(valuetype Microsoft.Crm.Platform.ComponentStateNames value)
0x362f8  ldloc.0
0x362f9  ret
```
