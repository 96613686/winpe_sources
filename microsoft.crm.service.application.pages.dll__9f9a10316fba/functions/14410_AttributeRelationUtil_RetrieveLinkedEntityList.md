# AttributeRelationUtil::RetrieveLinkedEntityList

- ea: `0x14410`
- end: `0x14518`
- name: `AttributeRelationUtil::RetrieveLinkedEntityList`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xcb80`

## callees

- `0x14410`
- `0x14560`

## pseudocode

```c

```

## disassembly

```asm
0x14410  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x14415  stloc.0
0x14416  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1441b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x14420  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x14425  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1442a  ldarg.1
0x1442b  ldc.i4.1
0x1442c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x14431  stloc.1
0x14432  ldnull
0x14433  stloc.2
0x14434  ldarg.3
0x14435  brfalse  loc_14516
0x1443a  ldloc.1
0x1443b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencingEntityRoles()
0x14440  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0x14445  stloc.3
0x14446  br       loc_144FF
0x1444b  ldloc.3
0x1444c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0x14451  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencingEntityRelationshipRole
0x14456  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencingEntityRelationshipRole::get_OneToManyRelationship()
0x1445b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x14460  stloc.s  4
0x14462  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x14467  brtrue.s loc_1447A
0x14469  ldloc.s  4
0x1446b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14470  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x14475  brfalse  loc_144FF
0x1447a  ldarg.2
0x1447b  brfalse.s loc_14491
0x1447d  ldloc.s  4
0x1447f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14484  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14489  ldarg.2
0x1448a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1448f  brtrue.s loc_144FF
0x14491  ldloc.s  4
0x14493  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_IsValidForAdvancedFind()
0x14498  brfalse.s loc_144FF
0x1449a  ldloc.s  4
0x1449c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x144a1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x144a6  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.FetchUtility::CheckReadPrivilege(int32)
0x144ab  brfalse.s loc_144FF
0x144ad  ldloc.s  4
0x144af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x144b4  stloc.2
0x144b5  ldloc.2
0x144b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x144bb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x144c0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x144c5  brfalse.s loc_144E2
0x144c7  ldarg.0
0x144c8  ldloc.2
0x144c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x144ce  ldloc.2
0x144cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AggregateOf()
0x144d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid)
0x144d9  call     instance string AttributeRelationUtil::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attrMeta)
0x144de  stloc.s  5
0x144e0  br.s     loc_144EB
0x144e2  ldarg.0
0x144e3  ldloc.2
0x144e4  call     instance string AttributeRelationUtil::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attrMeta)
0x144e9  stloc.s  5
0x144eb  ldloc.0
0x144ec  ldloc.s  4
0x144ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x144f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x144f8  ldloc.s  5
0x144fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x144ff  ldloc.3
0x14500  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14505  brtrue   loc_1444B
0x1450a  leave.s  loc_14516
0x1450c  ldloc.3
0x1450d  brfalse.s loc_14515
0x1450f  ldloc.3
0x14510  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14515  endfinally
0x14516  ldloc.0
0x14517  ret
```
