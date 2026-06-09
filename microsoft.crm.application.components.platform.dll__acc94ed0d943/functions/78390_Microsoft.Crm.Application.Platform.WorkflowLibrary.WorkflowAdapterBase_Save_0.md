# Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save_0

- ea: `0x78390`
- end: `0x78766`
- name: `Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save_0`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x78380`

## callees

- `0x3aa00`
- `0x5ccb0`
- `0x77d80`
- `0x78390`
- `0x78770`
- `0x799f0`
- `0x79aa0`
- `0x79c60`
- `0x79d10`
- `0x7aa50`
- `0x959e0`
- `0x95a30`

## string_xrefs

- `0x7872a`: `formxml`
- `0x783d4`: `asyncautodelete`
- `0x78651`: `channelaccessprofilerule`
- `0x78668`: `channelaccessprofileruleitem`

## pseudocode

```c

```

## disassembly

```asm
0x78390  ldstr    aWorkflow// "workflow"
0x78395  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x7839a  stloc.0
0x7839b  ldloc.0
0x7839c  ldstr    aWorkflowid// "workflowid"
0x783a1  ldarg.1
0x783a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x783a7  box      [mscorlib]System.Guid
0x783ac  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x783b1  ldloc.0
0x783b2  ldstr    aName// "name"
0x783b7  ldarg.1
0x783b8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_Title()
0x783bd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x783c2  ldloc.0
0x783c3  ldstr    aDescription_0// "description"
0x783c8  ldarg.1
0x783c9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x783ce  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x783d3  ldloc.0
0x783d4  ldstr    aAsyncautodelet// "asyncautodelete"
0x783d9  ldarg.1
0x783da  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x783df  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_AsyncAutoDelete()
0x783e4  box      [mscorlib]System.Boolean
0x783e9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x783ee  ldarg.1
0x783ef  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x783f4  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsTemplate()
0x783f9  brfalse.s loc_7840E
0x783fb  ldloc.0
0x783fc  ldstr    aType// "type"
0x78401  ldc.i4.3
0x78402  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x78407  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7840c  br.s     loc_7841F
0x7840e  ldloc.0
0x7840f  ldstr    aType// "type"
0x78414  ldc.i4.1
0x78415  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x7841a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7841f  ldarg.1
0x78420  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78425  ldc.i4.4
0x78426  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x7842b  brfalse.s loc_78440
0x7842d  ldloc.0
0x7842e  ldstr    aOndemand// "ondemand"
0x78433  ldc.i4.1
0x78434  box      [mscorlib]System.Boolean
0x78439  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7843e  br.s     loc_78451
0x78440  ldloc.0
0x78441  ldstr    aOndemand// "ondemand"
0x78446  ldc.i4.0
0x78447  box      [mscorlib]System.Boolean
0x7844c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78451  ldarg.1
0x78452  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78457  ldc.i4.8
0x78458  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x7845d  brfalse.s loc_78472
0x7845f  ldloc.0
0x78460  ldstr    aSubprocess// "subprocess"
0x78465  ldc.i4.1
0x78466  box      [mscorlib]System.Boolean
0x7846b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78470  br.s     loc_78483
0x78472  ldloc.0
0x78473  ldstr    aSubprocess// "subprocess"
0x78478  ldc.i4.0
0x78479  box      [mscorlib]System.Boolean
0x7847e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78483  ldarg.1
0x78484  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78489  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x7848e  ldc.i4.1
0x7848f  bne.un.s loc_784C6
0x78491  ldloc.0
0x78492  ldstr    aOndemand// "ondemand"
0x78497  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7849c  unbox.any [mscorlib]System.Boolean
0x784a1  brtrue.s loc_784C6
0x784a3  ldloc.0
0x784a4  ldstr    aSubprocess// "subprocess"
0x784a9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x784ae  unbox.any [mscorlib]System.Boolean
0x784b3  brtrue.s loc_784C6
0x784b5  ldloc.0
0x784b6  ldstr    aOndemand// "ondemand"
0x784bb  ldc.i4.1
0x784bc  box      [mscorlib]System.Boolean
0x784c1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x784c6  ldarg.1
0x784c7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x784cc  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsSyncWorkflow()
0x784d1  brtrue.s loc_784E0
0x784d3  ldarg.1
0x784d4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x784d9  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsCustomOperation()
0x784de  brfalse.s loc_784FB
0x784e0  ldloc.0
0x784e1  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x784e6  ldarg.1
0x784e7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x784ec  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_SyncWorkflowLogOnFailure()
0x784f1  box      [mscorlib]System.Boolean
0x784f6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x784fb  ldloc.0
0x784fc  ldstr    aScope// "scope"
0x78501  ldarg.1
0x78502  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78507  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_Scope()
0x7850c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x78511  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78516  ldarg.2
0x78517  brfalse.s loc_7854F
0x78519  ldloc.0
0x7851a  ldstr    aCategory// "category"
0x7851f  ldarg.1
0x78520  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78525  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x7852a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x7852f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78534  ldloc.0
0x78535  ldstr    aMode// "mode"
0x7853a  ldarg.1
0x7853b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78540  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowMode()
0x78545  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x7854a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7854f  ldarg.1
0x78550  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78555  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x7855a  ldc.i4.3
0x7855b  bne.un.s loc_785B4
0x7855d  ldarg.1
0x7855e  ldarg.1
0x7855f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_UniqueName()
0x78564  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78569  brtrue.s loc_78573
0x7856b  ldarg.1
0x7856c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_UniqueName()
0x78571  br.s     loc_7857E
0x78573  ldarg.1
0x78574  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_Title()
0x78579  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::SanitizeWorkflowUniqueName(string)
0x7857e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::set_UniqueName(string)
0x78583  ldloc.0
0x78584  ldstr    aUniquename// "uniquename"
0x78589  ldarg.1
0x7858a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_UniqueName()
0x7858f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78594  ldloc.0
0x78595  ldstr    aIstransacted// "istransacted"
0x7859a  ldarg.1
0x7859b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x785a0  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomOperationPublicationParameters
0x785a5  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomOperationPublicationParameters::get_InTransaction()
0x785aa  box      [mscorlib]System.Boolean
0x785af  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x785b4  ldarg.1
0x785b5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x785ba  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x785bf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x785c4  brtrue   loc_78685
0x785c9  ldloc.0
0x785ca  ldstr    aRendererobject// "rendererobjecttypecode"
0x785cf  ldarg.1
0x785d0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x785d5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x785da  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x785df  ldarg.0
0x785e0  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_OverriddenOwnerId()
0x785e5  brfalse  loc_78685
0x785ea  ldarg.1
0x785eb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x785f0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x785f5  ldstr    aSla// "sla"
0x785fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x785ff  brtrue.s loc_78674
0x78601  ldarg.1
0x78602  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78607  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x7860c  ldstr    aSlaitem// "slaitem"
0x78611  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78616  brtrue.s loc_78674
0x78618  ldarg.1
0x78619  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x7861e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x78623  ldstr    aConvertrule// "convertrule"
0x78628  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7862d  brtrue.s loc_78674
0x7862f  ldarg.1
0x78630  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78635  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x7863a  ldstr    aConvertruleite_0// "convertruleitem"
0x7863f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78644  brtrue.s loc_78674
0x78646  ldarg.1
0x78647  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x7864c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x78651  ldstr    aChannelaccessp// "channelaccessprofilerule"
0x78656  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7865b  brtrue.s loc_78674
0x7865d  ldarg.1
0x7865e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78663  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x78668  ldstr    aChannelaccessp_0// "channelaccessprofileruleitem"
0x7866d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78672  brfalse.s loc_78685
0x78674  ldloc.0
0x78675  ldstr    aOwnerid// "ownerid"
0x7867a  ldarg.0
0x7867b  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_OverriddenOwnerId()
0x78680  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78685  ldarg.1
0x78686  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x7868b  ldc.i4.4
0x7868c  bne.un.s loc_786BC
0x7868e  ldarg.1
0x7868f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x78694  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Count()
0x78699  brtrue.s loc_786B3
0x7869b  ldarg.1
0x7869c  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowBusinessProcessType()
0x786a1  brtrue.s loc_786AC
0x786a3  ldarg.0
0x786a4  ldarg.1
0x786a5  call     instance void Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GenerateDefaultBusinessProcessFlow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x786aa  br.s     loc_786B3
0x786ac  ldarg.0
0x786ad  ldarg.1
0x786ae  call     instance void Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GenerateDefaultTaskBasedFlow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x786b3  ldarg.0
0x786b4  ldarg.1
0x786b5  ldloc.0
0x786b6  ldc.i4.1
0x786b7  call     instance void Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::AddTriggersToWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity, bool isUpdate)
0x786bc  ldloc.0
0x786bd  ldarg.0
0x786be  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::_sdkCommand
0x786c3  ldarg.0
0x786c4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::_context
0x786c9  newobj   instance void Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowDefinitionVisitor::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity definition, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand sdkCommand, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x786ce  ldarg.1
0x786cf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x786d4  ldarg.1
0x786d5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0x786da  ldloca.s 1
0x786dc  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x786e1  brfalse.s loc_7875E
0x786e3  ldarg.1
0x786e4  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x786e9  ldc.i4.4
0x786ea  bne.un.s loc_7875E
0x786ec  ldarg.1
0x786ed  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowBusinessProcessType()
0x786f2  ldc.i4.1
0x786f3  bne.un.s loc_7875E
0x786f5  ldarg.1
0x786f6  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x786fb  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x78700  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.FormXmlGenerationVisitor::GenerateFormXml(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, int32)
0x78705  stloc.2
0x78706  ldloc.0
0x78707  ldstr    aFormid// "formid"
0x7870c  ldloc.1
0x7870d  box      [mscorlib]System.Guid
0x78712  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78717  ldstr    aSystemform// "systemform"
0x7871c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x78721  stloc.3
0x78722  ldloc.3
0x78723  ldloc.1
0x78724  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x78729  ldloc.3
0x7872a  ldstr    aFormxml// "formxml"
0x7872f  ldloc.2
0x78730  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x78735  ldloc.0
0x78736  ldarg.0
0x78737  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_Context()
0x7873c  newobj   instance void Microsoft.Crm.Application.Platform.EntityProxy::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity platformEntity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x78741  ldloc.3
0x78742  ldarg.0
0x78743  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_Context()
0x78748  newobj   instance void Microsoft.Crm.Application.Platform.EntityProxy::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity platformEntity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7874d  ldarg.0
0x7874e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_Context()
0x78753  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.SaveTaskBasedFlowCommand::.ctor(class Microsoft.Crm.Application.Platform.EntityProxy workflow, class Microsoft.Crm.Application.Platform.EntityProxy systemForm, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x78758  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.SaveTaskBasedFlowCommand::Execute()
0x7875d  ret
0x7875e  ldarg.0
0x7875f  ldloc.0
0x78760  callvirt instance void Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity)
0x78765  ret
```
