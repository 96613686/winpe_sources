# Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RemoveDependenciesForUninstall

- ea: `0x1a6290`
- end: `0x1a657a`
- name: `Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RemoveDependenciesForUninstall`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18ff10`

## callees

- `0x1913c0`
- `0x1a5fb0`
- `0x1a6290`
- `0x1a6580`
- `0x1a65b0`
- `0x1a6640`
- `0x1a66d0`
- `0x1a67a0`
- `0x1a6820`

## string_xrefs

- `0x1a64d7`: `configuration`
- `0x1a6315`: `requiredcomponentobjectid`
- `0x1a6476`: `dependentcomponentobjectid`
- `0x1a648b`: `dependentcomponentobjectid`
- `0x1a62ff`: `dependentcomponenttype`
- `0x1a6452`: `dependentcomponenttype`
- `0x1a62a5`: `isDeleteAndPromote`

## pseudocode

```c

```

## disassembly

```asm
0x1a6290  ldarg.1
0x1a6291  brfalse.s loc_1A629B
0x1a6293  ldarg.1
0x1a6294  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1a6299  brtrue.s loc_1A629D
0x1a629b  ldarg.1
0x1a629c  ret
0x1a629d  nop
0x1a629e  ldarg.s  4
0x1a62a0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x1a62a5  ldstr    aIsdeleteandpro_0// "isDeleteAndPromote"
0x1a62aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1a62af  call     bool [mscorlib]System.Convert::ToBoolean(object)
0x1a62b4  brfalse  loc_1A6359
0x1a62b9  newobj   instance void Microsoft.Crm.ObjectModel.SolutionService::.ctor()
0x1a62be  ldarg.3
0x1a62bf  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string)
0x1a62c4  ldarg.s  4
0x1a62c6  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Crm.ObjectModel.SolutionServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrieveSolutionId(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a62cb  stloc.2
0x1a62cc  ldarg.0
0x1a62cd  ldarg.2
0x1a62ce  ldloc.2
0x1a62cf  ldarg.s  4
0x1a62d1  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::GetSurvivingPluginTypeIds(valuetype [mscorlib]System.Guid uninstallingSolutionId, valuetype [mscorlib]System.Guid upgradingSolutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a62d6  stloc.3
0x1a62d7  ldarg.s  4
0x1a62d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a62de  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(valuetype [mscorlib]System.Guid)
0x1a62e3  stloc.s  4
0x1a62e5  ldarg.1
0x1a62e6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1a62eb  stloc.s  5
0x1a62ed  br.s     loc_1A6335
0x1a62ef  ldloc.s  5
0x1a62f1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a62f6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1a62fb  stloc.s  6
0x1a62fd  ldloc.s  6
0x1a62ff  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1a6304  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1a6309  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x1a630e  ldc.i4.s 0x1D
0x1a6310  bne.un.s loc_1A632B
0x1a6312  ldloc.3
0x1a6313  ldloc.s  6
0x1a6315  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1a631a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1a631f  unbox.any [mscorlib]System.Guid
0x1a6324  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x1a6329  brtrue.s loc_1A6335
0x1a632b  ldloc.s  4
0x1a632d  ldloc.s  6
0x1a632f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1a6334  pop
0x1a6335  ldloc.s  5
0x1a6337  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a633c  brtrue.s loc_1A62EF
0x1a633e  leave.s  loc_1A6355
0x1a6340  ldloc.s  5
0x1a6342  isinst   [mscorlib]System.IDisposable
0x1a6347  stloc.s  7
0x1a6349  ldloc.s  7
0x1a634b  brfalse.s loc_1A6354
0x1a634d  ldloc.s  7
0x1a634f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a6354  endfinally
0x1a6355  ldloc.s  4
0x1a6357  starg.s  1
0x1a6359  leave.s  loc_1A635E
0x1a635b  pop
0x1a635c  leave.s  loc_1A635E
0x1a635e  ldarg.0
0x1a635f  ldarg.2
0x1a6360  ldarg.s  4
0x1a6362  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RetrieveWorkflowComponentsInSolution(valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a6367  stloc.0
0x1a6368  ldloc.0
0x1a6369  brfalse.s loc_1A6373
0x1a636b  ldloc.0
0x1a636c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1a6371  brtrue.s loc_1A6375
0x1a6373  ldarg.1
0x1a6374  ret
0x1a6375  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1a637a  stloc.1
0x1a637b  ldloc.0
0x1a637c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1a6381  stloc.s  5
0x1a6383  br.s     loc_1A6403
0x1a6385  ldloc.s  5
0x1a6387  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a638c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1a6391  ldstr    aWorkflowid// "workflowid"
0x1a6396  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a639b  unbox.any [mscorlib]System.Guid
0x1a63a0  stloc.s  8
0x1a63a2  ldarg.0
0x1a63a3  ldloc.s  8
0x1a63a5  ldarg.s  4
0x1a63a7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RetrieveActivatedWorkflow(valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a63ac  stloc.s  9
0x1a63ae  ldloc.s  9
0x1a63b0  brfalse.s loc_1A6403
0x1a63b2  ldloc.s  9
0x1a63b4  ldstr    aCategory// "category"
0x1a63b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a63be  unbox.any [mscorlib]System.Int32
0x1a63c3  stloc.s  0xA
0x1a63c5  ldloc.s  9
0x1a63c7  ldstr    aMode// "mode"
0x1a63cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a63d1  unbox.any [mscorlib]System.Int32
0x1a63d6  stloc.s  0xB
0x1a63d8  ldloc.s  0xA
0x1a63da  ldc.i4.3
0x1a63db  beq.s    loc_1A63EB
0x1a63dd  ldloc.s  0xA
0x1a63df  brfalse.s loc_1A63E6
0x1a63e1  ldloc.s  0xA
0x1a63e3  ldc.i4.2
0x1a63e4  bne.un.s loc_1A6403
0x1a63e6  ldloc.s  0xB
0x1a63e8  ldc.i4.1
0x1a63e9  bne.un.s loc_1A6403
0x1a63eb  ldloc.1
0x1a63ec  ldloc.s  9
0x1a63ee  ldstr    aActiveworkflow// "activeworkflowid"
0x1a63f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a63f8  unbox.any [mscorlib]System.Guid
0x1a63fd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1a6402  pop
0x1a6403  ldloc.s  5
0x1a6405  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a640a  brtrue   loc_1A6385
0x1a640f  leave.s  loc_1A6426
0x1a6411  ldloc.s  5
0x1a6413  isinst   [mscorlib]System.IDisposable
0x1a6418  stloc.s  7
0x1a641a  ldloc.s  7
0x1a641c  brfalse.s loc_1A6425
0x1a641e  ldloc.s  7
0x1a6420  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a6425  endfinally
0x1a6426  ldloc.1
0x1a6427  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1a642c  brtrue.s loc_1A6430
0x1a642e  ldarg.1
0x1a642f  ret
0x1a6430  ldarg.1
0x1a6431  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1a6436  ldc.i4.1
0x1a6437  sub
0x1a6438  stloc.s  0xC
0x1a643a  br       loc_1A6570
0x1a643f  ldarg.1
0x1a6440  ldloc.s  0xC
0x1a6442  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1a6447  stloc.s  0xD
0x1a6449  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a644e  stloc.s  0xE
0x1a6450  ldloc.s  0xD
0x1a6452  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1a6457  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a645c  unbox.any [mscorlib]System.Int32
0x1a6461  stloc.s  0xF
0x1a6463  ldloc.s  0xF
0x1a6465  ldc.i4.s 0x5C
0x1a6467  beq.s    loc_1A6474
0x1a6469  ldloc.s  0xF
0x1a646b  ldc.i4.s 0x5D
0x1a646d  beq.s    loc_1A6489
0x1a646f  br       loc_1A656A
0x1a6474  ldloc.s  0xD
0x1a6476  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1a647b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a6480  unbox.any [mscorlib]System.Guid
0x1a6485  stloc.s  0xE
0x1a6487  br.s     loc_1A64C2
0x1a6489  ldloc.s  0xD
0x1a648b  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1a6490  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a6495  unbox.any [mscorlib]System.Guid
0x1a649a  stloc.s  0x14
0x1a649c  ldarg.0
0x1a649d  ldloc.s  0x14
0x1a649f  ldarg.s  4
0x1a64a1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RetrieveSdkMessageProcessingStepImage(valuetype [mscorlib]System.Guid sdkMessageProcessingStepImageId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a64a6  stloc.s  0x15
0x1a64a8  ldloc.s  0x15
0x1a64aa  brfalse  loc_1A656A
0x1a64af  ldloc.s  0x15
0x1a64b1  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x1a64b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a64bb  unbox.any [mscorlib]System.Guid
0x1a64c0  stloc.s  0xE
0x1a64c2  ldarg.0
0x1a64c3  ldloc.s  0xE
0x1a64c5  ldarg.s  4
0x1a64c7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RetrieveSdkMessageProcessingStep(valuetype [mscorlib]System.Guid sdkMessageProcessingStepId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a64cc  stloc.s  0x10
0x1a64ce  ldloc.s  0x10
0x1a64d0  brfalse  loc_1A656A
0x1a64d5  ldloc.s  0x10
0x1a64d7  ldstr    aConfiguration// "configuration"
0x1a64dc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1a64e1  isinst   [mscorlib]System.String
0x1a64e6  stloc.s  0x11
0x1a64e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a64ed  stloc.s  0x12
0x1a64ef  ldloc.s  0x11
0x1a64f1  brfalse.s loc_1A6512
0x1a64f3  ldloc.s  0x11
0x1a64f5  ldloca.s 0x12
0x1a64f7  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1a64fc  brfalse.s loc_1A6512
0x1a64fe  ldloc.1
0x1a64ff  ldloc.s  0x12
0x1a6501  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x1a6506  brfalse.s loc_1A6512
0x1a6508  ldarg.1
0x1a6509  ldloc.s  0xC
0x1a650b  callvirt instance void [mscorlib]System.Collections.CollectionBase::RemoveAt(int32)
0x1a6510  br.s     loc_1A656A
0x1a6512  ldarg.0
0x1a6513  ldarg.s  4
0x1a6515  ldloc.s  0x10
0x1a6517  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::RetrieveSdkMessageFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity step)
0x1a651c  stloc.s  0x13
0x1a651e  ldloc.s  0x13
0x1a6520  brfalse.s loc_1A656A
0x1a6522  ldloc.s  0x13
0x1a6524  ldstr    aPrimaryobjectt_0// "primaryobjecttypecode"
0x1a6529  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1a652e  unbox.any [mscorlib]System.Int32
0x1a6533  stloc.s  0x16
0x1a6535  ldloc.s  0x13
0x1a6537  ldstr    aSecondaryobjec_0// "secondaryobjecttypecode"
0x1a653c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1a6541  unbox.any [mscorlib]System.Int32
0x1a6546  stloc.s  0x17
0x1a6548  ldarg.0
0x1a6549  ldarg.2
0x1a654a  ldloc.s  0x16
0x1a654c  ldarg.s  4
0x1a654e  call     instance bool Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::IsParentEntityInUninstallSolution(valuetype [mscorlib]System.Guid uninstallingSolutionId, int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a6553  brtrue.s loc_1A6562
0x1a6555  ldarg.0
0x1a6556  ldarg.2
0x1a6557  ldloc.s  0x17
0x1a6559  ldarg.s  4
0x1a655b  call     instance bool Microsoft.Crm.ObjectModel.SdkMessageProcessingStepDependencyCalculator::IsParentEntityInUninstallSolution(valuetype [mscorlib]System.Guid uninstallingSolutionId, int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a6560  brfalse.s loc_1A656A
0x1a6562  ldarg.1
0x1a6563  ldloc.s  0xC
0x1a6565  callvirt instance void [mscorlib]System.Collections.CollectionBase::RemoveAt(int32)
0x1a656a  ldloc.s  0xC
0x1a656c  ldc.i4.1
0x1a656d  sub
0x1a656e  stloc.s  0xC
0x1a6570  ldloc.s  0xC
0x1a6572  ldc.i4.0
0x1a6573  bge      loc_1A643F
0x1a6578  ldarg.1
0x1a6579  ret
```
