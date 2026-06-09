# Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedStagedTransition::ConstructActionSet

- ea: `0x3e4e0`
- end: `0x3ebd8`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedStagedTransition::ConstructActionSet`
- size: `1784`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

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
- `0x3e4e0`
- `0x3ebe0`
- `0x66ae0`
- `0x670c0`

## string_xrefs

- `0x3e521`: `When doing an update during system install or upgrade the base instance must be the system component.  Current base solution id: {0}  Component Type:{1}  Object Id:{2}  Business Component State(Base Instance):{3}  Business Component State(Top Instance):{4}`
- `0x3e617`: `There should not be more than one component instance for a solution being upgraded.  Solution id: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3e4e0  ldnull
0x3e4e1  stloc.0
0x3e4e2  ldc.i4.0
0x3e4e3  stloc.1
0x3e4e4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x3e4e9  stloc.2
0x3e4ea  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x3e4ef  stloc.3
0x3e4f0  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x3e4f5  ldarg.s  5
0x3e4f7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e4fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3e501  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e506  brfalse  loc_3E5E0
0x3e50b  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x3e510  ldarg.s  4
0x3e512  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e517  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e51c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e521  ldstr    aWhenDoingAnUpd// "When doing an update during system inst"...
0x3e526  ldc.i4.5
0x3e527  newarr   [mscorlib]System.Object
0x3e52c  dup
0x3e52d  ldc.i4.0
0x3e52e  ldarg.s  4
0x3e530  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e535  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e53a  box      [mscorlib]System.Guid
0x3e53f  stelem.ref
0x3e540  dup
0x3e541  ldc.i4.1
0x3e542  ldarg.1
0x3e543  box      [mscorlib]System.Int32
0x3e548  stelem.ref
0x3e549  dup
0x3e54a  ldc.i4.2
0x3e54b  ldarg.2
0x3e54c  box      [mscorlib]System.Guid
0x3e551  stelem.ref
0x3e552  dup
0x3e553  ldc.i4.3
0x3e554  ldarg.s  4
0x3e556  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e55b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3e560  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3e565  stelem.ref
0x3e566  dup
0x3e567  ldc.i4.4
0x3e568  ldarg.s  4
0x3e56a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3e56f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3e574  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3e579  stelem.ref
0x3e57a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x3e57f  ldarg.s  4
0x3e581  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e586  stloc.0
0x3e587  ldarg.s  4
0x3e589  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e58e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3e593  stloc.s  4
0x3e595  br.s     loc_3E5C4
0x3e597  ldloca.s 4
0x3e599  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3e59e  stloc.s  5
0x3e5a0  ldloc.s  5
0x3e5a2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3e5a7  ldloc.0
0x3e5a8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3e5ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e5b2  brfalse.s loc_3E5C4
0x3e5b4  ldloc.2
0x3e5b5  ldloc.s  5
0x3e5b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3e5bc  ldloc.3
0x3e5bd  ldloc.s  5
0x3e5bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3e5c4  ldloca.s 4
0x3e5c6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3e5cb  brtrue.s loc_3E597
0x3e5cd  leave    loc_3E666
0x3e5d2  ldloca.s 4
0x3e5d4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3e5da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e5df  endfinally
0x3e5e0  ldarg.s  4
0x3e5e2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e5e7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3e5ec  stloc.s  4
0x3e5ee  br.s     loc_3E64D
0x3e5f0  ldloca.s 4
0x3e5f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3e5f7  stloc.s  6
0x3e5f9  ldloc.s  6
0x3e5fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e600  ldarg.s  5
0x3e602  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e607  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3e60c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e611  brfalse.s loc_3E640
0x3e613  ldloc.0
0x3e614  ldnull
0x3e615  ceq
0x3e617  ldstr    aThereShouldNot// "There should not be more than one compo"...
0x3e61c  ldc.i4.1
0x3e61d  newarr   [mscorlib]System.Object
0x3e622  dup
0x3e623  ldc.i4.0
0x3e624  ldarg.s  5
0x3e626  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e62b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3e630  box      [mscorlib]System.Guid
0x3e635  stelem.ref
0x3e636  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x3e63b  ldloc.s  6
0x3e63d  stloc.0
0x3e63e  br.s     loc_3E64D
0x3e640  ldloc.0
0x3e641  brfalse.s loc_3E64D
0x3e643  ldloc.3
0x3e644  ldloc.s  6
0x3e646  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x3e64b  ldc.i4.1
0x3e64c  stloc.1
0x3e64d  ldloca.s 4
0x3e64f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3e654  brtrue.s loc_3E5F0
0x3e656  leave.s  loc_3E666
0x3e658  ldloca.s 4
0x3e65a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3e660  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e665  endfinally
0x3e666  ldloc.0
0x3e667  brtrue   loc_3E96D
0x3e66c  ldc.i4.1
0x3e66d  stloc.s  7
0x3e66f  ldc.i4.0
0x3e670  stloc.s  8
0x3e672  ldarg.s  5
0x3e674  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x3e679  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x3e67e  ldc.i4.s 0x41
0x3e680  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x3e685  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x3e68a  brfalse.s loc_3E6B7
0x3e68c  ldarg.s  4
0x3e68e  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e693  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e698  ldarg.s  5
0x3e69a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e69f  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::IsBaseInstancePublisherShared(valuetype [mscorlib]System.Guid baseSolutionId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3e6a4  brfalse.s loc_3E6B7
0x3e6a6  ldarg.s  5
0x3e6a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e6ad  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_OverwriteUnmanagedCustomizations()
0x3e6b2  ldc.i4.0
0x3e6b3  ceq
0x3e6b5  stloc.s  8
0x3e6b7  ldnull
0x3e6b8  stloc.s  9
0x3e6ba  ldloc.s  8
0x3e6bc  brfalse.s loc_3E6E5
0x3e6be  ldarg.0
0x3e6bf  ldarg.s  4
0x3e6c1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::GetLastActivePublishedOrDeletedInstance(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3e6c6  stloc.s  9
0x3e6c8  ldloc.s  9
0x3e6ca  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e6cf  ldarg.s  4
0x3e6d1  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e6d6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e6db  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e6e0  brfalse.s loc_3E6E5
0x3e6e2  ldc.i4.0
0x3e6e3  stloc.s  7
0x3e6e5  ldloc.s  7
0x3e6e7  brfalse.s loc_3E6F3
0x3e6e9  ldarg.0
0x3e6ea  ldarg.s  4
0x3e6ec  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::DeleteUnpublishedRow(class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState)
0x3e6f1  stloc.s  9
0x3e6f3  ldarg.1
0x3e6f4  ldc.i4.7
0x3e6f5  bne.un   loc_3E787
0x3e6fa  ldarg.s  4
0x3e6fc  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3e701  ldstr    aLabeltypecode// "labeltypecode"
0x3e706  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3e70b  unbox.any [mscorlib]System.Int32
0x3e710  stloc.s  0xE
0x3e712  ldc.i4.s 0x12
0x3e714  ldloc.s  0xE
0x3e716  bne.un.s loc_3E728
0x3e718  ldarg.s  4
0x3e71a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e71f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e724  stloc.s  0xD
0x3e726  br.s     loc_3E75F
0x3e728  ldarg.0
0x3e729  ldarg.2
0x3e72a  ldarg.s  4
0x3e72c  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3e731  ldstr    aLabeltypecode// "labeltypecode"
0x3e736  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3e73b  unbox.any [mscorlib]System.Int32
0x3e740  ldarg.s  4
0x3e742  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e747  ldstr    aObjectid// "objectid"
0x3e74c  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3e751  unbox.any [mscorlib]System.Guid
0x3e756  ldarg.s  5
0x3e758  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::RetrieveParentBaseSolutionForLabel(valuetype [mscorlib]System.Guid labelId, int32 labelTypeCode, valuetype [mscorlib]System.Guid objectId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3e75d  stloc.s  0xD
0x3e75f  ldloc.s  0xD
0x3e761  ldarg.s  5
0x3e763  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e768  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3e76d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e772  brfalse.s loc_3E787
0x3e774  ldarg.0
0x3e775  ldarg.3
0x3e776  ldloc.s  9
0x3e778  ldarg.s  4
0x3e77a  ldarg.s  5
0x3e77c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e781  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.UpgradeProtectedStagedTransition::HandleLocalizedLabelCreatedByDifferentSolution(object operationParameter, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance activeInstance, class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState currentState, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3e786  ret
0x3e787  ldloc.s  7
0x3e789  brfalse.s loc_3E7AE
0x3e78b  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3e790  stloc.s  0xA
0x3e792  ldloc.s  9
0x3e794  stloc.s  0xB
0x3e796  ldarg.0
0x3e797  ldloc.s  9
0x3e799  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3e79e  ldc.i4.1
0x3e79f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x3e7a4  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::SetInstanceOverwriteTime(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime)
0x3e7a9  br       loc_3E91F
0x3e7ae  ldarg.s  4
0x3e7b0  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3e7b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3e7ba  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x3e7bf  stloc.s  0xF
0x3e7c1  ldloca.s 0xF
0x3e7c3  ldc.r8   1.0
0x3e7cc  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e7d1  stloc.s  0xA
0x3e7d3  ldc.i4.1
0x3e7d4  stloc.s  0x10
0x3e7d6  br       loc_3E903
0x3e7db  ldloc.s  0xA
0x3e7dd  ldarg.s  4
0x3e7df  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e7e4  ldloc.s  0x10
0x3e7e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3e7eb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3e7f0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x3e7f5  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3e7fa  brfalse  loc_3E916
0x3e7ff  ldarg.s  4
0x3e801  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e806  ldloc.s  0x10
0x3e808  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3e80d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3e812  ldarg.s  5
0x3e814  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3e819  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateHelper::IsBaseInstancePublisherShared(valuetype [mscorlib]System.Guid baseSolutionId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x3e81e  brfalse.s loc_3E837
0x3e820  ldloca.s 0xA
0x3e822  ldc.r8   1.0
0x3e82b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e830  stloc.s  0xA
0x3e832  br       loc_3E8FD
0x3e837  newobj   instance void class [System]System.Collections.Generic.Stack`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime>>::.ctor()
0x3e83c  stloc.s  0x11
0x3e83e  ldloc.s  0xA
0x3e840  stloc.s  0x12
0x3e842  br.s     loc_3E88B
0x3e844  ldloc.s  0x11
0x3e846  ldarg.s  4
0x3e848  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3e84d  ldloc.s  0x10
0x3e84f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x3e854  ldloca.s 0x12
0x3e856  ldc.r8   1.0
0x3e85f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e864  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x3e869  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime>::.ctor(var<u1>, !!T0)
0x3e86e  callvirt instance void class [System]System.Collections.Generic.Stack`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime>>::Push(var<u1>)
0x3e873  ldloca.s 0x12
0x3e875  ldc.r8   1.0
0x3e87e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x3e883  stloc.s  0x12
0x3e885  ldloc.s  0x10
0x3e887  ldc.i4.1
0x3e888  add
0x3e889  stloc.s  0x10
0x3e88b  ldloc.s  0x10
  ... truncated ...
```
