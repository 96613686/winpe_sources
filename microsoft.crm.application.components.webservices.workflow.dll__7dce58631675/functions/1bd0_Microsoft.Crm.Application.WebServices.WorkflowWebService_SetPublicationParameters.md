# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetPublicationParameters

- ea: `0x1bd0`
- end: `0x1e30`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetPublicationParameters`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x1bd0`
- `0x1e30`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldstr    aWorkflow// "workflow"
0x1bd5  ldarg.1
0x1bd6  ldc.i4.2
0x1bd7  newarr   [mscorlib]System.String
0x1bdc  dup
0x1bdd  ldc.i4.0
0x1bde  ldstr    aWorkflowid// "workflowid"
0x1be3  stelem.ref
0x1be4  dup
0x1be5  ldc.i4.1
0x1be6  ldstr    aStatecode// "statecode"
0x1beb  stelem.ref
0x1bec  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x1bf1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bf6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bfb  stloc.0
0x1bfc  leave.s  loc_1C18
0x1bfe  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x1c03  ldc.i4   0x80040217
0x1c08  bne.un.s loc_1C16
0x1c0a  ldsfld   string [mscorlib]System.String::Empty
0x1c0f  stloc.s  4
0x1c11  leave    loc_1E2D
0x1c16  rethrow
0x1c18  ldloc.0
0x1c19  ldstr    aStatecode// "statecode"
0x1c1e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1c23  isinst   [mscorlib]System.String
0x1c28  ldc.i4.1
0x1c29  stloc.s  5
0x1c2b  ldloca.s 5
0x1c2d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.WorkflowState
0x1c33  callvirt instance string [mscorlib]System.Object::ToString()
0x1c38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c3d  brfalse.s loc_1C4B
0x1c3f  ldsfld   string [mscorlib]System.String::Empty
0x1c44  stloc.s  4
0x1c46  leave    loc_1E2D
0x1c4b  ldarg.0
0x1c4c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x1c51  ldarg.1
0x1c52  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x1c57  stloc.1
0x1c58  ldloc.1
0x1c59  ldarg.2
0x1c5a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::set_Title(string)
0x1c5f  ldloc.1
0x1c60  ldarg.s  0x11
0x1c62  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::set_UniqueName(string)
0x1c67  ldarg.0
0x1c68  ldloc.1
0x1c69  ldarg.s  0xD
0x1c6b  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x1c70  ldloc.1
0x1c71  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1c76  stloc.2
0x1c77  ldloc.2
0x1c78  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ResetTriggerConditions()
0x1c7d  ldloc.2
0x1c7e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ResetTriggers()
0x1c83  ldloc.2
0x1c84  ldarg.3
0x1c85  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_IsTemplate(bool)
0x1c8a  ldarg.s  4
0x1c8c  brfalse.s loc_1C95
0x1c8e  ldloc.2
0x1c8f  ldc.i4.4
0x1c90  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1c95  ldarg.s  5
0x1c97  brfalse.s loc_1CA0
0x1c99  ldloc.2
0x1c9a  ldc.i4.8
0x1c9b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1ca0  ldloc.2
0x1ca1  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x1ca6  brfalse.s loc_1CB4
0x1ca8  ldloc.2
0x1ca9  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x1cae  ldc.i4.3
0x1caf  bne.un   loc_1D74
0x1cb4  ldarg.0
0x1cb5  ldloc.2
0x1cb6  ldarg.s  0xE
0x1cb8  ldarg.s  6
0x1cba  ldarg.s  8
0x1cbc  ldarg.s  7
0x1cbe  ldarg.s  0xF
0x1cc0  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStagesAndRunAs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters publicationParameters, string stages, bool onCreate, string updateAttributes, bool onDelete, int32 runAs)
0x1cc5  ldarg.s  6
0x1cc7  ldarg.s  7
0x1cc9  or
0x1cca  brtrue.s loc_1CD5
0x1ccc  ldarg.s  8
0x1cce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cd3  brtrue.s loc_1CDC
0x1cd5  ldloc.2
0x1cd6  ldc.i4.2
0x1cd7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1cdc  ldarg.s  6
0x1cde  brfalse.s loc_1CE7
0x1ce0  ldloc.2
0x1ce1  ldc.i4.2
0x1ce2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x1ce7  ldarg.s  7
0x1ce9  brfalse.s loc_1CF2
0x1ceb  ldloc.2
0x1cec  ldc.i4.4
0x1ced  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x1cf2  ldloc.2
0x1cf3  ldarg.s  8
0x1cf5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_UpdateAttributeList(string)
0x1cfa  ldloc.2
0x1cfb  ldarg.s  9
0x1cfd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_AllAttributesSelected(bool)
0x1d02  ldarg.s  0xA
0x1d04  ldc.i4.1
0x1d05  stloc.s  6
0x1d07  ldloca.s 6
0x1d09  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d0e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1d13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d18  brfalse.s loc_1D23
0x1d1a  ldloc.2
0x1d1b  ldc.i4.1
0x1d1c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_Scope(int32)
0x1d21  br.s     loc_1D6C
0x1d23  ldarg.s  0xA
0x1d25  ldc.i4.2
0x1d26  stloc.s  6
0x1d28  ldloca.s 6
0x1d2a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d2f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1d34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d39  brfalse.s loc_1D44
0x1d3b  ldloc.2
0x1d3c  ldc.i4.2
0x1d3d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_Scope(int32)
0x1d42  br.s     loc_1D6C
0x1d44  ldarg.s  0xA
0x1d46  ldc.i4.3
0x1d47  stloc.s  6
0x1d49  ldloca.s 6
0x1d4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d50  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1d55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d5a  brfalse.s loc_1D65
0x1d5c  ldloc.2
0x1d5d  ldc.i4.3
0x1d5e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_Scope(int32)
0x1d63  br.s     loc_1D6C
0x1d65  ldloc.2
0x1d66  ldc.i4.4
0x1d67  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_Scope(int32)
0x1d6c  ldloc.2
0x1d6d  ldarg.s  0xB
0x1d6f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_AsyncAutoDelete(bool)
0x1d74  ldloc.2
0x1d75  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsSyncWorkflow()
0x1d7a  brtrue.s loc_1D84
0x1d7c  ldloc.2
0x1d7d  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsCustomOperation()
0x1d82  brfalse.s loc_1D8C
0x1d84  ldloc.2
0x1d85  ldarg.s  0xC
0x1d87  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_SyncWorkflowLogOnFailure(bool)
0x1d8c  ldloc.2
0x1d8d  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x1d92  ldc.i4.3
0x1d93  bne.un.s loc_1DB3
0x1d95  ldarg.s  0x10
0x1d97  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d9c  brtrue.s loc_1DA6
0x1d9e  ldloc.1
0x1d9f  ldarg.s  0x10
0x1da1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::LoadWorkflowArguments(string)
0x1da6  ldloc.2
0x1da7  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomOperationPublicationParameters
0x1dac  ldarg.s  0x12
0x1dae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomOperationPublicationParameters::set_InTransaction(bool)
0x1db3  ldarg.0
0x1db4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x1db9  ldloc.1
0x1dba  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1dbf  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0x1dc4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x1dc9  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorVisitor::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x1dce  stloc.3
0x1dcf  ldloc.3
0x1dd0  ldloc.1
0x1dd1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1dd6  ldloc.3
0x1dd7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1ddc  ldloc.1
0x1ddd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1de2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::ContainsKey(var<u1>)
0x1de7  brfalse.s loc_1E19
0x1de9  ldloc.3
0x1dea  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x1def  ldloc.1
0x1df0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1df5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::get_Item(void)
0x1dfa  stloc.s  7
0x1dfc  ldloc.s  7
0x1dfe  ldc.i4   0x20000
0x1e03  and
0x1e04  brtrue.s loc_1E10
0x1e06  ldloc.s  7
0x1e08  ldc.i4   0x40000
0x1e0d  and
0x1e0e  brfalse.s loc_1E19
0x1e10  ldstr    aWorkflowerror// "workflowerror"
0x1e15  stloc.s  4
0x1e17  leave.s  loc_1E2D
0x1e19  ldsfld   string [mscorlib]System.String::Empty
0x1e1e  stloc.s  4
0x1e20  leave.s  loc_1E2D
0x1e22  stloc.s  8
0x1e24  ldarg.0
0x1e25  ldloc.s  8
0x1e27  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x1e2c  throw
0x1e2d  ldloc.s  4
0x1e2f  ret
```
