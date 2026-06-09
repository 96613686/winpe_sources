# Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedTransition::ConstructActionSet

- ea: `0x3dd90`
- end: `0x3e3e9`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedTransition::ConstructActionSet`
- size: `1625`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3f0e0`

## callees

- `0x355d0`
- `0x355f0`
- `0x35680`
- `0x356e0`
- `0x35ae0`
- `0x35b20`
- `0x35b40`
- `0x35b60`
- `0x35b70`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x35c00`
- `0x35c10`
- `0x35c20`
- `0x36a10`
- `0x36ad0`
- `0x36cc0`
- `0x36ce0`
- `0x36d20`
- `0x36d90`
- `0x36db0`
- `0x378e0`
- `0x37910`
- `0x37940`
- `0x37bf0`
- `0x37df0`
- `0x37e10`
- `0x37e20`
- `0x37e30`
- `0x37e50`
- `0x37e70`
- `0x3dd90`
- `0x3e3f0`
- `0x3e4b0`
- `0x66ae0`
- `0x670c0`
- `0x7e120`

## string_xrefs

- `0x3ddda`: `When doing an update during system install or upgrade the base instance must be the system component.  Current base solution id: {0}  Component Type:{1}  Object Id:{2}  Business Component State(Base Instance):{3}  Business Component State(Top Instance):{4}`
- `0x3ded0`: `There should not be more than one component instance for a solution being upgraded.  Solution id: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3dd90  ldnull
0x3dd91  stloc.0
0x3dd92  ldc.i4.0
0x3dd93  stloc.1
0x3dd94  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x3dd99  stloc.2
0x3dd9a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x3dd9f  stloc.3
0x3dda0  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x3dda5  ldarg.s  5
0x3dda7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3ddac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3ddb1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3ddb6  brfalse  loc_3DE99
0x3ddbb  ldarg.s  5
0x3ddbd  call     bool Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3ddc2  brtrue.s loc_3DE38
0x3ddc4  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x3ddc9  ldarg.s  4
0x3ddcb  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3ddd0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3ddd5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3ddda  ldstr    aWhenDoingAnUpd// "When doing an update during system inst"...
0x3dddf  ldc.i4.5
0x3dde0  newarr   [mscorlib]System.Object
0x3dde5  dup
0x3dde6  ldc.i4.0
0x3dde7  ldarg.s  4
0x3dde9  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3ddee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3ddf3  box      [mscorlib]System.Guid
0x3ddf8  stelem.ref
0x3ddf9  dup
0x3ddfa  ldc.i4.1
0x3ddfb  ldarg.1
0x3ddfc  box      [mscorlib]System.Int32
0x3de01  stelem.ref
0x3de02  dup
0x3de03  ldc.i4.2
0x3de04  ldarg.2
0x3de05  box      [mscorlib]System.Guid
0x3de0a  stelem.ref
0x3de0b  dup
0x3de0c  ldc.i4.3
0x3de0d  ldarg.s  4
0x3de0f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3de14  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3de19  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3de1e  stelem.ref
0x3de1f  dup
0x3de20  ldc.i4.4
0x3de21  ldarg.s  4
0x3de23  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3de28  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3de2d  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3de32  stelem.ref
0x3de33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x3de38  ldarg.s  4
0x3de3a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3de3f  stloc.0
0x3de40  ldarg.s  4
0x3de42  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3de47  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3de4c  stloc.s  4
0x3de4e  br.s     loc_3DE7D
0x3de50  ldloca.s 4
0x3de52  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3de57  stloc.s  5
0x3de59  ldloc.s  5
0x3de5b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3de60  ldloc.0
0x3de61  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3de66  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3de6b  brfalse.s loc_3DE7D
0x3de6d  ldloc.2
0x3de6e  ldloc.s  5
0x3de70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3de75  ldloc.3
0x3de76  ldloc.s  5
0x3de78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3de7d  ldloca.s 4
0x3de7f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3de84  brtrue.s loc_3DE50
0x3de86  leave    loc_3DF1F
0x3de8b  ldloca.s 4
0x3de8d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3de93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3de98  endfinally
0x3de99  ldarg.s  4
0x3de9b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3dea0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3dea5  stloc.s  4
0x3dea7  br.s     loc_3DF06
0x3dea9  ldloca.s 4
0x3deab  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3deb0  stloc.s  6
0x3deb2  ldloc.s  6
0x3deb4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3deb9  ldarg.s  5
0x3debb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3dec0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3dec5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3deca  brfalse.s loc_3DEF9
0x3decc  ldloc.0
0x3decd  ldnull
0x3dece  ceq
0x3ded0  ldstr    aThereShouldNot// "There should not be more than one compo"...
0x3ded5  ldc.i4.1
0x3ded6  newarr   [mscorlib]System.Object
0x3dedb  dup
0x3dedc  ldc.i4.0
0x3dedd  ldarg.s  5
0x3dedf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3dee4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3dee9  box      [mscorlib]System.Guid
0x3deee  stelem.ref
0x3deef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x3def4  ldloc.s  6
0x3def6  stloc.0
0x3def7  br.s     loc_3DF06
0x3def9  ldloc.0
0x3defa  brfalse.s loc_3DF06
0x3defc  ldloc.3
0x3defd  ldloc.s  6
0x3deff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3df04  ldc.i4.1
0x3df05  stloc.1
0x3df06  ldloca.s 4
0x3df08  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3df0d  brtrue.s loc_3DEA9
0x3df0f  leave.s  loc_3DF1F
0x3df11  ldloca.s 4
0x3df13  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3df19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3df1e  endfinally
0x3df1f  ldloc.0
0x3df20  brtrue   loc_3E166
0x3df25  ldc.i4.1
0x3df26  stloc.s  7
0x3df28  ldc.i4.0
0x3df29  stloc.s  8
0x3df2b  ldarg.s  5
0x3df2d  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x3df32  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x3df37  ldc.i4.s 0x41
0x3df39  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x3df3e  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x3df43  brfalse.s loc_3DF79
0x3df45  ldarg.s  4
0x3df47  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3df4c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3df51  ldarg.s  5
0x3df53  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3df58  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::IsBaseInstancePublisherShared(valuetype [mscorlib]System.Guid baseSolutionId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3df5d  brfalse.s loc_3DF79
0x3df5f  ldarg.0
0x3df60  ldarg.1
0x3df61  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedTransition::IsMergeEnabledComponent(int32 componentType)
0x3df66  brtrue.s loc_3DF79
0x3df68  ldarg.s  5
0x3df6a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3df6f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_OverwriteUnmanagedCustomizations()
0x3df74  ldc.i4.0
0x3df75  ceq
0x3df77  stloc.s  8
0x3df79  ldnull
0x3df7a  stloc.s  9
0x3df7c  ldloc.s  8
0x3df7e  brfalse.s loc_3DFA7
0x3df80  ldarg.0
0x3df81  ldarg.s  4
0x3df83  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::GetLastActivePublishedOrDeletedInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3df88  stloc.s  9
0x3df8a  ldloc.s  9
0x3df8c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3df91  ldarg.s  4
0x3df93  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3df98  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3df9d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3dfa2  brfalse.s loc_3DFA7
0x3dfa4  ldc.i4.0
0x3dfa5  stloc.s  7
0x3dfa7  ldloc.s  7
0x3dfa9  brfalse.s loc_3DFB5
0x3dfab  ldarg.0
0x3dfac  ldarg.s  4
0x3dfae  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::DeleteUnpublishedRow(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3dfb3  stloc.s  9
0x3dfb5  ldarg.1
0x3dfb6  ldc.i4.7
0x3dfb7  bne.un   loc_3E049
0x3dfbc  ldarg.s  4
0x3dfbe  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3dfc3  ldstr    aLabeltypecode// "labeltypecode"
0x3dfc8  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3dfcd  unbox.any [mscorlib]System.Int32
0x3dfd2  stloc.s  0xE
0x3dfd4  ldc.i4.s 0x12
0x3dfd6  ldloc.s  0xE
0x3dfd8  bne.un.s loc_3DFEA
0x3dfda  ldarg.s  4
0x3dfdc  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3dfe1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3dfe6  stloc.s  0xD
0x3dfe8  br.s     loc_3E021
0x3dfea  ldarg.0
0x3dfeb  ldarg.2
0x3dfec  ldarg.s  4
0x3dfee  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3dff3  ldstr    aLabeltypecode// "labeltypecode"
0x3dff8  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3dffd  unbox.any [mscorlib]System.Int32
0x3e002  ldarg.s  4
0x3e004  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e009  ldstr    aObjectid// "objectid"
0x3e00e  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3e013  unbox.any [mscorlib]System.Guid
0x3e018  ldarg.s  5
0x3e01a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::RetrieveParentBaseSolutionForLabel(valuetype [mscorlib]System.Guid labelId, int32 labelTypeCode, valuetype [mscorlib]System.Guid objectId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3e01f  stloc.s  0xD
0x3e021  ldloc.s  0xD
0x3e023  ldarg.s  5
0x3e025  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e02a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3e02f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e034  brfalse.s loc_3E049
0x3e036  ldarg.0
0x3e037  ldarg.3
0x3e038  ldloc.s  9
0x3e03a  ldarg.s  4
0x3e03c  ldarg.s  5
0x3e03e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e043  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedTransition::HandleLocalizedLabelCreatedByDifferentSolution(object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance activeInstance, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3e048  ret
0x3e049  ldloc.s  7
0x3e04b  brfalse.s loc_3E070
0x3e04d  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3e052  stloc.s  0xA
0x3e054  ldloc.s  9
0x3e056  stloc.s  0xB
0x3e058  ldarg.0
0x3e059  ldloc.s  9
0x3e05b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3e060  ldc.i4.1
0x3e061  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x3e066  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::SetInstanceOverwriteTime(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime)
0x3e06b  br       loc_3E11D
0x3e070  ldarg.s  4
0x3e072  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e077  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3e07c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x3e081  stloc.s  0xF
0x3e083  ldloca.s 0xF
0x3e085  ldc.r8   1.0
0x3e08e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e093  stloc.s  0xA
0x3e095  ldc.i4.1
0x3e096  stloc.s  0x10
0x3e098  br.s     loc_3E104
0x3e09a  ldloc.s  0xA
0x3e09c  ldarg.s  4
0x3e09e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e0a3  ldloc.s  0x10
0x3e0a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3e0aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3e0af  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x3e0b4  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3e0b9  brfalse.s loc_3E114
0x3e0bb  ldarg.s  4
0x3e0bd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e0c2  ldloc.s  0x10
0x3e0c4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3e0c9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e0ce  ldarg.s  5
0x3e0d0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e0d5  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::IsBaseInstancePublisherShared(valuetype [mscorlib]System.Guid baseSolutionId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3e0da  brfalse.s loc_3E0F0
0x3e0dc  ldloca.s 0xA
0x3e0de  ldc.r8   1.0
0x3e0e7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e0ec  stloc.s  0xA
0x3e0ee  br.s     loc_3E0FE
0x3e0f0  ldarg.0
0x3e0f1  ldarg.s  4
0x3e0f3  ldloc.s  0xA
0x3e0f5  ldloc.s  0x10
0x3e0f7  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::IncerementOverwriteTimeForConflictingRows(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, valuetype [mscorlib]System.DateTime instanceOverwriteTime, int32 index)
0x3e0fc  br.s     loc_3E114
0x3e0fe  ldloc.s  0x10
0x3e100  ldc.i4.1
0x3e101  add
0x3e102  stloc.s  0x10
0x3e104  ldloc.s  0x10
0x3e106  ldarg.s  4
0x3e108  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e10d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x3e112  blt.s    loc_3E09A
0x3e114  ldarg.s  4
0x3e116  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e11b  stloc.s  0xB
  ... truncated ...
```
