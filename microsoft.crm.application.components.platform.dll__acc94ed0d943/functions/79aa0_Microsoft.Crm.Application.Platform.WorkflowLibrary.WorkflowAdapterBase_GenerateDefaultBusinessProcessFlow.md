# Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GenerateDefaultBusinessProcessFlow

- ea: `0x79aa0`
- end: `0x79c06`
- name: `Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::GenerateDefaultBusinessProcessFlow`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x78390`
- `0x79750`

## callees

- `0x11760`
- `0x2fb90`
- `0x2fd50`
- `0x30260`
- `0x3aa00`
- `0x79aa0`
- `0x79c10`

## string_xrefs

- `0x79b4c`: `ProcessControl.Configurator.NewStep`
- `0x79afd`: `ProcessControl.Configurator.NewStage`

## pseudocode

```c

```

## disassembly

```asm
0x79aa0  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x79aa5  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Application.Security.UserInformation::get_OrganizationLanguageId()
0x79aaa  stloc.s  4
0x79aac  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x79ab1  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x79ab6  stloc.s  5
0x79ab8  ldloca.s 4
0x79aba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x79abf  ldloc.s  5
0x79ac1  beq.s    loc_79AC6
0x79ac3  ldc.i4.1
0x79ac4  br.s     loc_79AD0
0x79ac6  ldloca.s 4
0x79ac8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x79acd  ldc.i4.0
0x79ace  ceq
0x79ad0  brfalse.s loc_79AE3
0x79ad2  ldc.i4   0x8005E102
0x79ad7  ldc.i4.0
0x79ad8  newarr   [mscorlib]System.Object
0x79add  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x79ae2  throw
0x79ae3  ldarg.1
0x79ae4  ldarg.1
0x79ae5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x79aea  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x79aef  stloc.0
0x79af0  ldloc.0
0x79af1  ldarg.1
0x79af2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x79af7  ldarg.1
0x79af8  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x79afd  ldstr    aProcesscontrol_6// "ProcessControl.Configurator.NewStage"
0x79b02  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x79b07  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x79b0c  stloc.1
0x79b0d  ldloc.1
0x79b0e  ldarg.1
0x79b0f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x79b14  ldloc.1
0x79b15  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x79b1a  stloc.s  6
0x79b1c  ldloca.s 6
0x79b1e  constrained. [mscorlib]System.Guid
0x79b24  callvirt instance string [mscorlib]System.Object::ToString()
0x79b29  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::set_StageId(string)
0x79b2e  ldloc.1
0x79b2f  ldarg.0
0x79b30  ldloc.1
0x79b31  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageId()
0x79b36  ldloc.1
0x79b37  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageName()
0x79b3c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::BuildStepLabel(string labelId, string description)
0x79b41  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddLabel(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel)
0x79b46  ldarg.1
0x79b47  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x79b4c  ldstr    aProcesscontrol_5// "ProcessControl.Configurator.NewStep"
0x79b51  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x79b56  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x79b5b  stloc.2
0x79b5c  ldloc.2
0x79b5d  ldarg.1
0x79b5e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x79b63  ldloc.2
0x79b64  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x79b69  stloc.s  6
0x79b6b  ldloca.s 6
0x79b6d  constrained. [mscorlib]System.Guid
0x79b73  callvirt instance string [mscorlib]System.Object::ToString()
0x79b78  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::set_StepStepId(string)
0x79b7d  ldloc.2
0x79b7e  ldc.i4.0
0x79b7f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::set_IsProcessRequired(bool)
0x79b84  ldloc.2
0x79b85  ldarg.0
0x79b86  ldloc.2
0x79b87  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::get_StepStepId()
0x79b8c  ldloc.2
0x79b8d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::get_StepStepName()
0x79b92  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::BuildStepLabel(string labelId, string description)
0x79b97  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddLabel(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel)
0x79b9c  ldarg.1
0x79b9d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x79ba2  stloc.3
0x79ba3  ldloc.3
0x79ba4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x79ba9  stloc.s  6
0x79bab  ldloca.s 6
0x79bad  constrained. [mscorlib]System.Guid
0x79bb3  callvirt instance string [mscorlib]System.Object::ToString()
0x79bb8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlId(string)
0x79bbd  ldloc.3
0x79bbe  ldstr    asc_A9652// ""
0x79bc3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_DataFieldName(string)
0x79bc8  ldloc.3
0x79bc9  ldstr    asc_A9652// ""
0x79bce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ClassId(string)
0x79bd3  ldloc.3
0x79bd4  ldstr    asc_A9652// ""
0x79bd9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_Parameters(string)
0x79bde  ldloc.3
0x79bdf  ldstr    asc_A9652// ""
0x79be4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlDisplayName(string)
0x79be9  ldloc.2
0x79bea  ldloc.3
0x79beb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x79bf0  ldloc.1
0x79bf1  ldloc.2
0x79bf2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x79bf7  ldloc.0
0x79bf8  ldloc.1
0x79bf9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x79bfe  ldarg.1
0x79bff  ldloc.0
0x79c00  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x79c05  ret
```
