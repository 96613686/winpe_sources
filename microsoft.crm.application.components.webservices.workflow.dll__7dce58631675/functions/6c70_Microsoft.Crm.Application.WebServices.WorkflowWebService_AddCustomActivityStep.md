# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddCustomActivityStep

- ea: `0x6c70`
- end: `0x6ce2`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddCustomActivityStep`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x6c70`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x6c70  ldarg.0
0x6c71  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6c76  ldarg.3
0x6c77  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6c7c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6c81  stloc.0
0x6c82  ldloc.0
0x6c83  ldarg.2
0x6c84  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6c89  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x6c8e  ldarg.0
0x6c8f  ldloc.0
0x6c90  ldarg.s  4
0x6c92  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6c97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6c9c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationSdkCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ca1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6ca6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6cab  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x6cb0  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.CustomActivityInfoMetadata::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x6cb5  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityFactory::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.ICustomActivityInfoProvider)
0x6cba  ldloc.0
0x6cbb  ldarg.1
0x6cbc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6cc1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.CustomActivityFactory::CreateCustomActivityStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [mscorlib]System.Guid)
0x6cc6  stloc.1
0x6cc7  ldloc.1
0x6cc8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x6ccd  ldarg.0
0x6cce  ldloc.0
0x6ccf  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x6cd4  stloc.2
0x6cd5  leave.s  loc_6CE0
0x6cd7  stloc.3
0x6cd8  ldarg.0
0x6cd9  ldloc.3
0x6cda  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x6cdf  throw
0x6ce0  ldloc.2
0x6ce1  ret
```
