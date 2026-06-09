# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ConvertToSolutionComponentEntity

- ea: `0xb8d70`
- end: `0xb8dc7`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::ConvertToSolutionComponentEntity`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb8d20`

## string_xrefs

- `0xb8d85`: `componenttype`
- `0xb8d8b`: `requiredcomponenttype`
- `0xb8da1`: `requiredcomponentbasesolutionid`
- `0xb8db7`: `requiredcomponentobjectid`

## pseudocode

```c

```

## disassembly

```asm
0xb8d70  ldc.i4   0x1BBF
0xb8d75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb8d7a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb8d7f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xb8d84  dup
0xb8d85  ldstr    aComponenttype// "componenttype"
0xb8d8a  ldarg.1
0xb8d8b  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0xb8d90  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8d95  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb8d9a  dup
0xb8d9b  ldstr    aSolutionid// "solutionid"
0xb8da0  ldarg.1
0xb8da1  ldstr    aRequiredcompon_1// "requiredcomponentbasesolutionid"
0xb8da6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8dab  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb8db0  dup
0xb8db1  ldstr    aObjectid// "objectid"
0xb8db6  ldarg.1
0xb8db7  ldstr    aRequiredcompon_2// "requiredcomponentobjectid"
0xb8dbc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8dc1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xb8dc6  ret
```
