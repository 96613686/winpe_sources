# Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert_11

- ea: `0x9460`
- end: `0x98aa`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert_11`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9a80`

## callees

- `0x8b10`
- `0x9460`
- `0x98b0`
- `0xa940`
- `0xaa40`
- `0xabe0`
- `0x496d0`
- `0x496f0`
- `0x49710`
- `0x49730`

## string_xrefs

- `0x9602`: `cascadedelete`
- `0x97f7`: `NavigationProperty Name of Referencing Relationship Role cannot be updated for OOB relationship.`
- `0x9839`: `NavigationProperty Name of Referenced Relationship Role cannot be updated for OOB relationship.`

## pseudocode

```c

```

## disassembly

```asm
0x9460  ldstr    aEntityrelation_3// "EntityRelationship"
0x9465  ldarg.0
0x9466  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x946b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9470  stloc.0
0x9471  ldarg.0
0x9472  ldarg.1
0x9473  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x9478  ldc.i4.8
0x9479  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.Metadata.MetadataConverter::Convert(string name, valuetype ConversionQualifier qualifier)
0x947e  stloc.1
0x947f  ldloc.0
0x9480  ldstr    aEntityrelation// "entityrelationshipid"
0x9485  ldloc.1
0x9486  box      [mscorlib]System.Guid
0x948b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x9490  ldarg.1
0x9491  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_IsHierarchical()
0x9496  stloc.s  5
0x9498  ldloca.s 5
0x949a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x949f  brfalse.s loc_94B7
0x94a1  ldloc.0
0x94a2  ldstr    aIshierarchical// "ishierarchical"
0x94a7  ldarg.1
0x94a8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_IsHierarchical()
0x94ad  box      valuetype [mscorlib]System.Nullable`1<bool>
0x94b2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x94b7  ldarg.1
0x94b8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsCustomizable()
0x94bd  ldloc.0
0x94be  ldstr    aIscustomizable// "iscustomizable"
0x94c3  call     void Microsoft.Crm.Sdk.Metadata.MetadataConverter::ExtractBooleanManagedProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty property, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity retval, string index)
0x94c8  ldloc.0
0x94c9  newobj   instance void Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityRelationshipDescription)
0x94ce  stloc.2
0x94cf  ldstr    aRelationship_0// "Relationship"
0x94d4  ldarg.0
0x94d5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x94da  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x94df  stloc.3
0x94e0  ldarg.1
0x94e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x94e6  brfalse  loc_966B
0x94eb  ldarg.1
0x94ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x94f1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Assign()
0x94f6  stloc.s  6
0x94f8  ldloca.s 6
0x94fa  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x94ff  brfalse.s loc_952B
0x9501  ldloc.3
0x9502  ldstr    aCascadeassign// "cascadeassign"
0x9507  ldarg.0
0x9508  ldarg.1
0x9509  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x950e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Assign()
0x9513  stloc.s  6
0x9515  ldloca.s 6
0x9517  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x951c  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x9521  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x9526  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x952b  ldarg.1
0x952c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x9531  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Share()
0x9536  stloc.s  6
0x9538  ldloca.s 6
0x953a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x953f  brfalse.s loc_956B
0x9541  ldloc.3
0x9542  ldstr    aCascadeshare// "cascadeshare"
0x9547  ldarg.0
0x9548  ldarg.1
0x9549  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x954e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Share()
0x9553  stloc.s  6
0x9555  ldloca.s 6
0x9557  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x955c  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x9561  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x9566  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x956b  ldarg.1
0x956c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x9571  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Unshare()
0x9576  stloc.s  6
0x9578  ldloca.s 6
0x957a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x957f  brfalse.s loc_95AB
0x9581  ldloc.3
0x9582  ldstr    aCascadeunshare// "cascadeunshare"
0x9587  ldarg.0
0x9588  ldarg.1
0x9589  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x958e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Unshare()
0x9593  stloc.s  6
0x9595  ldloca.s 6
0x9597  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x959c  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x95a1  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x95a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x95ab  ldarg.1
0x95ac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x95b1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Reparent()
0x95b6  stloc.s  6
0x95b8  ldloca.s 6
0x95ba  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x95bf  brfalse.s loc_95EB
0x95c1  ldloc.3
0x95c2  ldstr    aCascadereparen// "cascadereparent"
0x95c7  ldarg.0
0x95c8  ldarg.1
0x95c9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x95ce  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Reparent()
0x95d3  stloc.s  6
0x95d5  ldloca.s 6
0x95d7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x95dc  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x95e1  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x95e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x95eb  ldarg.1
0x95ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x95f1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Delete()
0x95f6  stloc.s  6
0x95f8  ldloca.s 6
0x95fa  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x95ff  brfalse.s loc_962B
0x9601  ldloc.3
0x9602  ldstr    aCascadedelete// "cascadedelete"
0x9607  ldarg.0
0x9608  ldarg.1
0x9609  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x960e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_Delete()
0x9613  stloc.s  6
0x9615  ldloca.s 6
0x9617  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x961c  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x9621  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x9626  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x962b  ldarg.1
0x962c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x9631  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_RollupView()
0x9636  stloc.s  6
0x9638  ldloca.s 6
0x963a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_HasValue()
0x963f  brfalse.s loc_966B
0x9641  ldloc.3
0x9642  ldstr    aCascaderollupv// "cascaderollupview"
0x9647  ldarg.0
0x9648  ldarg.1
0x9649  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x964e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration::get_RollupView()
0x9653  stloc.s  6
0x9655  ldloca.s 6
0x9657  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType>::get_Value()
0x965c  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetCascadeLinkType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeType cascadeType)
0x9661  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x9666  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x966b  ldarg.1
0x966c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsValidForAdvancedFind()
0x9671  stloc.s  5
0x9673  ldloca.s 5
0x9675  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x967a  brfalse.s loc_969B
0x967c  ldloc.3
0x967d  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0x9682  ldarg.1
0x9683  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsValidForAdvancedFind()
0x9688  stloc.s  5
0x968a  ldloca.s 5
0x968c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9691  box      [mscorlib]System.Boolean
0x9696  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x969b  ldloc.2
0x969c  ldloc.3
0x969d  callvirt instance void Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::set_RelationshipDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity value)
0x96a2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::.ctor()
0x96a7  stloc.s  4
0x96a9  ldarg.1
0x96aa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_AssociatedMenuConfiguration()
0x96af  brfalse  loc_98A8
0x96b4  ldarg.1
0x96b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_AssociatedMenuConfiguration()
0x96ba  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuBehavior> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration::get_Behavior()
0x96bf  stloc.s  7
0x96c1  ldloca.s 7
0x96c3  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuBehavior>::get_HasValue()
0x96c8  brtrue.s loc_96F0
0x96ca  ldarg.1
0x96cb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_AssociatedMenuConfiguration()
0x96d0  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration::get_Order()
0x96d5  stloc.s  8
0x96d7  ldloca.s 8
0x96d9  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x96de  brtrue.s loc_96F0
0x96e0  ldarg.1
0x96e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_AssociatedMenuConfiguration()
0x96e6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration::get_Label()
0x96eb  brfalse  loc_98A8
0x96f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x96f5  dup
0x96f6  ldstr    aEntityrelation_1// "entityrelationshiproleid"
0x96fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9700  stloc.s  9
0x9702  ldarg.0
0x9703  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x9708  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::CheckIfNavigationPropertyNameAttributeExists(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x970d  brfalse.s loc_971B
0x970f  ldloc.s  9
0x9711  ldstr    aNavigationprop// "navigationpropertyname"
0x9716  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x971b  ldloc.s  4
0x971d  ldloc.1
0x971e  ldloc.s  9
0x9720  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x9725  ldc.i4.1
0x9726  ldarg.0
0x9727  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x972c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x9731  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::RetrieveRolesByEntityRelationshipAndRoleTypeAsIfPublished(valuetype [mscorlib]System.Guid, string[], valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x9736  stloc.s  0xA
0x9738  ldloc.s  0xA
0x973a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x973f  brtrue.s loc_9765
0x9741  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9746  ldstr    aTheEntityRelat// "The entity relationship {0} either does"...
0x974b  ldc.i4.1
0x974c  newarr   [mscorlib]System.Object
0x9751  dup
0x9752  ldc.i4.0
0x9753  ldarg.1
0x9754  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x9759  stelem.ref
0x975a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x975f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x9764  throw
0x9765  ldloc.s  4
0x9767  ldloc.1
0x9768  ldloc.s  9
0x976a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x976f  ldc.i4.0
0x9770  ldarg.0
0x9771  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x9776  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x977b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::RetrieveRolesByEntityRelationshipAndRoleTypeAsIfPublished(valuetype [mscorlib]System.Guid, string[], valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x9780  stloc.s  0xB
0x9782  ldloc.s  0xB
0x9784  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x9789  brtrue.s loc_97AF
0x978b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9790  ldstr    aTheEntityRelat_0// "The entity relationship {0} either does"...
0x9795  ldc.i4.1
0x9796  newarr   [mscorlib]System.Object
0x979b  dup
0x979c  ldc.i4.0
0x979d  ldarg.1
0x979e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_SchemaName()
0x97a3  stelem.ref
0x97a4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x97ae  throw
0x97af  ldarg.0
0x97b0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Sdk.Metadata.MetadataConverter::_context
0x97b5  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityRelationshipRoleService::CheckIfNavigationPropertyNameAttributeExists(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x97ba  brfalse  loc_984F
0x97bf  ldarg.0
0x97c0  ldarg.1
0x97c1  call     instance bool Microsoft.Crm.Sdk.Metadata.MetadataConverter::IsCustomRelationship(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase relationship)
0x97c6  brtrue   loc_984F
0x97cb  ldarg.1
0x97cc  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingEntityNavigationPropertyName()
0x97d1  brfalse.s loc_980D
0x97d3  ldloc.s  0xA
0x97d5  ldc.i4.0
0x97d6  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x97db  ldstr    aNavigationprop// "navigationpropertyname"
0x97e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x97e5  ldarg.1
0x97e6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingEntityNavigationPropertyName()
0x97eb  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x97f0  brtrue.s loc_980D
0x97f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97f7  ldstr    aNavigationprop_0// "NavigationProperty Name of Referencing "...
0x97fc  ldc.i4.0
0x97fd  newarr   [mscorlib]System.Object
0x9802  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9807  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x980c  throw
0x980d  ldarg.1
0x980e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedEntityNavigationPropertyName()
0x9813  brfalse.s loc_984F
0x9815  ldloc.s  0xB
0x9817  ldc.i4.0
0x9818  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x981d  ldstr    aNavigationprop// "navigationpropertyname"
0x9822  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x9827  ldarg.1
0x9828  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedEntityNavigationPropertyName()
0x982d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9832  brtrue.s loc_984F
  ... truncated ...
```
