# Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert_14

- ea: `0x9ae0`
- end: `0x9cb0`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert_14`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9a80`

## callees

- `0x8b10`
- `0x98b0`
- `0x9ae0`
- `0xa940`
- `0xaa40`
- `0xc810`
- `0x49780`
- `0x497a0`
- `0x497c0`

## string_xrefs

- `0x9bf3`: `Navigation Property Name of Relationship Role cannot be updated for OOB relationship.`
- `0x9c47`: `Navigation Property Name of Relationship Role cannot be updated for OOB relationship.`

## pseudocode

```c

```

## disassembly

```asm
0x9ae0  ldstr    aEntityrelation_3// "EntityRelationship"
0x9ae5  ldarg.0
0x9ae6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x9aeb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9af0  stloc.0
0x9af1  ldarg.0
0x9af2  ldarg.1
0x9af3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x9af8  ldc.i4.8
0x9af9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert(string name, valuetype ConversionQualifier qualifier)
0x9afe  stloc.1
0x9aff  ldloc.0
0x9b00  ldstr    aEntityrelation// "entityrelationshipid"
0x9b05  ldloc.1
0x9b06  box      [mscorlib]System.Guid
0x9b0b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x9b10  ldarg.1
0x9b11  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsCustomizable()
0x9b16  ldloc.0
0x9b17  ldstr    aIscustomizable// "iscustomizable"
0x9b1c  call     void Microsoft.Crm.Sdk.Metadata.MetadataConverter::ExtractBooleanManagedProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty property, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity retval, string index)
0x9b21  ldloc.0
0x9b22  ldarg.1
0x9b23  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsValidForAdvancedFind()
0x9b28  newobj   instance void Microsoft.Crm.Metadata.ManyToManyRelationshipUpdateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipDescription, valuetype [mscorlib]System.Nullable`1<bool> isValidForAdvancedFind)
0x9b2d  stloc.2
0x9b2e  ldarg.0
0x9b2f  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataLoader Microsoft.Crm.Sdk.Metadata.MetadataConverter::_loader
0x9b34  ldloc.1
0x9b35  ldc.i4.2
0x9b36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Sdk.Metadata.MetadataLoader::LoadEntityRelationshipRoles(valuetype [mscorlib]System.Guid entityRelationshipId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType roleType)
0x9b3b  stloc.3
0x9b3c  ldloc.3
0x9b3d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x9b42  newarr   [mscorlib]System.Guid
0x9b47  stloc.s  4
0x9b49  ldc.i4.0
0x9b4a  stloc.s  5
0x9b4c  br.s     loc_9B8F
0x9b4e  ldloc.3
0x9b4f  ldloc.s  5
0x9b51  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9b56  ldstr    aAssociationrol// "associationroleordinal"
0x9b5b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9b60  unbox.any [mscorlib]System.Int32
0x9b65  stloc.s  6
0x9b67  ldloc.s  4
0x9b69  ldloc.s  6
0x9b6b  ldc.i4.1
0x9b6c  sub
0x9b6d  ldloc.3
0x9b6e  ldloc.s  5
0x9b70  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9b75  ldstr    aEntityrelation_1// "entityrelationshiproleid"
0x9b7a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9b7f  unbox.any [mscorlib]System.Guid
0x9b84  stelem   [mscorlib]System.Guid
0x9b89  ldloc.s  5
0x9b8b  ldc.i4.1
0x9b8c  add
0x9b8d  stloc.s  5
0x9b8f  ldloc.s  5
0x9b91  ldloc.3
0x9b92  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x9b97  blt.s    loc_9B4E
0x9b99  ldarg.0
0x9b9a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x9b9f  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::CheckIfNavigationPropertyNameAttributeExists(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ba4  brfalse  loc_9C5D
0x9ba9  ldarg.0
0x9baa  ldarg.1
0x9bab  call     instance bool Microsoft.Crm.Sdk.Metadata.MetadataConverter::IsCustomRelationship(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase relationship)
0x9bb0  brtrue   loc_9C5D
0x9bb5  ldloc.3
0x9bb6  ldc.i4.0
0x9bb7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9bbc  ldstr    aNavigationprop// "navigationpropertyname"
0x9bc1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9bc6  brfalse.s loc_9C09
0x9bc8  ldarg.1
0x9bc9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1NavigationPropertyName()
0x9bce  brfalse.s loc_9C09
0x9bd0  ldloc.3
0x9bd1  ldc.i4.0
0x9bd2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9bd7  ldstr    aNavigationprop// "navigationpropertyname"
0x9bdc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9be1  ldarg.1
0x9be2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1NavigationPropertyName()
0x9be7  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9bec  brtrue.s loc_9C09
0x9bee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9bf3  ldstr    aNavigationProp// "Navigation Property Name of Relationshi"...
0x9bf8  ldc.i4.0
0x9bf9  newarr   [mscorlib]System.Object
0x9bfe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9c03  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x9c08  throw
0x9c09  ldloc.3
0x9c0a  ldc.i4.1
0x9c0b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9c10  ldstr    aNavigationprop// "navigationpropertyname"
0x9c15  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9c1a  brfalse.s loc_9C5D
0x9c1c  ldarg.1
0x9c1d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2NavigationPropertyName()
0x9c22  brfalse.s loc_9C5D
0x9c24  ldloc.3
0x9c25  ldc.i4.1
0x9c26  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x9c2b  ldstr    aNavigationprop// "navigationpropertyname"
0x9c30  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9c35  ldarg.1
0x9c36  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2NavigationPropertyName()
0x9c3b  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9c40  brtrue.s loc_9C5D
0x9c42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c47  ldstr    aNavigationProp// "Navigation Property Name of Relationshi"...
0x9c4c  ldc.i4.0
0x9c4d  newarr   [mscorlib]System.Object
0x9c52  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9c57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x9c5c  throw
0x9c5d  ldloc.s  4
0x9c5f  ldlen
0x9c60  conv.i4
0x9c61  ldc.i4.2
0x9c62  ceq
0x9c64  ldstr    aThereShouldBeT// "There should be two and only two associ"...
0x9c69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9c6e  ldloc.2
0x9c6f  ldarg.0
0x9c70  ldloc.s  4
0x9c72  ldc.i4.0
0x9c73  ldelem   [mscorlib]System.Guid
0x9c78  ldarg.1
0x9c79  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1AssociatedMenuConfiguration()
0x9c7e  ldarg.1
0x9c7f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1NavigationPropertyName()
0x9c84  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Sdk.Metadata.MetadataConverter::CreateEntityRelationshipRoleForUpdate(valuetype [mscorlib]System.Guid entityRelationshipRoleId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration associatedMenuConfiguration, string navigationpropertyname)
0x9c89  callvirt instance void Microsoft.Crm.Metadata.ManyToManyRelationshipUpdateData::set_EntityOneRelationshipRole(class Microsoft.Crm.Metadata.EntityRelationshipRoleData value)
0x9c8e  ldloc.2
0x9c8f  ldarg.0
0x9c90  ldloc.s  4
0x9c92  ldc.i4.1
0x9c93  ldelem   [mscorlib]System.Guid
0x9c98  ldarg.1
0x9c99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2AssociatedMenuConfiguration()
0x9c9e  ldarg.1
0x9c9f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2NavigationPropertyName()
0x9ca4  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Sdk.Metadata.MetadataConverter::CreateEntityRelationshipRoleForUpdate(valuetype [mscorlib]System.Guid entityRelationshipRoleId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration associatedMenuConfiguration, string navigationpropertyname)
0x9ca9  callvirt instance void Microsoft.Crm.Metadata.ManyToManyRelationshipUpdateData::set_EntityTwoRelationshipRole(class Microsoft.Crm.Metadata.EntityRelationshipRoleData value)
0x9cae  ldloc.2
0x9caf  ret
```
