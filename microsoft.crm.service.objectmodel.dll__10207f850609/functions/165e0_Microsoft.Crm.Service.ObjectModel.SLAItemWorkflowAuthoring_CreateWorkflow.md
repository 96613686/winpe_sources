# Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::CreateWorkflow

- ea: `0x165e0`
- end: `0x169db`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::CreateWorkflow`
- size: `1019`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x165e0`
- `0x16d40`
- `0x16dc0`
- `0x17b10`
- `0x17bf0`

## string_xrefs

- `0x1664c`: `BusinessHoursId`

## pseudocode

```c

```

## disassembly

```asm
0x165e0  ldarg.0
0x165e1  ldarg.0
0x165e2  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_getWorkflowname
0x165e7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x165ec  ldarg.0
0x165ed  ldarg.0
0x165ee  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_entityName
0x165f3  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x165f8  ldarg.0
0x165f9  ldc.i4.0
0x165fa  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x165ff  ldarg.0
0x16600  ldc.i4.0
0x16601  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x16606  ldarg.0
0x16607  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x1660c  ldarg.0
0x1660d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::sla
0x16612  ldstr    aOwnerid// "ownerid"
0x16617  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1661c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x16621  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x16626  ldarg.0
0x16627  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x1662c  stloc.0
0x1662d  ldarg.0
0x1662e  ldloc.0
0x1662f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x16634  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_workflowid
0x16639  ldarg.0
0x1663a  ldloca.s 5
0x1663c  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x16642  ldloca.s 5
0x16644  ldc.i4.5
0x16645  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x1664a  ldloca.s 5
0x1664c  ldstr    aBusinesshoursi_0// "BusinessHoursId"
0x16651  ldc.i4.6
0x16652  ldc.i4.1
0x16653  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x16658  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x1665d  ldloca.s 5
0x1665f  ldc.i4.1
0x16660  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x16665  ldloca.s 5
0x16667  ldstr    aCalendar_0// "calendar"
0x1666c  ldstr    aCalendarid// "calendarid"
0x16671  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::.ctor(string, string)
0x16676  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x1667b  ldloca.s 5
0x1667d  ldc.i4.0
0x1667e  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x16683  ldloc.s  5
0x16685  stfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_calendarInputArgument
0x1668a  ldloc.0
0x1668b  ldarg.0
0x1668c  ldfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_calendarInputArgument
0x16691  ldc.i4.1
0x16692  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x16697  ldarg.0
0x16698  ldloca.s 5
0x1669a  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x166a0  ldloca.s 5
0x166a2  ldc.i4.3
0x166a3  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x166a8  ldloca.s 5
0x166aa  ldstr    aCalculatedfail// "CalculatedFailureTimeout"
0x166af  ldc.i4.2
0x166b0  ldc.i4.1
0x166b1  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x166b6  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x166bb  ldloca.s 5
0x166bd  ldc.i4.0
0x166be  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x166c3  ldloca.s 5
0x166c5  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x166ca  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x166cf  ldloca.s 5
0x166d1  ldc.i4.1
0x166d2  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x166d7  ldloca.s 5
0x166d9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x166de  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsDateTime(valuetype [mscorlib]System.DateTime)
0x166e3  ldloc.s  5
0x166e5  stfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_failureTimeoutInputVariable
0x166ea  ldloc.0
0x166eb  ldarg.0
0x166ec  ldfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_failureTimeoutInputVariable
0x166f1  ldc.i4.1
0x166f2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x166f7  ldarg.0
0x166f8  ldloca.s 5
0x166fa  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x16700  ldloca.s 5
0x16702  ldc.i4.3
0x16703  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x16708  ldloca.s 5
0x1670a  ldstr    aCalculatedwarn// "CalculatedWarningTimeout"
0x1670f  ldc.i4.2
0x16710  ldc.i4.1
0x16711  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x16716  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x1671b  ldloca.s 5
0x1671d  ldc.i4.0
0x1671e  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x16723  ldloca.s 5
0x16725  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x1672a  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x1672f  ldloca.s 5
0x16731  ldc.i4.1
0x16732  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x16737  ldloca.s 5
0x16739  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1673e  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsDateTime(valuetype [mscorlib]System.DateTime)
0x16743  ldloc.s  5
0x16745  stfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_warningTimeoutInputVariable
0x1674a  ldloc.0
0x1674b  ldarg.0
0x1674c  ldfld    valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_warningTimeoutInputVariable
0x16751  ldc.i4.1
0x16752  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x16757  ldsfld   string [mscorlib]System.String::Empty
0x1675c  stloc.1
0x1675d  ldsfld   string [mscorlib]System.String::Empty
0x16762  stloc.2
0x16763  ldsfld   string [mscorlib]System.String::Empty
0x16768  stloc.3
0x16769  ldarg.0
0x1676a  ldstr    asc_1EEAE// ""
0x1676f  ldloc.0
0x16770  ldarg.0
0x16771  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16776  ldstr    asc_1EEAE// ""
0x1677b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16780  ldstr    aWebSlaWorkflow_2// "Web.SLA.Workflow.ApplicableWhenCheckCon"...
0x16785  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1678a  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x1678f  stloc.s  4
0x16791  ldloc.s  4
0x16793  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16798  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x1679d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x167a2  stloc.1
0x167a3  ldarg.0
0x167a4  ldfld    bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_useslakpi
0x167a9  brfalse.s loc_167E6
0x167ab  ldarg.0
0x167ac  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_organizationContext
0x167b1  ldarg.0
0x167b2  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_relatedfield
0x167b7  ldarg.0
0x167b8  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x167bd  ldarg.0
0x167be  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_defaultSuccessCondition
0x167c3  newobj   instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext organizationContext, string relatedField, string successWhenStep, string defaultSuccessCondition)
0x167c8  ldloc.0
0x167c9  ldloc.s  4
0x167cb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x167d0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x167d5  callvirt instance string [mscorlib]System.Object::ToString()
0x167da  ldloc.2
0x167db  ldloc.3
0x167dc  callvirt instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::CreateStepsForUseSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string applicableCriteriaStepId, string waitStepId, string successConditionStepId)
0x167e1  br       loc_16979
0x167e6  ldarg.0
0x167e7  ldloc.s  4
0x167e9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x167ee  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x167f3  callvirt instance string [mscorlib]System.Object::ToString()
0x167f8  ldloc.0
0x167f9  ldarg.0
0x167fa  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x167ff  ldstr    asc_1EEAE// ""
0x16804  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16809  ldstr    aWebSlaWorkflow_3// "Web.SLA.Workflow.SuccessCheckCondition"
0x1680e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16813  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x16818  stloc.s  6
0x1681a  ldloc.s  6
0x1681c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16821  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16826  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1682b  stloc.3
0x1682c  ldarg.0
0x1682d  ldloc.0
0x1682e  ldloc.s  6
0x16830  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16835  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x1683a  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddStopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x1683f  ldarg.0
0x16840  ldloc.3
0x16841  ldloc.0
0x16842  ldstr    asc_1EEAE// ""
0x16847  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1684c  ldloc.s  6
0x1684e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16853  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x16858  stloc.2
0x16859  ldnull
0x1685a  stloc.s  7
0x1685c  ldnull
0x1685d  stloc.s  8
0x1685f  ldarg.0
0x16860  ldloc.2
0x16861  ldloc.0
0x16862  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16867  ldstr    aWebSlaWorkflow_4// "Web.SLA.Workflow.WarningVariable"
0x1686c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16871  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::AddAssignVariableStep(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepDescription)
0x16876  ldarg.0
0x16877  ldloc.2
0x16878  ldloc.0
0x16879  ldstr    asc_1EEAE// ""
0x1687e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16883  ldstr    aWebSlaWorkflow_5// "Web.SLA.Workflow.TimeoutWarnAt"
0x16888  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1688d  ldc.i4.1
0x1688e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::AddWaitStep(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml, string stepDescription, bool isWarning)
0x16893  stloc.s  7
0x16895  ldarg.0
0x16896  ldloc.s  7
0x16898  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1689d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x168a2  callvirt instance string [mscorlib]System.Object::ToString()
0x168a7  ldloc.0
0x168a8  ldarg.0
0x168a9  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x168ae  ldstr    asc_1EEAE// ""
0x168b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x168b8  ldstr    aWebSlaWorkflow_6// "Web.SLA.Workflow.SuccessCondition"
0x168bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x168c2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x168c7  dup
0x168c8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x168cd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x168d2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x168d7  stloc.3
0x168d8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x168dd  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x168e2  stloc.s  9
0x168e4  ldarg.0
0x168e5  ldloc.0
0x168e6  ldloc.s  9
0x168e8  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddStopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x168ed  ldarg.0
0x168ee  ldloc.3
0x168ef  ldloc.0
0x168f0  ldstr    asc_1EEAE// ""
0x168f5  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x168fa  ldarg.0
0x168fb  ldloc.2
0x168fc  ldloc.0
0x168fd  ldstr    asc_1EEAE// ""
0x16902  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16907  ldstr    aWebSlaWorkflow_7// "Web.SLA.Workflow.TimeoutFailureAt"
0x1690c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16911  ldc.i4.0
0x16912  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::AddWaitStep(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml, string stepDescription, bool isWarning)
0x16917  stloc.s  8
0x16919  ldarg.0
0x1691a  ldloc.s  8
0x1691c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16921  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x16926  ldloc.0
0x16927  ldarg.0
0x16928  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x1692d  ldstr    asc_1EEAE// ""
0x16932  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16937  ldstr    aWebSlaWorkflow_6// "Web.SLA.Workflow.SuccessCondition"
0x1693c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16941  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x16946  dup
0x16947  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1694c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16951  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x16956  stloc.3
0x16957  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1695c  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x16961  stloc.s  0xA
0x16963  ldarg.0
0x16964  ldloc.0
0x16965  ldloc.s  0xA
0x16967  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddStopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x1696c  ldarg.0
0x1696d  ldloc.3
0x1696e  ldloc.0
0x1696f  ldstr    asc_1EEAE// ""
0x16974  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x16979  ldarg.0
0x1697a  ldloc.1
0x1697b  ldloc.0
0x1697c  ldstr    asc_1EEAE// ""
0x16981  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x16986  ldarg.0
0x16987  ldloc.0
0x16988  ldloc.0
0x16989  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1698e  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x16993  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddStopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x16998  ldloc.0
  ... truncated ...
```
