# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityInfo

- ea: `0x9c0`
- end: `0xa0a`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityInfo`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x630`

## pseudocode

```c

```

## disassembly

```asm
0x9c0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::.ctor()
0x9c5  dup
0x9c6  ldarg.1
0x9c7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9cc  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::EntityTypeCode
0x9d1  dup
0x9d2  ldarg.1
0x9d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x9d8  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::EntityLogicalName
0x9dd  dup
0x9de  ldarg.1
0x9df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x9e4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9e9  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x9ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9f8  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::DisplayName
0x9fd  dup
0x9fe  ldarg.1
0x9ff  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0xa04  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::IsActivity
0xa09  ret
```
