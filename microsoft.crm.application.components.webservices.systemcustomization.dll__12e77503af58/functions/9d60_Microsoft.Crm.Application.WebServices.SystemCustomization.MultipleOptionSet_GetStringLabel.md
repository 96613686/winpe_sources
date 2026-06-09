# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel

- ea: `0x9d60`
- end: `0x9d82`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a10`
- `0x9bd0`

## pseudocode

```c

```

## disassembly

```asm
0x9d60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9d6a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9d6f  stloc.0
0x9d70  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9d75  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x9d7a  ldarg.0
0x9d7b  ldloc.0
0x9d7c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d81  ret
```
