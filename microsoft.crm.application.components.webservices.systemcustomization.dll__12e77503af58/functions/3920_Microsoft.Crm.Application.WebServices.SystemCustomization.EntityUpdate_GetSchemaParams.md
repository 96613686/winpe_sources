# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSchemaParams

- ea: `0x3920`
- end: `0x399b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSchemaParams`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x200`
- `0x220`
- `0x3920`

## pseudocode

```c

```

## disassembly

```asm
0x3920  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x3925  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x392a  stloc.0
0x392b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3930  stloc.1
0x3931  ldarg.1
0x3932  ldstr    aSingularname// "singularname"
0x3937  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x393c  brfalse.s loc_399A
0x393e  ldarg.0
0x393f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayName()
0x3944  ldloc.0
0x3945  ldarg.1
0x3946  ldstr    aSingularname// "singularname"
0x394b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x3950  ldloc.1
0x3951  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3956  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x395b  ldarg.0
0x395c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayCollectionName()
0x3961  ldloc.0
0x3962  ldarg.1
0x3963  ldstr    aPluralname// "pluralname"
0x3968  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x396d  ldloc.1
0x396e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3973  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x3978  ldarg.0
0x3979  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDescription()
0x397e  ldloc.0
0x397f  ldarg.1
0x3980  ldstr    aDescription// "description"
0x3985  ldsfld   string [mscorlib]System.String::Empty
0x398a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x398f  ldloc.1
0x3990  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3995  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x399a  ret
```
