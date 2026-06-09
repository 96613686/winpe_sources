# Microsoft.Crm.Application.ProcessControl.Configuration.BpfPageStepControl::GetSourceDisplayLabel

- ea: `0x4d510`
- end: `0x4d570`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfPageStepControl::GetSourceDisplayLabel`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4d3c0`

## callees

- `0x4d380`
- `0x4d510`

## string_xrefs

- `0x4d563`: `ProcessControl.Configurator.Stage.Title.PageStepSource`
- `0x4d551`: `ProcessControl.Configurator.Page.ControlStep.SectionLabel`
- `0x4d53f`: `ProcessControl.Configurator.Page.ControlStep.Label`

## pseudocode

```c

```

## disassembly

```asm
0x4d510  ldarg.0
0x4d511  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_Step()
0x4d516  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x4d51b  ldc.i4.0
0x4d51c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x4d521  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x4d526  ldsfld   string [mscorlib]System.String::Empty
0x4d52b  stloc.0
0x4d52c  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_ControlType()
0x4d531  stloc.1
0x4d532  ldloc.1
0x4d533  ldc.i4.1
0x4d534  beq.s    loc_4D54C
0x4d536  ldloc.1
0x4d537  ldc.i4.2
0x4d538  bne.un.s loc_4D55E
0x4d53a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d53f  ldstr    aProcesscontrol_62// "ProcessControl.Configurator.Page.Contro"...
0x4d544  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d549  stloc.0
0x4d54a  br.s     loc_4D56E
0x4d54c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d551  ldstr    aProcesscontrol_61// "ProcessControl.Configurator.Page.Contro"...
0x4d556  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d55b  stloc.0
0x4d55c  br.s     loc_4D56E
0x4d55e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d563  ldstr    aProcesscontrol_23// "ProcessControl.Configurator.Stage.Title"...
0x4d568  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d56d  stloc.0
0x4d56e  ldloc.0
0x4d56f  ret
```
