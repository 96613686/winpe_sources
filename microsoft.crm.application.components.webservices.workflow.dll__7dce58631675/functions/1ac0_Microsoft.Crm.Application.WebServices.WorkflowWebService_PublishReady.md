# Microsoft.Crm.Application.WebServices.WorkflowWebService::PublishReady

- ea: `0x1ac0`
- end: `0x1bc7`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::PublishReady`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x1ac0`
- `0x8bc0`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.0
0x1ac1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x1ac6  ldarg.1
0x1ac7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x1acc  stloc.0
0x1acd  ldstr    aWorkflow// "workflow"
0x1ad2  ldarg.1
0x1ad3  ldc.i4.5
0x1ad4  newarr   [mscorlib]System.String
0x1ad9  dup
0x1ada  ldc.i4.0
0x1adb  ldstr    aWorkflowid// "workflowid"
0x1ae0  stelem.ref
0x1ae1  dup
0x1ae2  ldc.i4.1
0x1ae3  ldstr    aType// "type"
0x1ae8  stelem.ref
0x1ae9  dup
0x1aea  ldc.i4.2
0x1aeb  ldstr    aOndemand// "ondemand"
0x1af0  stelem.ref
0x1af1  dup
0x1af2  ldc.i4.3
0x1af3  ldstr    aScope// "scope"
0x1af8  stelem.ref
0x1af9  dup
0x1afa  ldc.i4.4
0x1afb  ldstr    aSubprocess// "subprocess"
0x1b00  stelem.ref
0x1b01  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x1b06  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b10  stloc.1
0x1b11  ldloc.1
0x1b12  ldstr    aWorkflowid// "workflowid"
0x1b17  ldarg.1
0x1b18  box      [mscorlib]System.Guid
0x1b1d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b22  ldloc.0
0x1b23  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1b28  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_IsTemplate()
0x1b2d  brfalse.s loc_1B42
0x1b2f  ldloc.1
0x1b30  ldstr    aType// "type"
0x1b35  ldc.i4.3
0x1b36  box      [mscorlib]System.Int32
0x1b3b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b40  br.s     loc_1B53
0x1b42  ldloc.1
0x1b43  ldstr    aType// "type"
0x1b48  ldc.i4.1
0x1b49  box      [mscorlib]System.Int32
0x1b4e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b53  ldloc.1
0x1b54  ldstr    aOndemand// "ondemand"
0x1b59  ldloc.0
0x1b5a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1b5f  ldc.i4.4
0x1b60  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1b65  box      [mscorlib]System.Boolean
0x1b6a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b6f  ldloc.1
0x1b70  ldstr    aScope// "scope"
0x1b75  ldloc.0
0x1b76  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1b7b  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_Scope()
0x1b80  box      [mscorlib]System.Int32
0x1b85  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1b8a  ldloc.1
0x1b8b  ldstr    aSubprocess// "subprocess"
0x1b90  ldloc.0
0x1b91  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1b96  ldc.i4.8
0x1b97  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1b9c  box      [mscorlib]System.Boolean
0x1ba1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1ba6  ldloc.1
0x1ba7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bac  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bb1  ldarg.0
0x1bb2  ldloc.0
0x1bb3  ldc.i4.0
0x1bb4  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, bool bSave)
0x1bb9  stloc.2
0x1bba  leave.s  loc_1BC5
0x1bbc  stloc.3
0x1bbd  ldarg.0
0x1bbe  ldloc.3
0x1bbf  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x1bc4  throw
0x1bc5  ldloc.2
0x1bc6  ret
```
