# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStepPrameters

- ea: `0x49c0`
- end: `0x49e5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStepPrameters`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6d70`
- `0x7e70`

## pseudocode

```c

```

## disassembly

```asm
0x49c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x49c5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x49ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x49cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x49d4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x49d9  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.CustomActivityInfoMetadata::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x49de  ldarg.1
0x49df  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::RefreshCustomActivityStepInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep)
0x49e4  ret
```
