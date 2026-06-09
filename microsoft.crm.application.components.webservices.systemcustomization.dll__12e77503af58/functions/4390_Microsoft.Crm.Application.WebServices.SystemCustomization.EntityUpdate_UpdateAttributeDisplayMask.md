# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateAttributeDisplayMask

- ea: `0x4390`
- end: `0x43ef`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateAttributeDisplayMask`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4230`

## callees

- `0x4390`

## pseudocode

```c

```

## disassembly

```asm
0x4390  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteAttribute()
0x4395  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x439a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x439f  brtrue.s loc_43B2
0x43a1  ldc.i4   0x80040277
0x43a6  ldc.i4.0
0x43a7  newarr   [mscorlib]System.Object
0x43ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x43b1  throw
0x43b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x43b7  stloc.0
0x43b8  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::.ctor()
0x43bd  ldarg.2
0x43be  ldloc.0
0x43bf  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x43c4  stloc.1
0x43c5  ldloc.1
0x43c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x43cb  ldarg.3
0x43cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x43d1  ldarg.1
0x43d2  ldloc.1
0x43d3  ldc.i4.1
0x43d4  ldarg.0
0x43d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x43da  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x43df  brtrue.s loc_43E4
0x43e1  ldarg.0
0x43e2  br.s     loc_43E9
0x43e4  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x43e9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo, bool, valuetype [mscorlib]System.Guid)
0x43ee  ret
```
