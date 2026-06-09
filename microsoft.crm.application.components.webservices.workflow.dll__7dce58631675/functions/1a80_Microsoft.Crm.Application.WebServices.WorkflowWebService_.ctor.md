# Microsoft.Crm.Application.WebServices.WorkflowWebService::.ctor

- ea: `0x1a80`
- end: `0x1aa6`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::.ctor`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1a80  ldarg.0
0x1a81  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::.ctor()
0x1a86  ldarg.0
0x1a87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a8c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a91  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ApplicationMetadataProvider::.ctor()
0x1a96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a9b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Workflow.ObjectModel.IServerMetadataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1aa0  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::_workflowAdapter
0x1aa5  ret
```
