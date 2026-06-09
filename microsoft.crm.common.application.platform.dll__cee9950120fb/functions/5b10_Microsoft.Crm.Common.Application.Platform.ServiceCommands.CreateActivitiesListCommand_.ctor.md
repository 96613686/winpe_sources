# Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::.ctor

- ea: `0x5b10`
- end: `0x5bd1`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::.ctor`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f60`

## pseudocode

```c

```

## disassembly

```asm
0x5b10  ldarg.0
0x5b11  ldstr    aList// "list"
0x5b16  ldarg.s  0xB
0x5b18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b1d  ldarg.s  0xB
0x5b1f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b24  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::.ctor()
0x5b29  stloc.0
0x5b2a  ldloc.0
0x5b2b  ldarg.1
0x5b2c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x5b31  ldloc.0
0x5b32  ldarg.2
0x5b33  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_FriendlyName(string)
0x5b38  ldloc.0
0x5b39  ldarg.3
0x5b3a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x5b3f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_Activity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x5b44  ldloc.0
0x5b45  ldarg.s  4
0x5b47  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x5b4c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5b51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5b56  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x5b5b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5b60  stloc.1
0x5b61  ldloc.0
0x5b62  ldloc.1
0x5b63  ldc.i4.0
0x5b64  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext, int32)
0x5b69  ldarg.s  6
0x5b6b  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions
0x5b70  ldtoken  [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PropagationOwnershipOptions
0x5b75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b7a  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x5b7f  unbox.any [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PropagationOwnershipOptions
0x5b84  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_OwnershipOptions(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PropagationOwnershipOptions)
0x5b89  ldloc.0
0x5b8a  ldarg.s  5
0x5b8c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_Propagate(bool)
0x5b91  ldloc.0
0x5b92  ldarg.s  9
0x5b94  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_sendEmail(bool)
0x5b99  ldloc.0
0x5b9a  ldc.i4.1
0x5b9b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_PostWorkflowEvent(bool)
0x5ba0  ldloc.0
0x5ba1  ldarg.s  0xA
0x5ba3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_QueueId(valuetype [mscorlib]System.Guid)
0x5ba8  ldarg.s  8
0x5baa  ldarg.0
0x5bab  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x5bb0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5bb5  stloc.2
0x5bb6  ldloc.0
0x5bb7  ldloc.2
0x5bb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5bbd  ldarg.s  7
0x5bbf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x5bc4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateActivitiesListRequest::set_Owner(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x5bc9  ldarg.0
0x5bca  ldloc.0
0x5bcb  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5bd0  ret
```
