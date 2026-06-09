# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::ValidatePublishableReferencedItemIntegrity

- ea: `0x45630`
- end: `0x45753`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::ValidatePublishableReferencedItemIntegrity`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x45550`

## callees

- `0x44620`
- `0x45630`
- `0x46000`
- `0x462a0`
- `0x465f0`
- `0x46630`
- `0x46640`

## string_xrefs

- `0x4565e`: `componentstate`
- `0x456ef`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x45630  ldarg.1
0x45631  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x45636  ldarg.2
0x45637  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4563c  stloc.0
0x4563d  ldloc.0
0x4563e  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x45643  ldc.i4.2
0x45644  newarr   [mscorlib]System.String
0x45649  dup
0x4564a  ldc.i4.0
0x4564b  ldarg.1
0x4564c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x45651  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x45656  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x4565b  stelem.ref
0x4565c  dup
0x4565d  ldc.i4.1
0x4565e  ldstr    aComponentstate// "componentstate"
0x45663  stelem.ref
0x45664  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[] attributeNames)
0x45669  ldloc.0
0x4566a  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4566f  ldarg.1
0x45670  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x45675  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x4567a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x4567f  ldc.i4.1
0x45680  newarr   [mscorlib]System.Object
0x45685  dup
0x45686  ldc.i4.0
0x45687  ldarg.1
0x45688  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x4568d  box      [mscorlib]System.Guid
0x45692  stelem.ref
0x45693  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, class [mscorlib]System.Array values)
0x45698  ldarg.0
0x45699  ldloc.0
0x4569a  ldarg.2
0x4569b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultipleAsIfPublished(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x456a0  stloc.1
0x456a1  ldloc.1
0x456a2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x456a7  brtrue.s loc_456E0
0x456a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x456ae  ldstr    aMetadataObject// "metadata object {0} with id {1} cannot "...
0x456b3  ldc.i4.2
0x456b4  newarr   [mscorlib]System.Object
0x456b9  dup
0x456ba  ldc.i4.0
0x456bb  ldarg.1
0x456bc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x456c1  stelem.ref
0x456c2  dup
0x456c3  ldc.i4.1
0x456c4  ldarg.1
0x456c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x456ca  box      [mscorlib]System.Guid
0x456cf  stelem.ref
0x456d0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x456d5  ldc.i4   0x80040217
0x456da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x456df  throw
0x456e0  ldloc.1
0x456e1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x456e6  stloc.2
0x456e7  br.s     loc_4573E
0x456e9  ldloc.2
0x456ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x456ef  ldstr    aComponentstate// "componentstate"
0x456f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x456f9  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x456fe  stloc.3
0x456ff  ldloc.3
0x45700  ldc.i4.2
0x45701  beq.s    loc_45707
0x45703  ldloc.3
0x45704  ldc.i4.3
0x45705  bne.un.s loc_4573E
0x45707  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4570c  ldstr    aMetadataObject// "metadata object {0} with id {1} cannot "...
0x45711  ldc.i4.2
0x45712  newarr   [mscorlib]System.Object
0x45717  dup
0x45718  ldc.i4.0
0x45719  ldarg.1
0x4571a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x4571f  stelem.ref
0x45720  dup
0x45721  ldc.i4.1
0x45722  ldarg.1
0x45723  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x45728  box      [mscorlib]System.Guid
0x4572d  stelem.ref
0x4572e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x45733  ldc.i4   0x80040217
0x45738  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4573d  throw
0x4573e  ldloc.2
0x4573f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45744  brtrue.s loc_456E9
0x45746  leave.s  loc_45752
0x45748  ldloc.2
0x45749  brfalse.s loc_45751
0x4574b  ldloc.2
0x4574c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45751  endfinally
0x45752  ret
```
