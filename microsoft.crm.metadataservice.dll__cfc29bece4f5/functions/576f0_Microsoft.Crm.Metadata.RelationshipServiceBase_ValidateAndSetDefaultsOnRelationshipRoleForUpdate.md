# Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateAndSetDefaultsOnRelationshipRoleForUpdate

- ea: `0x576f0`
- end: `0x578a9`
- name: `Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateAndSetDefaultsOnRelationshipRoleForUpdate`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x57410`

## callees

- `0x576f0`
- `0x578b0`
- `0x57940`

## string_xrefs

- `0x5778e`: `Entity relationship role {0} should use a custom label for display but the custom labels are being deleted`
- `0x5787f`: `Entity relationship role {0} should use a custom label for display but the custom labels are being deleted`
- `0x57820`: `Entity relationship role {0} should use a custom label for display but the custom labels are not being provided and none already exist`

## pseudocode

```c

```

## disassembly

```asm
0x576f0  ldarg.0
0x576f1  ldarg.2
0x576f2  ldarg.3
0x576f3  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateNavPaneIsCustomizable(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag differenceReferencingRelationshipRoleData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingReferencingRelationshipRoleData)
0x576f8  ldarg.0
0x576f9  ldarg.1
0x576fa  ldarg.2
0x576fb  ldarg.s  6
0x576fd  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateNavPaneOrder(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescriptionPropertyBag differenceReferencingRelationshipRoleData, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x57702  ldarg.2
0x57703  ldstr    aNavpanedisplay// "navpanedisplayoption"
0x57708  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x5770d  brfalse  loc_57849
0x57712  ldarg.2
0x57713  ldstr    aNavpanedisplay// "navpanedisplayoption"
0x57718  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x5771d  unbox.any [mscorlib]System.Byte
0x57722  dup
0x57723  ldc.i4.2
0x57724  beq.s    loc_5776C
0x57726  ldarg.2
0x57727  ldstr    aNavpanearea// "navpanearea"
0x5772c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x57731  brtrue.s loc_57747
0x57733  ldarg.3
0x57734  ldstr    aNavpanearea// "navpanearea"
0x57739  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5773e  brfalse.s loc_57747
0x57740  ldarg.2
0x57741  ldc.i4.0
0x57742  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneArea(int32)
0x57747  ldarg.2
0x57748  ldstr    aNavpaneorder// "navpaneorder"
0x5774d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x57752  brtrue.s loc_5776C
0x57754  ldarg.3
0x57755  ldstr    aNavpaneorder// "navpaneorder"
0x5775a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x5775f  brfalse.s loc_5776C
0x57761  ldarg.2
0x57762  ldc.i4   0x2710
0x57767  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::set_NavPaneOrder(int32)
0x5776c  ldc.i4.1
0x5776d  bne.un   loc_578A8
0x57772  ldarg.s  4
0x57774  brfalse.s loc_577B7
0x57776  ldarg.s  4
0x57778  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x5777d  brtrue   loc_578A8
0x57782  ldarg.s  5
0x57784  brtrue   loc_578A8
0x57789  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5778e  ldstr    aEntityRelation_1// "Entity relationship role {0} should use"...
0x57793  ldc.i4.1
0x57794  newarr   [mscorlib]System.Object
0x57799  dup
0x5779a  ldc.i4.0
0x5779b  ldarg.2
0x5779c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x577a1  box      [mscorlib]System.Guid
0x577a6  stelem.ref
0x577a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x577ac  ldc.i4   0x80044328
0x577b1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x577b6  throw
0x577b7  ldstr    aLocalizedlabel// "LocalizedLabel"
0x577bc  ldarg.s  6
0x577be  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x577c3  stloc.0
0x577c4  ldloc.0
0x577c5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x577ca  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x577cf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x577d4  ldloc.0
0x577d5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x577da  ldstr    aObjectid// "objectid"
0x577df  ldarg.2
0x577e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x577e5  box      [mscorlib]System.Guid
0x577ea  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, object)
0x577ef  ldloc.0
0x577f0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x577f5  ldstr    aObjectcolumnna// "objectcolumnname"
0x577fa  ldstr    aCustomlabel// "CustomLabel"
0x577ff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, object)
0x57804  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x57809  ldloc.0
0x5780a  ldarg.s  6
0x5780c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x57811  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x57816  brtrue   loc_578A8
0x5781b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57820  ldstr    aEntityRelation_2// "Entity relationship role {0} should use"...
0x57825  ldc.i4.1
0x57826  newarr   [mscorlib]System.Object
0x5782b  dup
0x5782c  ldc.i4.0
0x5782d  ldarg.2
0x5782e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x57833  box      [mscorlib]System.Guid
0x57838  stelem.ref
0x57839  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5783e  ldc.i4   0x80044328
0x57843  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x57848  throw
0x57849  ldarg.s  4
0x5784b  brfalse.s loc_578A8
0x5784d  ldarg.3
0x5784e  ldstr    aNavpanedisplay// "navpanedisplayoption"
0x57853  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x57858  brtrue.s loc_578A8
0x5785a  ldarg.3
0x5785b  ldstr    aNavpanedisplay// "navpanedisplayoption"
0x57860  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57865  unbox.any [mscorlib]System.Byte
0x5786a  ldc.i4.1
0x5786b  bne.un.s loc_578A8
0x5786d  ldarg.s  4
0x5786f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x57874  brtrue.s loc_578A8
0x57876  ldarg.s  5
0x57878  brtrue.s loc_578A8
0x5787a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5787f  ldstr    aEntityRelation_1// "Entity relationship role {0} should use"...
0x57884  ldc.i4.1
0x57885  newarr   [mscorlib]System.Object
0x5788a  dup
0x5788b  ldc.i4.0
0x5788c  ldarg.2
0x5788d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleDescription::get_EntityRelationshipRoleId()
0x57892  box      [mscorlib]System.Guid
0x57897  stelem.ref
0x57898  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5789d  ldc.i4   0x80044328
0x578a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x578a7  throw
0x578a8  ret
```
