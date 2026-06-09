# Microsoft.Crm.ObjectModel.SystemFormUninstallHandler::UpdateComponent

- ea: `0x1961a0`
- end: `0x1964e5`
- name: `Microsoft.Crm.ObjectModel.SystemFormUninstallHandler::UpdateComponent`
- size: `837`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x100e60`
- `0x100f00`
- `0x100f20`
- `0x101030`
- `0x1014c0`
- `0x107c10`
- `0x109410`
- `0x10fcc0`
- `0x122c90`
- `0x122ed0`
- `0x1345d0`
- `0x1530e0`
- `0x153570`
- `0x195e60`
- `0x1961a0`
- `0x1964f0`
- `0x196570`
- `0x197f10`
- `0x197ff0`
- `0x198000`

## string_xrefs

- `0x1961f3`: `formxml`
- `0x196258`: `formxml`
- `0x1962cd`: `formxml`
- `0x1963be`: `formxml`
- `0x19640b`: `formxml`
- `0x1961a8`: `systemFormComponentInstance`

## pseudocode

```c

```

## disassembly

```asm
0x1961a0  ldarg.3
0x1961a1  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x1961a6  stloc.0
0x1961a7  ldloc.0
0x1961a8  ldstr    aSystemformcomp// "systemFormComponentInstance"
0x1961ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1961b2  ldloc.0
0x1961b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x1961b8  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm
0x1961bd  stloc.1
0x1961be  ldloc.1
0x1961bf  ldstr    aSystemformenti// "systemFormEntity"
0x1961c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1961c9  ldloc.1
0x1961ca  ldstr    aType// "type"
0x1961cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1961d4  unbox.any [mscorlib]System.Int32
0x1961d9  stloc.2
0x1961da  ldloc.2
0x1961db  brfalse.s loc_1961E6
0x1961dd  ldloc.2
0x1961de  ldc.i4.8
0x1961df  beq.s    loc_1961E6
0x1961e1  ldloc.2
0x1961e2  ldc.i4.s 9
0x1961e4  bne.un.s loc_1961F2
0x1961e6  ldarg.0
0x1961e7  ldarg.1
0x1961e8  ldarg.2
0x1961e9  ldarg.3
0x1961ea  ldarg.s  4
0x1961ec  call     instance void Microsoft.Crm.ObjectModel.SystemFormUninstallHandler::UpdateComponentNoNeedMerge(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData componentTypeData, valuetype [mscorlib]System.Guid componentObjectId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance componentInstance, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x1961f1  ret
0x1961f2  ldloc.1
0x1961f3  ldstr    aFormxml// "formxml"
0x1961f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1961fd  isinst   [mscorlib]System.String
0x196202  stloc.3
0x196203  ldloc.1
0x196204  ldstr    aFormid// "formid"
0x196209  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19620e  unbox.any [mscorlib]System.Guid
0x196213  stloc.s  4
0x196215  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::.ctor()
0x19621a  ldc.i4.s 0x3C
0x19621c  ldloc.s  4
0x19621e  ldc.i4.1
0x19621f  ldarg.s  4
0x196221  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196226  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19622b  stloc.s  5
0x19622d  ldloc.s  4
0x19622f  ldarg.s  4
0x196231  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196236  call     string Microsoft.Crm.ObjectModel.FormSolutionUtility::CalculateCustomizationFormXmlDiff(valuetype [mscorlib]System.Guid formEntityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19623b  stloc.s  6
0x19623d  newobj   instance void Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x196242  stloc.s  7
0x196244  ldloc.s  7
0x196246  ldloc.s  4
0x196248  ldarg.s  4
0x19624a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x19624f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SystemFormService::RetrieveLastPublishedForm(valuetype [mscorlib]System.Guid formEntityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x196254  stloc.s  8
0x196256  ldloc.s  8
0x196258  ldstr    aFormxml// "formxml"
0x19625d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x196262  isinst   [mscorlib]System.String
0x196267  stloc.s  9
0x196269  ldnull
0x19626a  stloc.s  0xA
0x19626c  ldc.i4.0
0x19626d  stloc.s  0xF
0x19626f  br.s     loc_1962B6
0x196271  ldloc.s  5
0x196273  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x196278  ldloc.s  0xF
0x19627a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Item(!!T0)
0x19627f  stloc.s  0x10
0x196281  ldarg.s  4
0x196283  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196288  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19628d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x196292  ldloc.s  0x10
0x196294  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x196299  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19629e  brfalse.s loc_1962B0
0x1962a0  ldloc.s  0x10
0x1962a2  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x1962a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x1962ac  stloc.s  0xA
0x1962ae  br.s     loc_1962C6
0x1962b0  ldloc.s  0xF
0x1962b2  ldc.i4.1
0x1962b3  add
0x1962b4  stloc.s  0xF
0x1962b6  ldloc.s  0xF
0x1962b8  ldloc.s  5
0x1962ba  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x1962bf  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x1962c4  blt.s    loc_196271
0x1962c6  ldloc.s  5
0x1962c8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_TopInstance()
0x1962cd  ldstr    aFormxml// "formxml"
0x1962d2  callvirt instance object [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string)
0x1962d7  castclass [mscorlib]System.String
0x1962dc  stloc.s  0xB
0x1962de  newobj   instance void Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x1962e3  ldloc.s  0xB
0x1962e5  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.FormLabelHelper::GetLabelIdsOfNodesWithLabels(string formXml)
0x1962ea  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x1962ef  ldarg.s  4
0x1962f1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1962f6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1962fb  callvirt instance void Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::DeleteUnpublished(valuetype [mscorlib]System.Guid[] objectIds, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x196300  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x196305  stloc.s  0xC
0x196307  ldloc.s  5
0x196309  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x19630e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x196313  ldarg.s  4
0x196315  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x19631a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x19631f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x196324  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x196329  brfalse.s loc_196333
0x19632b  ldloc.0
0x19632c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x196331  stloc.s  0xC
0x196333  ldloc.s  4
0x196335  ldloc.3
0x196336  ldloc.s  0xC
0x196338  ldarg.s  4
0x19633a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x19633f  ldc.i4.0
0x196340  call     string Microsoft.Crm.ObjectModel.FormSolutionUtility::RecalculateFormSolutionStacks(valuetype [mscorlib]System.Guid formId, string baseFormXml, valuetype [mscorlib]System.Guid skipSolutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool isFormFromSystemConvertedSolution)
0x196345  stloc.s  0xD
0x196347  ldarg.0
0x196348  ldloc.s  0xA
0x19634a  ldarg.s  4
0x19634c  call     instance void Microsoft.Crm.ObjectModel.SystemFormUninstallHandler::CascadeUninstallToFormLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x196351  ldloc.s  6
0x196353  brfalse  loc_1963E8
0x196358  ldloc.s  0xD
0x19635a  ldloc.s  4
0x19635c  ldarg.s  4
0x19635e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196363  call     string Microsoft.Crm.ObjectModel.FormSolutionUtility::InsertFormXmlWithCustomLabels(string formXml, valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x196368  stloc.s  0xD
0x19636a  ldloc.s  0xD
0x19636c  ldloc.s  6
0x19636e  ldarg.s  4
0x196370  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196375  call     string Microsoft.Crm.ObjectModel.FormSolutionUtility::MergeFormXmlDiff(string formXmlOld, string formXmlDiff, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19637a  stloc.s  0x11
0x19637c  ldloc.2
0x19637d  ldc.i4.7
0x19637e  beq.s    loc_196384
0x196380  ldloc.2
0x196381  ldc.i4.6
0x196382  bne.un.s loc_19638D
0x196384  ldloc.s  0x11
0x196386  call     string Microsoft.Crm.ObjectModel.XmlDiffUtility::MergeConflictsTabWithMainTab(string formXml)
0x19638b  stloc.s  0x11
0x19638d  ldarg.s  4
0x19638f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196394  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSetSolutionToDefaultModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x196399  stloc.s  0x12
0x19639b  ldarg.s  4
0x19639d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1963a2  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1963a7  stloc.s  0x13
0x1963a9  ldloc.s  0x13
0x1963ab  ldstr    aFormid// "formid"
0x1963b0  ldloc.s  4
0x1963b2  box      [mscorlib]System.Guid
0x1963b7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1963bc  ldloc.s  0x13
0x1963be  ldstr    aFormxml// "formxml"
0x1963c3  ldloc.s  0x11
0x1963c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1963ca  ldloc.s  7
0x1963cc  ldloc.s  0x13
0x1963ce  ldarg.s  4
0x1963d0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1963d5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1963da  leave.s  loc_196436
0x1963dc  ldloc.s  0x12
0x1963de  brfalse.s loc_1963E7
0x1963e0  ldloc.s  0x12
0x1963e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1963e7  endfinally
0x1963e8  ldarg.s  4
0x1963ea  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1963ef  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSetSolutionToDefaultModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1963f4  stloc.s  0x12
0x1963f6  ldloc.s  8
0x1963f8  ldstr    aFormid// "formid"
0x1963fd  ldloc.s  4
0x1963ff  box      [mscorlib]System.Guid
0x196404  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x196409  ldloc.s  8
0x19640b  ldstr    aFormxml// "formxml"
0x196410  ldloc.s  0xD
0x196412  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x196417  ldloc.s  8
0x196419  ldloc.s  9
0x19641b  ldc.i4.0
0x19641c  ldarg.s  4
0x19641e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x196423  call     void Microsoft.Crm.ObjectModel.FormSolutionUtility::ExtractAndSaveFormLabels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entityWithNewFormXml, string oldEntityFormXml, bool extractUnchangedLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x196428  leave.s  loc_196436
0x19642a  ldloc.s  0x12
0x19642c  brfalse.s loc_196435
0x19642e  ldloc.s  0x12
0x196430  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x196435  endfinally
0x196436  ldc.i4.0
0x196437  stloc.s  0xE
0x196439  ldarg.3
0x19643a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x19643f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x196444  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x196449  brfalse.s loc_196468
0x19644b  ldarg.3
0x19644c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x196451  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x196456  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19645b  brfalse.s loc_196468
0x19645d  ldloc.2
0x19645e  ldc.i4.7
0x19645f  beq.s    loc_196465
0x196461  ldloc.2
0x196462  ldc.i4.6
0x196463  bne.un.s loc_196468
0x196465  ldc.i4.1
0x196466  stloc.s  0xE
0x196468  ldarg.s  4
0x19646a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x19646f  ldstr    aIgnoreformtabc// "IgnoreFormTabCountValidation"
0x196474  ldloc.s  0xE
0x196476  box      [mscorlib]System.Boolean
0x19647b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x196480  stloc.s  0x14
0x196482  ldarg.0
0x196483  ldarg.1
0x196484  ldarg.2
0x196485  ldarg.3
0x196486  ldarg.s  4
0x196488  call     instance void Microsoft.Crm.ObjectModel.NonMetadataUninstallHandler::UpdateComponent(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData componentTypeData, valuetype [mscorlib]System.Guid componentObjectId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance componentInstance, class Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x19648d  leave.s  loc_19649B
0x19648f  ldloc.s  0x14
0x196491  brfalse.s loc_19649A
0x196493  ldloc.s  0x14
0x196495  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19649a  endfinally
0x19649b  newobj   instance void Microsoft.Crm.ObjectModel.RibbonCustomizationService::.ctor()
0x1964a0  ldloc.s  4
0x1964a2  ldarg.s  4
0x1964a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1964a9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1964ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1964b3  ldarg.s  4
0x1964b5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x1964ba  ldc.i4.0
0x1964bb  call     instance void Microsoft.Crm.ObjectModel.RibbonCustomizationService::DeleteCustomizationsForForm(valuetype [mscorlib]System.Guid formId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool publishDelete)
0x1964c0  ldarg.s  4
0x1964c2  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_FormIdsNeedingRibbonMetadataRegeneration()
0x1964c7  brtrue.s loc_1964D5
0x1964c9  ldarg.s  4
0x1964cb  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1964d0  callvirt instance void Microsoft.Crm.ObjectModel.SolutionUninstallContext::set_FormIdsNeedingRibbonMetadataRegeneration(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> value)
0x1964d5  ldarg.s  4
0x1964d7  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_FormIdsNeedingRibbonMetadataRegeneration()
0x1964dc  ldloc.s  4
0x1964de  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1964e3  pop
0x1964e4  ret
```
