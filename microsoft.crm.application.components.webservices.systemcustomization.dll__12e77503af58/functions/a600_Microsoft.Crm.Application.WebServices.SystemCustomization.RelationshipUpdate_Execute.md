# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::Execute

- ea: `0xa600`
- end: `0xa6ae`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::Execute`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb1b0`

## callees

- `0x220`
- `0x330`
- `0xa600`
- `0xa6b0`
- `0xa7f0`

## pseudocode

```c

```

## disassembly

```asm
0xa600  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteRelationship()
0xa605  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa60a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa60f  brtrue.s loc_A622
0xa611  ldc.i4   0x80040277
0xa616  ldc.i4.0
0xa617  newarr   [mscorlib]System.Object
0xa61c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa621  throw
0xa622  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xa627  stloc.0
0xa628  ldarg.1
0xa629  ldstr    aEntityrelation// "entityrelationshipid"
0xa62e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0xa633  stloc.1
0xa634  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::.ctor()
0xa639  stloc.2
0xa63a  ldarg.1
0xa63b  ldstr    aManytomany// "manytomany"
0xa640  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa645  ldstr    aFalse// "false"
0xa64a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa64f  brfalse.s loc_A67A
0xa651  ldarg.1
0xa652  ldloc.0
0xa653  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetRelationshipUpdateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xa658  stloc.3
0xa659  ldloc.2
0xa65a  ldloc.1
0xa65b  ldloc.3
0xa65c  ldc.i4.1
0xa65d  ldarg.0
0xa65e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa663  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa668  brtrue.s loc_A66D
0xa66a  ldarg.0
0xa66b  br.s     loc_A672
0xa66d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xa672  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0xa677  pop
0xa678  br.s     loc_A6A3
0xa67a  ldarg.1
0xa67b  ldloc.0
0xa67c  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipUpdateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetManyToManyRelationshipUpdateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xa681  stloc.s  4
0xa683  ldloc.2
0xa684  ldloc.1
0xa685  ldloc.s  4
0xa687  ldc.i4.1
0xa688  ldarg.0
0xa689  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa68e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa693  brtrue.s loc_A698
0xa695  ldarg.0
0xa696  br.s     loc_A69D
0xa698  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0xa69d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0xa6a2  pop
0xa6a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6a8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa6ad  ret
```
