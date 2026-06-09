# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetOption

- ea: `0x9d90`
- end: `0x9e16`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetOption`
- size: `134`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9850`
- `0x9a10`
- `0x9bd0`

## pseudocode

```c

```

## disassembly

```asm
0x9d90  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9d9a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9d9f  stloc.0
0x9da0  ldarg.s  4
0x9da2  ldarg.2
0x9da3  ldloc.0
0x9da4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9da9  stloc.1
0x9daa  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x9daf  stloc.2
0x9db0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x9db5  stloc.3
0x9db6  ldloc.2
0x9db7  ldloc.1
0x9db8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9dbd  ldloc.0
0x9dbe  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9dc3  dup
0x9dc4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x9dc9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_AttributePicklistValueId(valuetype [mscorlib]System.Guid)
0x9dce  dup
0x9dcf  ldarg.0
0x9dd0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Value(int32)
0x9dd5  dup
0x9dd6  ldarg.s  6
0x9dd8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ExternalValue(string)
0x9ddd  dup
0x9dde  ldarg.1
0x9ddf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Color(string)
0x9de4  dup
0x9de5  ldarg.s  5
0x9de7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ParentValues(class [mscorlib]System.Collections.Generic.IList`1<int32>)
0x9dec  ldloc.2
0x9ded  ldloc.3
0x9dee  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x9df3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider)
0x9df8  ldarg.s  4
0x9dfa  ldarg.3
0x9dfb  ldloc.0
0x9dfc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e01  stloc.s  4
0x9e03  dup
0x9e04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Descriptions()
0x9e09  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x9e0e  ldloc.s  4
0x9e10  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9e15  ret
```
