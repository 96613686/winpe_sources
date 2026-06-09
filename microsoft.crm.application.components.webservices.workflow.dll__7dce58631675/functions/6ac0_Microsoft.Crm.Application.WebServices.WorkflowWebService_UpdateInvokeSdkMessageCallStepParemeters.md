# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters

- ea: `0x6ac0`
- end: `0x6b11`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters`
- size: `81`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6100`
- `0x61a0`
- `0x6360`
- `0x7e70`

## callees

- `0x6ac0`

## pseudocode

```c

```

## disassembly

```asm
0x6ac0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6ac5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6aca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6acf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6ad4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x6ad9  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.CustomActivityInfoMetadata::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x6ade  stloc.0
0x6adf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6ae4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6ae9  ldc.i4.0
0x6aea  ldc.i4.0
0x6aeb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x6af0  stloc.1
0x6af1  ldloc.0
0x6af2  castclass [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase
0x6af7  ldloc.1
0x6af8  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::set_Context(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6afd  ldloc.0
0x6afe  ldarg.1
0x6aff  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider::RefreshInvokeSdkMessageStepInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep)
0x6b04  leave.s  loc_6B10
0x6b06  ldloc.1
0x6b07  brfalse.s loc_6B0F
0x6b09  ldloc.1
0x6b0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b0f  endfinally
0x6b10  ret
```
