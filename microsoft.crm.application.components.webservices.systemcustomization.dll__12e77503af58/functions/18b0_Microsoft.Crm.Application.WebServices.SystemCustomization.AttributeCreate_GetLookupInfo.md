# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetLookupInfo

- ea: `0x18b0`
- end: `0x18d2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetLookupInfo`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`
- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x18ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x18bf  stloc.0
0x18c0  ldarg.0
0x18c1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x18c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_AttributeLookupValues()
0x18cb  ldloc.0
0x18cc  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.LookupAttributeInfo::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18d1  ret
```
