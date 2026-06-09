# Microsoft.Crm.Common.Application.Platform.ServiceCommands.UploadDocumentCommand::.ctor

- ea: `0x64f0`
- end: `0x6580`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.UploadDocumentCommand::.ctor`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x64f0  ldarg.0
0x64f1  ldstr    aSharepointdocu// "SharePointDocument"
0x64f6  ldarg.s  8
0x64f8  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x64fd  ldstr    aSharepointdocu_0// "sharepointdocument"
0x6502  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x6507  stloc.0
0x6508  ldloc.0
0x6509  ldstr    aTitle// "title"
0x650e  ldarg.2
0x650f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x6514  ldloc.0
0x6515  ldstr    aFiletype// "filetype"
0x651a  ldarg.3
0x651b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x6520  ldloc.0
0x6521  ldstr    aLocationid// "locationid"
0x6526  ldarg.s  7
0x6528  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x652d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6532  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6537  ldarg.s  5
0x6539  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x653e  stloc.1
0x653f  ldloc.0
0x6540  ldstr    aRegardingobjec// "regardingobjectid"
0x6545  ldloc.1
0x6546  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x654b  ldarg.s  6
0x654d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6552  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x6557  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x655c  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::.ctor()
0x6561  stloc.2
0x6562  ldloc.2
0x6563  ldarg.1
0x6564  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::set_Content(unsigned int8[])
0x6569  ldloc.2
0x656a  ldloc.0
0x656b  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::set_Entity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x6570  ldloc.2
0x6571  ldarg.s  4
0x6573  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UploadDocumentRequest::set_OverwriteExisting(bool)
0x6578  ldarg.0
0x6579  ldloc.2
0x657a  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x657f  ret
```
