# Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveTransition::ConstructActionSetInternal

- ea: `0x3ba90`
- end: `0x3bff5`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveTransition::ConstructActionSetInternal`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3ba80`

## callees

- `0x75a0`
- `0x32cb0`
- `0x355d0`
- `0x355f0`
- `0x35680`
- `0x356e0`
- `0x35b20`
- `0x35b40`
- `0x35b60`
- `0x35b70`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`
- `0x35bf0`
- `0x35c00`
- `0x35c10`
- `0x36a10`
- `0x36a20`
- `0x37a90`
- `0x37dc0`
- `0x37df0`
- `0x37e00`
- `0x37e10`
- `0x37e50`
- `0x37e70`
- `0x39780`
- `0x3ba90`
- `0x3c000`
- `0x66ae0`
- `0x7e1b0`

## string_xrefs

- `0x3bd24`: `InvalidStateTransition for LocalizedLabel. ComponentType:{0}, ObjectId:{1}, LabelTypeCode:{2}, CurrentComponentState:{3}, FinalComponentState:{4} in UpdateActiveTransition. The final component state for a MetadataLabelTypeCode should always be Publish.`
- `0x3bd7a`: `InvalidStateTransition for ComponentType:{0}, ObjectId:{1}, CurrentComponentState:{2}, FinalComponentState:{3} in UpdateActiveTransition. The final component state for a MetadataComponent should always be Publish.`
- `0x3bf92`: `You are attempting to update in the active context when there exists an active row, but either the active row has a state other than publish or unpublish\nor you are attempting to do a published update of a publishable component, which is not allowed.  _Input.FinalComponentState: {0}; componentType: {1}; objectId: {2}; CurrentState: {3};`

## pseudocode

```c

```

## disassembly

```asm
0x3ba90  ldarg.0
0x3ba91  ldc.i4.0
0x3ba92  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ThrowIfInvalidProtection(bool isProtected)
0x3ba97  ldarg.0
0x3ba98  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.UpdateActiveTransition::ThrowIfInvalidSolutionOperationContext()
0x3ba9d  ldarg.0
0x3ba9e  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3baa3  ldarg.3
0x3baa4  ldarg.s  4
0x3baa6  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3baab  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x3bab0  ldarg.0
0x3bab1  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bab6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3babb  brfalse.s loc_3BAC0
0x3babd  ldc.i4.8
0x3babe  br.s     loc_3BAC1
0x3bac0  ldc.i4.4
0x3bac1  or
0x3bac2  ldarg.s  5
0x3bac4  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateComponentInstanceFrom(object operationParameter, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3bac9  stloc.0
0x3baca  ldarg.s  4
0x3bacc  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bad1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3bad6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3badb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3bae0  brfalse  loc_3BBCF
0x3bae5  ldarg.0
0x3bae6  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3baeb  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3baf0  brtrue.s loc_3BB48
0x3baf2  ldarg.s  4
0x3baf4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3baf9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3bafe  stloc.1
0x3baff  br.s     loc_3BB2F
0x3bb01  ldloca.s 1
0x3bb03  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x3bb08  stloc.2
0x3bb09  ldloc.2
0x3bb0a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3bb0f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3bb14  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3bb19  brfalse.s loc_3BB2F
0x3bb1b  ldarg.0
0x3bb1c  ldarg.0
0x3bb1d  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3bb22  ldloc.2
0x3bb23  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateDeleteInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3bb28  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3bb2d  leave.s  loc_3BB48
0x3bb2f  ldloca.s 1
0x3bb31  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::MoveNext()
0x3bb36  brtrue.s loc_3BB01
0x3bb38  leave.s  loc_3BB48
0x3bb3a  ldloca.s 1
0x3bb3c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>
0x3bb42  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3bb47  endfinally
0x3bb48  ldarg.0
0x3bb49  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bb4e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bb53  brtrue.s loc_3BB84
0x3bb55  ldarg.s  4
0x3bb57  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bb5c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3bb61  ldc.i4.1
0x3bb62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x3bb67  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_OverwriteTime(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime value)
0x3bb6c  ldarg.0
0x3bb6d  ldarg.0
0x3bb6e  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3bb73  ldarg.s  4
0x3bb75  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bb7a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3bb7f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3bb84  ldloc.0
0x3bb85  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3bb8a  ldarg.0
0x3bb8b  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bb90  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bb95  brfalse.s loc_3BB9A
0x3bb97  ldc.i4.1
0x3bb98  br.s     loc_3BB9B
0x3bb9a  ldc.i4.0
0x3bb9b  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3bba0  ldarg.s  4
0x3bba2  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bba7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3bbac  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3bbb1  ldarg.0
0x3bbb2  ldarg.0
0x3bbb3  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3bbb8  ldloc.0
0x3bbb9  ldarg.s  4
0x3bbbb  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bbc0  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateMergeComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance lastNonOverwrittenInstance)
0x3bbc5  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3bbca  br       loc_3BFE6
0x3bbcf  ldarg.s  4
0x3bbd1  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bbd6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bbdb  ldc.i4.1
0x3bbdc  beq.s    loc_3BBF9
0x3bbde  ldarg.s  4
0x3bbe0  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bbe5  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bbea  brtrue.s loc_3BC58
0x3bbec  ldarg.0
0x3bbed  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bbf2  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bbf7  brtrue.s loc_3BC58
0x3bbf9  ldloc.0
0x3bbfa  ldarg.s  4
0x3bbfc  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc01  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3bc06  ldarg.s  4
0x3bc08  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc0d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bc12  ldarg.s  4
0x3bc14  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc19  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3bc1e  ldarg.s  4
0x3bc20  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc25  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3bc2a  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3bc2f  ldloc.0
0x3bc30  ldarg.s  4
0x3bc32  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc37  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3bc3c  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x3bc41  ldarg.0
0x3bc42  ldarg.0
0x3bc43  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3bc48  ldloc.0
0x3bc49  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateFullComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3bc4e  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3bc53  br       loc_3BFE6
0x3bc58  ldarg.s  4
0x3bc5a  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc5f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bc64  ldc.i4.3
0x3bc65  bne.un.s loc_3BCC9
0x3bc67  ldarg.0
0x3bc68  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bc6d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bc72  ldc.i4.1
0x3bc73  bne.un.s loc_3BCC9
0x3bc75  ldloc.0
0x3bc76  ldarg.s  4
0x3bc78  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc7d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3bc82  ldc.i4.1
0x3bc83  ldarg.s  4
0x3bc85  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x3bc8f  ldarg.s  4
0x3bc91  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bc96  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3bc9b  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3bca0  ldloc.0
0x3bca1  ldarg.s  4
0x3bca3  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bca8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x3bcad  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x3bcb2  ldarg.0
0x3bcb3  ldarg.0
0x3bcb4  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3bcb9  ldloc.0
0x3bcba  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateUpdateFullComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3bcbf  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3bcc4  br       loc_3BFE6
0x3bcc9  ldarg.s  4
0x3bccb  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bcd0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bcd5  brtrue   loc_3BE1A
0x3bcda  ldarg.0
0x3bcdb  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bce0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bce5  ldc.i4.1
0x3bce6  bne.un   loc_3BE1A
0x3bceb  ldarg.1
0x3bcec  call     bool Microsoft.Crm.Solution.SolutionComponentTypeMap::IsMetadata(int32 componentType)
0x3bcf1  brfalse  loc_3BDDF
0x3bcf6  ldsfld   string [mscorlib]System.String::Empty
0x3bcfb  stloc.3
0x3bcfc  ldarg.1
0x3bcfd  ldc.i4.7
0x3bcfe  bne.un.s loc_3BD7A
0x3bd00  ldarg.s  4
0x3bd02  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bd07  ldstr    aLabeltypecode// "labeltypecode"
0x3bd0c  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3bd11  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x3bd16  stloc.s  4
0x3bd18  ldloc.s  4
0x3bd1a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCodeHelper::IsMetadataLabelTypeCode(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode)
0x3bd1f  brfalse  loc_3BDC4
0x3bd24  ldstr    aInvalidstatetr// "InvalidStateTransition for LocalizedLab"...
0x3bd29  ldc.i4.5
0x3bd2a  newarr   [mscorlib]System.Object
0x3bd2f  dup
0x3bd30  ldc.i4.0
0x3bd31  ldarg.1
0x3bd32  box      [mscorlib]System.Int32
0x3bd37  stelem.ref
0x3bd38  dup
0x3bd39  ldc.i4.1
0x3bd3a  ldarg.2
0x3bd3b  box      [mscorlib]System.Guid
0x3bd40  stelem.ref
0x3bd41  dup
0x3bd42  ldc.i4.2
0x3bd43  ldloc.s  4
0x3bd45  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x3bd4a  stelem.ref
0x3bd4b  dup
0x3bd4c  ldc.i4.3
0x3bd4d  ldarg.s  4
0x3bd4f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bd54  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bd59  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3bd5e  stelem.ref
0x3bd5f  dup
0x3bd60  ldc.i4.4
0x3bd61  ldarg.0
0x3bd62  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bd67  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bd6c  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3bd71  stelem.ref
0x3bd72  call     string [mscorlib]System.String::Format(string, object[])
0x3bd77  stloc.3
0x3bd78  br.s     loc_3BDC4
0x3bd7a  ldstr    aInvalidstatetr_0// "InvalidStateTransition for ComponentTyp"...
0x3bd7f  ldc.i4.4
0x3bd80  newarr   [mscorlib]System.Object
0x3bd85  dup
0x3bd86  ldc.i4.0
0x3bd87  ldarg.1
0x3bd88  box      [mscorlib]System.Int32
0x3bd8d  stelem.ref
0x3bd8e  dup
0x3bd8f  ldc.i4.1
0x3bd90  ldarg.2
0x3bd91  box      [mscorlib]System.Guid
0x3bd96  stelem.ref
0x3bd97  dup
0x3bd98  ldc.i4.2
0x3bd99  ldarg.s  4
0x3bd9b  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bda0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3bda5  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3bdaa  stelem.ref
0x3bdab  dup
0x3bdac  ldc.i4.3
0x3bdad  ldarg.0
0x3bdae  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bdb3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::get_FinalComponentState()
0x3bdb8  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x3bdbd  stelem.ref
0x3bdbe  call     string [mscorlib]System.String::Format(string, object[])
0x3bdc3  stloc.3
0x3bdc4  ldloc.3
0x3bdc5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bdca  brtrue.s loc_3BDDF
0x3bdcc  ldarg.s  5
0x3bdce  ldloc.3
0x3bdcf  ldarg.0
0x3bdd0  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_input
0x3bdd5  callvirt instance string [mscorlib]System.Object::ToString()
0x3bdda  call     void Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::InvalidStateTransition(class Microsoft.Crm.BusinessEntities.ExecutionContext context, string errorMessage, string cstInput)
0x3bddf  ldloc.0
0x3bde0  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3bde5  ldc.i4.1
0x3bde6  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x3bdeb  ldarg.s  4
0x3bded  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3bdf2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x3bdf7  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::SetComponentInstanceSolutionFields(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState state, valuetype [mscorlib]System.DateTime overwriteTime, valuetype [mscorlib]System.Guid supportingSolutionId)
0x3bdfc  ldarg.0
0x3bdfd  ldarg.0
0x3bdfe  ldfld    class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::_actionFactory
0x3be03  ldloc.0
0x3be04  ldarg.s  4
0x3be06  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x3be0b  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionActionFactory::CreateMergeComponentInstanceAction(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance lastNonOverwrittenInstance)
0x3be10  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AddStep(class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction action)
0x3be15  br       loc_3BFE6
0x3be1a  ldarg.0
0x3be1b  ldarg.1
0x3be1c  ldarg.s  4
0x3be1e  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x3be23  call     instance bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AllowRecreateForLogicallyDeletedRowInActiveSolution(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3be28  brfalse  loc_3BF12
0x3be2d  ldarg.s  4
0x3be2f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x3be34  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x3be39  stloc.1
0x3be3a  br.s     loc_3BEAB
  ... truncated ...
```
