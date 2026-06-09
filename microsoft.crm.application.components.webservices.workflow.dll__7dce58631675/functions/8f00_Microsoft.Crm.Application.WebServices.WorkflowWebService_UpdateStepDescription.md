# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription

- ea: `0x8f00`
- end: `0x8f19`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription`
- size: `25`
- prototype: ``
- caller_count: `62`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1bd0`
- `0x2030`
- `0x2290`
- `0x22e0`
- `0x2340`
- `0x27d0`
- `0x2820`
- `0x28b0`
- `0x2b40`
- `0x2d30`
- `0x3010`
- `0x3420`
- `0x3480`
- `0x3590`
- `0x3950`
- `0x3db0`
- `0x3e00`
- `0x3e50`
- `0x3ea0`
- `0x3f00`
- `0x4500`
- `0x4560`
- `0x45d0`
- `0x4630`
- `0x4680`
- `0x46e0`
- `0x4740`
- `0x47b0`
- `0x4810`
- `0x4860`
- `0x4940`
- `0x4a50`
- `0x4ab0`
- `0x4b20`
- `0x4cf0`
- `0x4d60`
- `0x4dd0`
- `0x4fd0`
- `0x5040`
- `0x50b0`
- `0x5290`
- `0x5300`
- `0x5370`
- `0x5690`
- `0x5700`
- `0x5770`
- `0x5a50`
- `0x5ac0`
- `0x5b30`
- `0x5d80`

## string_xrefs

- `0x8f05`: `Web.SFA.Workflow.CreateEntityDefaultDescription`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8f05  ldstr    aWebSfaWorkflow_1// "Web.SFA.Workflow.CreateEntityDefaultDes"...
0x8f0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8f0f  stloc.0
0x8f10  ldarg.1
0x8f11  ldarg.2
0x8f12  ldloc.0
0x8f13  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateStepDescriptions(string, string)
0x8f18  ret
```
