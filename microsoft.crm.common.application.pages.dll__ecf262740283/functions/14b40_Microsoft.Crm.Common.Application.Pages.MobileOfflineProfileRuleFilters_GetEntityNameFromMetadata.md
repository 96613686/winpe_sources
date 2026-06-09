# Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::GetEntityNameFromMetadata

- ea: `0x14b40`
- end: `0x14ccf`
- name: `Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::GetEntityNameFromMetadata`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14aa0`

## callees

- `0x14b40`

## pseudocode

```c

```

## disassembly

```asm
0x14b40  ldsfld   string [mscorlib]System.String::Empty
0x14b45  stloc.0
0x14b46  ldarg.1
0x14b47  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFromEntityRelationships()
0x14b4c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::GetEnumerator()
0x14b51  stloc.1
0x14b52  br.s     loc_14B99
0x14b54  ldloc.1
0x14b55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Current()
0x14b5a  stloc.2
0x14b5b  ldloc.2
0x14b5c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x14b61  ldarg.2
0x14b62  ldc.i4.5
0x14b63  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14b68  brfalse.s loc_14B99
0x14b6a  ldloc.2
0x14b6b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRelationships()
0x14b70  ldc.i4.0
0x14b71  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationships>::get_Item(!!T0)
0x14b76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationships::get_RelationshipId()
0x14b7b  stloc.3
0x14b7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14b81  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14b86  ldloc.3
0x14b87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRelationship(valuetype [mscorlib]System.Guid)
0x14b8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14b91  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14b96  stloc.0
0x14b97  leave.s  loc_14BAD
0x14b99  ldloc.1
0x14b9a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14b9f  brtrue.s loc_14B54
0x14ba1  leave.s  loc_14BAD
0x14ba3  ldloc.1
0x14ba4  brfalse.s loc_14BAC
0x14ba6  ldloc.1
0x14ba7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14bac  endfinally
0x14bad  ldarg.1
0x14bae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesToEntityRelationships()
0x14bb3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::GetEnumerator()
0x14bb8  stloc.1
0x14bb9  br.s     loc_14C05
0x14bbb  ldloc.1
0x14bbc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Current()
0x14bc1  stloc.s  4
0x14bc3  ldloc.s  4
0x14bc5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x14bca  ldarg.2
0x14bcb  ldc.i4.5
0x14bcc  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14bd1  brfalse.s loc_14C05
0x14bd3  ldloc.s  4
0x14bd5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRelationshipsCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRelationships()
0x14bda  ldc.i4.0
0x14bdb  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationships>::get_Item(!!T0)
0x14be0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationships::get_RelationshipId()
0x14be5  stloc.s  5
0x14be7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14bec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14bf1  ldloc.s  5
0x14bf3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRelationship(valuetype [mscorlib]System.Guid)
0x14bf8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x14bfd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14c02  stloc.0
0x14c03  leave.s  loc_14C19
0x14c05  ldloc.1
0x14c06  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14c0b  brtrue.s loc_14BBB
0x14c0d  leave.s  loc_14C19
0x14c0f  ldloc.1
0x14c10  brfalse.s loc_14C18
0x14c12  ldloc.1
0x14c13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14c18  endfinally
0x14c19  ldarg.1
0x14c1a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ManyToManyEntityRelationships()
0x14c1f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::GetEnumerator()
0x14c24  stloc.1
0x14c25  br       loc_14CB6
0x14c2a  ldloc.1
0x14c2b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Current()
0x14c30  stloc.s  6
0x14c32  ldloc.s  6
0x14c34  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x14c39  ldarg.2
0x14c3a  ldc.i4.5
0x14c3b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14c40  brfalse.s loc_14CB6
0x14c42  ldloc.s  6
0x14c44  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship
0x14c49  dup
0x14c4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::get_AssociationEntityRelationshipRoles()
0x14c4f  stloc.s  7
0x14c51  ldloc.s  7
0x14c53  ldc.i4.0
0x14c54  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Item(!!T0)
0x14c59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityRelationshipRoleId()
0x14c5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::GetOtherEntityRelationshipRoleInRelationship(valuetype [mscorlib]System.Guid)
0x14c63  dup
0x14c64  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole::get_ManyToManyRelationship()
0x14c69  ldarg.1
0x14c6a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x14c6f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::GetRelationshipInvolvingEntity(valuetype [mscorlib]System.Guid)
0x14c74  stloc.s  8
0x14c76  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole::get_ManyToManyRelationship()
0x14c7b  ldloc.s  8
0x14c7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_Id()
0x14c82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::GetOtherRelationship(valuetype [mscorlib]System.Guid)
0x14c87  stloc.s  9
0x14c89  ldarg.3
0x14c8a  ldloc.s  8
0x14c8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14c91  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x14c96  bne.un.s loc_14CA7
0x14c98  ldloc.s  9
0x14c9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14c9f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14ca4  stloc.0
0x14ca5  leave.s  loc_14CCD
0x14ca7  ldloc.s  8
0x14ca9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x14cae  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14cb3  stloc.0
0x14cb4  leave.s  loc_14CCD
0x14cb6  ldloc.1
0x14cb7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14cbc  brtrue   loc_14C2A
0x14cc1  leave.s  loc_14CCD
0x14cc3  ldloc.1
0x14cc4  brfalse.s loc_14CCC
0x14cc6  ldloc.1
0x14cc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ccc  endfinally
0x14ccd  ldloc.0
0x14cce  ret
```
