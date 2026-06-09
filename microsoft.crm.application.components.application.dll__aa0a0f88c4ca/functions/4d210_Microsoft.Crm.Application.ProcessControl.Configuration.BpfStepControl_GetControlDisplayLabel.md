# Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::GetControlDisplayLabel

- ea: `0x4d210`
- end: `0x4d2a6`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::GetControlDisplayLabel`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4d0b0`
- `0x4d4e0`

## callees

- `0x4d210`
- `0x4d380`

## string_xrefs

- `0x4d23e`: `ProcessControl.Configurator.NewStep`
- `0x4d299`: `ProcessControl.Configurator.NewField`
- `0x4d26a`: `ProcessControl.Configurator.Stage.Title.PageStepNewLabel`

## pseudocode

```c

```

## disassembly

```asm
0x4d210  ldarg.0
0x4d211  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_Step()
0x4d216  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x4d21b  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Count()
0x4d220  ldc.i4.0
0x4d221  ble.s    loc_4D294
0x4d223  ldarg.0
0x4d224  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_Step()
0x4d229  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x4d22e  ldc.i4.0
0x4d22f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x4d234  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x4d239  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d23e  ldstr    aProcesscontrol_3// "ProcessControl.Configurator.NewStep"
0x4d243  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d248  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4d24d  brfalse.s loc_4D294
0x4d24f  ldarg.0
0x4d250  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_Step()
0x4d255  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x4d25a  ldc.i4.0
0x4d25b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x4d260  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x4d265  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d26a  ldstr    aProcesscontrol_21// "ProcessControl.Configurator.Stage.Title"...
0x4d26f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d274  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4d279  brfalse.s loc_4D294
0x4d27b  ldarg.0
0x4d27c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_Step()
0x4d281  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x4d286  ldc.i4.0
0x4d287  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::get_Item(int32)
0x4d28c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x4d291  stloc.0
0x4d292  br.s     loc_4D2A4
0x4d294  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d299  ldstr    aProcesscontrol_5// "ProcessControl.Configurator.NewField"
0x4d29e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d2a3  stloc.0
0x4d2a4  ldloc.0
0x4d2a5  ret
```
