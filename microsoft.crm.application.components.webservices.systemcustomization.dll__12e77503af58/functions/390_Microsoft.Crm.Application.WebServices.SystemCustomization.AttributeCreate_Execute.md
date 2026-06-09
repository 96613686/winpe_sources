# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::Execute

- ea: `0x390`
- end: `0x413`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::Execute`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6240`
- `0xaf20`

## callees

- `0x290`
- `0x330`
- `0x390`
- `0x420`
- `0x1ed0`

## string_xrefs

- `0x3cb`: `linkedattributecreaterequired`

## pseudocode

```c

```

## disassembly

```asm
0x390  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateAttribute()
0x395  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x39f  brtrue.s loc_3B2
0x3a1  ldc.i4   0x80040277
0x3a6  ldc.i4.0
0x3a7  newarr   [mscorlib]System.Object
0x3ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3b1  throw
0x3b2  ldarg.1
0x3b3  ldstr    aEntityid// "entityid"
0x3b8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3bd  stloc.0
0x3be  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::.ctor()
0x3c3  ldarg.1
0x3c4  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3c9  stloc.1
0x3ca  ldarg.1
0x3cb  ldstr    aLinkedattribut// "linkedattributecreaterequired"
0x3d0  ldc.i4.0
0x3d1  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3d6  brfalse.s loc_3EC
0x3d8  ldarg.0
0x3d9  ldarg.1
0x3da  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::CreateLinkedAttribute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3df  stloc.2
0x3e0  ldloc.1
0x3e1  ldloc.2
0x3e2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3e7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_LinkedAttributeId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x3ec  ldloc.0
0x3ed  ldloc.1
0x3ee  ldarg.0
0x3ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f9  brtrue.s loc_3FE
0x3fb  ldarg.0
0x3fc  br.s     loc_403
0x3fe  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x403  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeService::Create(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo, valuetype [mscorlib]System.Guid)
0x408  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x40d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x412  ret
```
