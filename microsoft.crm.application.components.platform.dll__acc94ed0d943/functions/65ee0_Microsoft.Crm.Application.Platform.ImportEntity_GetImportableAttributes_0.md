# Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributes_0

- ea: `0x65ee0`
- end: `0x65ff9`
- name: `Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributes_0`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x65ed0`
- `0x66cc0`

## callees

- `0xe910`
- `0xfd20`
- `0x65e40`
- `0x65ee0`
- `0x66000`

## string_xrefs

- `0x65ee7`: `createdon`
- `0x65eff`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x65ee0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x65ee5  stloc.0
0x65ee6  ldloc.0
0x65ee7  ldstr    aCreatedon// "createdon"
0x65eec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65ef1  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_OverrideCreatedOnCreatedBy()
0x65ef6  ldarg.2
0x65ef7  call     bool Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition pd, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x65efc  brtrue.s loc_65F09
0x65efe  ldloc.0
0x65eff  ldstr    aOverriddencrea// "overriddencreatedon"
0x65f04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65f09  ldloc.0
0x65f0a  ldarg.0
0x65f0b  call     class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributesExclusionList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x65f10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x65f15  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x65f1a  stloc.1
0x65f1b  ldarg.0
0x65f1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x65f21  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x65f26  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x65f2b  stloc.2
0x65f2c  br       loc_65FD6
0x65f31  ldloc.2
0x65f32  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x65f37  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x65f3c  stloc.3
0x65f3d  ldloc.0
0x65f3e  ldloc.3
0x65f3f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x65f44  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x65f49  brtrue   loc_65FD6
0x65f4e  ldloc.3
0x65f4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x65f54  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65f59  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x65f5e  brtrue.s loc_65FD6
0x65f60  ldarg.1
0x65f61  brfalse.s loc_65F84
0x65f63  ldloc.3
0x65f64  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x65f69  brtrue.s loc_65FBD
0x65f6b  ldloc.3
0x65f6c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x65f71  brtrue.s loc_65FBD
0x65f73  ldloc.3
0x65f74  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x65f79  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x65f7e  ldc.i4.s 0xE
0x65f80  beq.s    loc_65FBD
0x65f82  br.s     loc_65FD6
0x65f84  ldloc.3
0x65f85  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x65f8a  brtrue.s loc_65F9B
0x65f8c  ldloc.3
0x65f8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x65f92  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x65f97  ldc.i4.s 0xE
0x65f99  bne.un.s loc_65FD6
0x65f9b  ldloc.3
0x65f9c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForCreate()
0x65fa1  brfalse.s loc_65FBD
0x65fa3  ldloc.3
0x65fa4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x65fa9  brfalse.s loc_65FBD
0x65fab  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x65fb0  ldloc.3
0x65fb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x65fb6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeCreatePrivilege(valuetype [mscorlib]System.Guid)
0x65fbb  brfalse.s loc_65FD6
0x65fbd  ldloc.3
0x65fbe  call     string Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x65fc3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x65fc8  brtrue.s loc_65FD6
0x65fca  ldloc.1
0x65fcb  ldloc.3
0x65fcc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x65fd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65fd6  ldloc.2
0x65fd7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x65fdc  brtrue   loc_65F31
0x65fe1  leave.s  loc_65FF7
0x65fe3  ldloc.2
0x65fe4  isinst   [mscorlib]System.IDisposable
0x65fe9  stloc.s  4
0x65feb  ldloc.s  4
0x65fed  brfalse.s loc_65FF6
0x65fef  ldloc.s  4
0x65ff1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65ff6  endfinally
0x65ff7  ldloc.1
0x65ff8  ret
```
