# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCustomActivityStep

- ea: `0x6cf0`
- end: `0x6d65`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCustomActivityStep`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x6cf0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x6cf0  ldarg.0
0x6cf1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6cf6  ldarg.3
0x6cf7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6cfc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6d01  stloc.0
0x6d02  ldloc.0
0x6d03  ldarg.2
0x6d04  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6d09  ldarg.0
0x6d0a  ldloc.0
0x6d0b  ldarg.s  4
0x6d0d  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6d12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6d17  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6d1c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6d21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6d26  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x6d2b  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.CustomActivityInfoMetadata::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x6d30  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityFactory::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider)
0x6d35  ldloc.0
0x6d36  ldarg.1
0x6d37  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6d3c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityFactory::CreateCustomActivityStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [mscorlib]System.Guid)
0x6d41  stloc.1
0x6d42  ldarg.0
0x6d43  ldarg.s  5
0x6d45  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x6d4a  ldloc.1
0x6d4b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x6d50  ldarg.0
0x6d51  ldloc.0
0x6d52  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x6d57  stloc.2
0x6d58  leave.s  loc_6D63
0x6d5a  stloc.3
0x6d5b  ldarg.0
0x6d5c  ldloc.3
0x6d5d  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x6d62  throw
0x6d63  ldloc.2
0x6d64  ret
```
