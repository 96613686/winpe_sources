# Microsoft.Crm.Common.Application.Platform.Template::Create

- ea: `0x4b70`
- end: `0x4be1`
- name: `Microsoft.Crm.Common.Application.Platform.Template::Create`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4b70`

## pseudocode

```c

```

## disassembly

```asm
0x4b70  ldc.i4.0
0x4b71  stloc.0
0x4b72  ldc.i4.0
0x4b73  stloc.1
0x4b74  ldarg.0
0x4b75  ldstr    aIspersonal// "ispersonal"
0x4b7a  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4b7f  brfalse.s loc_4BA0
0x4b81  ldc.i4.1
0x4b82  stloc.0
0x4b83  ldarg.0
0x4b84  ldstr    aIspersonal// "ispersonal"
0x4b89  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4b8e  unbox.any [mscorlib]System.Boolean
0x4b93  stloc.1
0x4b94  ldarg.0
0x4b95  ldstr    aIspersonal// "ispersonal"
0x4b9a  ldnull
0x4b9b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4ba0  ldarg.0
0x4ba1  ldarg.1
0x4ba2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create(bool)
0x4ba7  ldloc.0
0x4ba8  brfalse.s loc_4BE0
0x4baa  ldloc.1
0x4bab  brtrue.s loc_4BE0
0x4bad  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOrgEmailTemplates()
0x4bb2  ldc.i4.3
0x4bb3  ldarg.0
0x4bb4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4bb9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4bbe  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4bc3  brfalse.s loc_4BE0
0x4bc5  ldarg.0
0x4bc6  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x4bcb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4bd0  ldarg.0
0x4bd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4bd6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4bdb  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::MakeAvailableToOrganizationTemplate(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4be0  ret
```
