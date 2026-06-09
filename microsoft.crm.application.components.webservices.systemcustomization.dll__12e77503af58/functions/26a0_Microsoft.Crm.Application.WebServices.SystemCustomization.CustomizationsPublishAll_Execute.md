# Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublishAll::Execute

- ea: `0x26a0`
- end: `0x26d4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublishAll::Execute`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xad80`
- `0xb2c0`

## callees

- `0x26a0`

## pseudocode

```c

```

## disassembly

```asm
0x26a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x26a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26aa  brfalse.s loc_26B8
0x26ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x26b1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26b6  brtrue.s loc_26C9
0x26b8  ldc.i4   0x80040277
0x26bd  ldc.i4.0
0x26be  newarr   [mscorlib]System.Object
0x26c3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x26c8  throw
0x26c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x26ce  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::PublishAllXml(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26d3  ret
```
