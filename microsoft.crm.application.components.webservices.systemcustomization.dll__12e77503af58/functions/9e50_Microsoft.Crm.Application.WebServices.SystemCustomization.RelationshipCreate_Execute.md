# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::Execute

- ea: `0x9e50`
- end: `0x9fd3`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::Execute`
- size: `387`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6380`
- `0xaf20`
- `0xb180`

## callees

- `0x200`
- `0x220`
- `0x9e50`
- `0x9fe0`
- `0xa0c0`

## pseudocode

```c

```

## disassembly

```asm
0x9e50  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateRelationship()
0x9e55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e5a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e5f  brtrue.s loc_9E72
0x9e61  ldc.i4   0x80040277
0x9e66  ldc.i4.0
0x9e67  newarr   [mscorlib]System.Object
0x9e6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9e71  throw
0x9e72  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9e77  stloc.0
0x9e78  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::.ctor()
0x9e7d  stloc.1
0x9e7e  ldarg.1
0x9e7f  ldstr    aSchemaname2// "schemaname2"
0x9e84  ldstr    asc_10614// ""
0x9e89  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9e8e  ldstr    asc_10614// ""
0x9e93  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9e98  brfalse  loc_9F62
0x9e9d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x9ea2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x9ea7  ldc.i4.0
0x9ea8  ldc.i4.0
0x9ea9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x9eae  stloc.2
0x9eaf  ldloc.2
0x9eb0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9eb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x9eba  ldc.i4.0
0x9ebb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x9ec0  ldarg.1
0x9ec1  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetRelationshipCreateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x9ec6  stloc.3
0x9ec7  ldloc.3
0x9ec8  ldstr    aAccount// "account"
0x9ecd  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string)
0x9ed2  ldloc.3
0x9ed3  ldarg.1
0x9ed4  ldstr    aSchemaname// "schemaname"
0x9ed9  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9ede  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string)
0x9ee3  ldloc.3
0x9ee4  ldc.i4.1
0x9ee5  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsPartOfPolymorphicRelationships(bool)
0x9eea  ldloc.3
0x9eeb  ldstr    aCustomer// "customer"
0x9ef0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeTypeName(string)
0x9ef5  ldarg.1
0x9ef6  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetRelationshipCreateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x9efb  stloc.s  4
0x9efd  ldloc.s  4
0x9eff  ldstr    aContact// "contact"
0x9f04  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string)
0x9f09  ldloc.s  4
0x9f0b  ldarg.1
0x9f0c  ldstr    aSchemaname2// "schemaname2"
0x9f11  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9f16  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string)
0x9f1b  ldloc.s  4
0x9f1d  ldc.i4.1
0x9f1e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsPartOfPolymorphicRelationships(bool)
0x9f23  ldloc.s  4
0x9f25  ldstr    aCustomer// "customer"
0x9f2a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeTypeName(string)
0x9f2f  ldc.i4.2
0x9f30  newarr   [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo
0x9f35  dup
0x9f36  ldc.i4.0
0x9f37  ldloc.3
0x9f38  stelem.ref
0x9f39  dup
0x9f3a  ldc.i4.1
0x9f3b  ldloc.s  4
0x9f3d  stelem.ref
0x9f3e  stloc.s  5
0x9f40  ldloc.1
0x9f41  ldloc.s  5
0x9f43  ldloc.2
0x9f44  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Create(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipCreateInfo[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9f49  ldc.i4.0
0x9f4a  ldelem   [mscorlib]System.Guid
0x9f4f  stloc.0
0x9f50  ldloc.2
0x9f51  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x9f56  leave.s  loc_9FC7
0x9f58  ldloc.2
0x9f59  brfalse.s loc_9F61
0x9f5b  ldloc.2
0x9f5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9f61  endfinally
0x9f62  ldarg.1
0x9f63  ldstr    aManytomany// "manytomany"
0x9f68  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9f6d  ldstr    aFalse// "false"
0x9f72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9f77  brfalse.s loc_9FA1
0x9f79  ldarg.1
0x9f7a  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetRelationshipCreateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x9f7f  stloc.s  6
0x9f81  ldloc.1
0x9f82  ldloc.s  6
0x9f84  ldarg.0
0x9f85  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9f8a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9f8f  brtrue.s loc_9F94
0x9f91  ldarg.0
0x9f92  br.s     loc_9F99
0x9f94  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x9f99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Create(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipCreateInfo, valuetype [mscorlib]System.Guid)
0x9f9e  stloc.0
0x9f9f  br.s     loc_9FC7
0x9fa1  ldarg.1
0x9fa2  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetManyToManyRelationshipCreateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x9fa7  stloc.s  7
0x9fa9  ldloc.1
0x9faa  ldloc.s  7
0x9fac  ldarg.0
0x9fad  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9fb2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9fb7  brtrue.s loc_9FBC
0x9fb9  ldarg.0
0x9fba  br.s     loc_9FC1
0x9fbc  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x9fc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipService::Create(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IRelationshipCreateInfo, valuetype [mscorlib]System.Guid)
0x9fc6  stloc.0
0x9fc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9fcc  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9fd1  ldloc.0
0x9fd2  ret
```
