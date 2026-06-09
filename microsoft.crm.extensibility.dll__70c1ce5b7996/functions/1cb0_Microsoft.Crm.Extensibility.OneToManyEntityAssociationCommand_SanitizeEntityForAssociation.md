# Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::SanitizeEntityForAssociation

- ea: `0x1cb0`
- end: `0x1e1e`
- name: `Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::SanitizeEntityForAssociation`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1390`
- `0x1460`
- `0x1cb0`

## string_xrefs

- `0x1d27`: `Cannot create child entities before parent entity.`

## pseudocode

```c

```

## disassembly

```asm
0x1cb0  ldarg.0
0x1cb1  ldarg.1
0x1cb2  ldarg.0
0x1cb3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1cb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ReferencingEntityRelationshipRole [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_ReferencingEntityRole()
0x1cbd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_Entity()
0x1cc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x1cc7  call     instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole Microsoft.Crm.Extensibility.AssociateCommandBase::FindEntityRoleInRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, valuetype [mscorlib]System.Guid referencingEntityIdInRelationship)
0x1ccc  brtrue   loc_1D92
0x1cd1  ldarg.2
0x1cd2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1cd7  ldarg.0
0x1cd8  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship Microsoft.Crm.Extensibility.AssociateCommandBase::get_SdkRelationship()
0x1cdd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x1ce2  stloc.0
0x1ce3  ldloc.0
0x1ce4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1ce9  ldc.i4.0
0x1cea  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1cef  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x1cf4  stloc.2
0x1cf5  ldloca.s 2
0x1cf7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x1cfc  brtrue.s loc_1D01
0x1cfe  ldarg.3
0x1cff  br.s     loc_1D08
0x1d01  ldloca.s 2
0x1d03  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x1d08  stloc.1
0x1d09  ldarg.0
0x1d0a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1d0f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1d14  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1d19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsNullable()
0x1d1e  brtrue.s loc_1D33
0x1d20  ldloc.1
0x1d21  ldc.i4.1
0x1d22  bne.un   loc_1E1D
0x1d27  ldstr    aCannotCreateCh// "Cannot create child entities before par"...
0x1d2c  ldnull
0x1d2d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string, class [mscorlib]System.Exception)
0x1d32  throw
0x1d33  ldarg.2
0x1d34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1d39  ldarg.0
0x1d3a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1d3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1d44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1d49  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d4e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1d53  brfalse  loc_1E1D
0x1d58  ldloc.0
0x1d59  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1d5e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1d63  ldc.i4.0
0x1d64  ble      loc_1E1D
0x1d69  ldloc.1
0x1d6a  ldc.i4.1
0x1d6b  bne.un   loc_1E1D
0x1d70  ldarg.2
0x1d71  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1d76  ldarg.0
0x1d77  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1d7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1d81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1d86  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d8b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x1d90  pop
0x1d91  ret
0x1d92  ldarg.0
0x1d93  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1d98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1d9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1da2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsNullable()
0x1da7  brtrue.s loc_1E1D
0x1da9  ldarg.2
0x1daa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1daf  ldarg.0
0x1db0  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship Microsoft.Crm.Extensibility.AssociateCommandBase::get_SdkRelationship()
0x1db5  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x1dba  stloc.3
0x1dbb  ldloc.3
0x1dbc  brfalse.s loc_1E1D
0x1dbe  ldloc.3
0x1dbf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1dc4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1dc9  ldc.i4.0
0x1dca  ble.s    loc_1E1D
0x1dcc  ldarg.2
0x1dcd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x1dd2  stloc.s  4
0x1dd4  ldloc.3
0x1dd5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1dda  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1ddf  stloc.s  5
0x1de1  br.s     loc_1E06
0x1de3  ldloc.s  5
0x1de5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x1dea  ldarg.0
0x1deb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OneToManyEntityAssociationCommand::_oneToManyRelationship
0x1df0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x1df5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1dfa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1dff  ldloc.s  4
0x1e01  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e06  ldloc.s  5
0x1e08  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e0d  brtrue.s loc_1DE3
0x1e0f  leave.s  loc_1E1D
0x1e11  ldloc.s  5
0x1e13  brfalse.s loc_1E1C
0x1e15  ldloc.s  5
0x1e17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e1c  endfinally
0x1e1d  ret
```
