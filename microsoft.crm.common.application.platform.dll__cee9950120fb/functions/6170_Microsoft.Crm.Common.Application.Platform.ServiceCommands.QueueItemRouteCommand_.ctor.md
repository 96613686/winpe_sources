# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::.ctor

- ea: `0x6170`
- end: `0x6251`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::.ctor`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fe0`

## callees

- `0x6170`
- `0x6270`

## pseudocode

```c

```

## disassembly

```asm
0x6170  ldarg.0
0x6171  ldstr    aQueueitem// "queueitem"
0x6176  ldarg.s  6
0x6178  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x617d  ldarg.0
0x617e  ldarg.1
0x617f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::RetrieveQueuedObject(valuetype [mscorlib]System.Guid queueItemId)
0x6184  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x6189  dup
0x618a  ldstr    aObjectid// "objectid"
0x618f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x6194  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x6199  stloc.0
0x619a  ldloc.0
0x619b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x61a0  stloc.1
0x61a1  ldstr    aQueueid// "queueid"
0x61a6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x61ab  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x61b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x61b5  stloc.2
0x61b6  ldarg.s  6
0x61b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x61bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x61c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x61c7  ldloc.0
0x61c8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x61cd  ldc.i4.1
0x61ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x61d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x61d8  ldloc.1
0x61d9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x61de  stloc.3
0x61df  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::.ctor()
0x61e4  stloc.s  4
0x61e6  ldloc.s  4
0x61e8  ldloc.2
0x61e9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_SourceQueueId(valuetype [mscorlib]System.Guid)
0x61ee  ldloc.s  4
0x61f0  ldarg.2
0x61f1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_DestinationQueueId(valuetype [mscorlib]System.Guid)
0x61f6  ldloc.s  4
0x61f8  ldloc.3
0x61f9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x61fe  ldarg.s  5
0x6200  brtrue.s loc_6248
0x6202  ldstr    aQueueitem// "queueitem"
0x6207  ldarg.s  6
0x6209  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x620e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x6213  stloc.s  5
0x6215  ldloc.s  5
0x6217  ldstr    aWorkerid// "workerid"
0x621c  ldarg.3
0x621d  box      [mscorlib]System.Guid
0x6222  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x6227  ldloc.s  5
0x6229  ldstr    aWorkeridtype// "workeridtype"
0x622e  ldarg.s  4
0x6230  box      [mscorlib]System.Int32
0x6235  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x623a  ldloc.s  4
0x623c  ldloc.s  5
0x623e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x6243  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddToQueueRequest::set_QueueItemProperties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x6248  ldarg.0
0x6249  ldloc.s  4
0x624b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x6250  ret
```
