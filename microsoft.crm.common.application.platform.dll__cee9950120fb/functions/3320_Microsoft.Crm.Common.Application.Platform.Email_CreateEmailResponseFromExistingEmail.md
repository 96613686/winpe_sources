# Microsoft.Crm.Common.Application.Platform.Email::CreateEmailResponseFromExistingEmail

- ea: `0x3320`
- end: `0x3374`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateEmailResponseFromExistingEmail`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3790`
- `0x3810`
- `0x39c0`

## callees

- `0x3380`
- `0x3410`
- `0x3450`

## pseudocode

```c

```

## disassembly

```asm
0x3320  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.AllColumns::.ctor()
0x3325  stloc.0
0x3326  ldstr    aEmail// "email"
0x332b  ldarg.1
0x332c  ldloc.0
0x332d  ldarg.0
0x332e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3333  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3338  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x333d  stloc.1
0x333e  ldloc.1
0x333f  ldstr    aActivityid// "activityid"
0x3344  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3349  ldloc.1
0x334a  ldstr    aStatecode// "statecode"
0x334f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3354  ldarg.0
0x3355  ldloc.1
0x3356  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x335b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_InnerEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x3360  ldarg.0
0x3361  call     instance void Microsoft.Crm.Common.Application.Platform.Email::ResetDirectionAndStateStatus()
0x3366  ldarg.0
0x3367  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsOwner()
0x336c  ldarg.0
0x336d  ldarg.2
0x336e  call     instance void Microsoft.Crm.Common.Application.Platform.Email::PrependSubjectWithPrefix(string prefix)
0x3373  ret
```
