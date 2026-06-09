# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSchemaParams

- ea: `0x2a00`
- end: `0x2aae`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetSchemaParams`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x200`
- `0x220`
- `0x360`

## pseudocode

```c

```

## disassembly

```asm
0x2a00  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2a05  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2a0a  stloc.0
0x2a0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2a15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2a1a  stloc.1
0x2a1b  ldarg.0
0x2a1c  ldarg.1
0x2a1d  ldstr    aSchemaname// "schemaname"
0x2a22  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2a27  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x2a2c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_Name(string)
0x2a31  ldarg.0
0x2a32  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_DisplayName()
0x2a37  ldloc.0
0x2a38  ldarg.1
0x2a39  ldstr    aSingularname// "singularname"
0x2a3e  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2a43  ldloc.1
0x2a44  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a49  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x2a4e  ldarg.0
0x2a4f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_DisplayCollectionName()
0x2a54  ldloc.0
0x2a55  ldarg.1
0x2a56  ldstr    aPluralname// "pluralname"
0x2a5b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2a60  ldloc.1
0x2a61  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a66  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x2a6b  ldarg.0
0x2a6c  ldarg.1
0x2a6d  ldstr    aOwnershiptype// "ownershiptype"
0x2a72  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x2a77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a7c  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0x2a81  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x2a86  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_OwnershipTypeMask(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes)
0x2a8b  ldarg.0
0x2a8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_Description()
0x2a91  ldloc.0
0x2a92  ldarg.1
0x2a93  ldstr    aDescription// "description"
0x2a98  ldsfld   string [mscorlib]System.String::Empty
0x2a9d  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x2aa2  ldloc.1
0x2aa3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2aa8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x2aad  ret
```
