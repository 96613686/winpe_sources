# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::ValidateItemIsDeletable

- ea: `0x44ff0`
- end: `0x45192`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::ValidateItemIsDeletable`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x44fc0`

## callees

- `0x2f10`
- `0x444a0`
- `0x44ff0`
- `0x45490`
- `0x46230`
- `0x462a0`
- `0x66ae0`

## string_xrefs

- `0x4500d`: `componentstate`
- `0x45043`: `componentstate`
- `0x4501d`: `overwritetime`
- `0x45065`: `overwritetime`
- `0x450e4`: `{0} with id {1} cannot be deleted because a delete row already exists for this item, therefore it has already been deleted`
- `0x45148`: `{0} with id {1} cannot be deleted because it is a system record and system records of this type cannot be deleted`

## pseudocode

```c

```

## disassembly

```asm
0x44ff0  ldarg.2
0x44ff1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x44ff6  stloc.0
0x44ff7  ldarg.1
0x44ff8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x44ffd  ldloc.0
0x44ffe  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x45003  stloc.1
0x45004  ldloc.1
0x45005  ldc.i4.3
0x45006  newarr   [mscorlib]System.String
0x4500b  dup
0x4500c  ldc.i4.0
0x4500d  ldstr    aComponentstate// "componentstate"
0x45012  stelem.ref
0x45013  dup
0x45014  ldc.i4.1
0x45015  ldstr    aSolutionid_0// "solutionid"
0x4501a  stelem.ref
0x4501b  dup
0x4501c  ldc.i4.2
0x4501d  ldstr    aOverwritetime_0// "overwritetime"
0x45022  stelem.ref
0x45023  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[] attributeNames)
0x45028  ldarg.0
0x45029  ldarg.1
0x4502a  ldloc.1
0x4502b  ldloc.0
0x4502c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveTableRowsForMetadataEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker moniker, class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection columns, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x45031  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x45036  stloc.2
0x45037  br       loc_4517A
0x4503c  ldloc.2
0x4503d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x45042  dup
0x45043  ldstr    aComponentstate// "componentstate"
0x45048  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4504d  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x45052  stloc.3
0x45053  dup
0x45054  ldstr    aSolutionid_0// "solutionid"
0x45059  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4505e  unbox.any [mscorlib]System.Guid
0x45063  stloc.s  4
0x45065  ldstr    aOverwritetime_0// "overwritetime"
0x4506a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4506f  unbox.any [mscorlib]System.DateTime
0x45074  ldc.i4.1
0x45075  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x4507a  stloc.s  5
0x4507c  ldloc.3
0x4507d  ldc.i4.2
0x4507e  beq.s    loc_45087
0x45080  ldloc.3
0x45081  ldc.i4.3
0x45082  bne.un   loc_45116
0x45087  ldloc.s  5
0x45089  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x4508e  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x45093  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x45098  brfalse.s loc_45116
0x4509a  ldarg.1
0x4509b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x450a0  ldstr    aLocalizedlabel// "LocalizedLabel"
0x450a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x450aa  brtrue   loc_4517A
0x450af  ldarg.1
0x450b0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x450b5  ldstr    aAttributelooku// "AttributeLookupValue"
0x450ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x450bf  brtrue   loc_4517A
0x450c4  ldarg.0
0x450c5  ldarg.1
0x450c6  ldc.i4.1
0x450c7  ldloc.0
0x450c8  call     instance class Microsoft.Crm.Dependency.ComponentDefinition Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetComponentDefinition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker moniker, bool returnParentDefinitionIfLocalizedLabel, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x450cd  stloc.s  6
0x450cf  ldloc.s  6
0x450d1  brfalse.s loc_450DF
0x450d3  ldloc.s  6
0x450d5  callvirt instance bool Microsoft.Crm.Dependency.ComponentDefinition::get_AllowDeleteBaseSolutionRowAndFakeDeleteInSolutionUpgrade()
0x450da  brtrue   loc_4517A
0x450df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x450e4  ldstr    a0WithId1Cannot// "{0} with id {1} cannot be deleted becau"...
0x450e9  ldc.i4.2
0x450ea  newarr   [mscorlib]System.Object
0x450ef  dup
0x450f0  ldc.i4.0
0x450f1  ldarg.1
0x450f2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x450f7  stelem.ref
0x450f8  dup
0x450f9  ldc.i4.1
0x450fa  ldarg.1
0x450fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x45100  box      [mscorlib]System.Guid
0x45105  stelem.ref
0x45106  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4510b  ldc.i4   0x80040217
0x45110  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x45115  throw
0x45116  ldloc.s  4
0x45118  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x4511d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x45122  brtrue.s loc_4512E
0x45124  ldloc.s  4
0x45126  ldarg.2
0x45127  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4512c  brfalse.s loc_4517A
0x4512e  ldarg.1
0x4512f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x45134  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_AreSystemRecordsDeletable()
0x45139  brtrue.s loc_4517A
0x4513b  ldloc.0
0x4513c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemRecordsDeletableValidationDisabled()
0x45141  brtrue.s loc_4517A
0x45143  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45148  ldstr    a0WithId1Cannot_0// "{0} with id {1} cannot be deleted becau"...
0x4514d  ldc.i4.2
0x4514e  newarr   [mscorlib]System.Object
0x45153  dup
0x45154  ldc.i4.0
0x45155  ldarg.1
0x45156  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityName()
0x4515b  stelem.ref
0x4515c  dup
0x4515d  ldc.i4.1
0x4515e  ldarg.1
0x4515f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x45164  box      [mscorlib]System.Guid
0x45169  stelem.ref
0x4516a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4516f  ldc.i4   0x80044250
0x45174  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x45179  throw
0x4517a  ldloc.2
0x4517b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45180  brtrue   loc_4503C
0x45185  leave.s  loc_45191
0x45187  ldloc.2
0x45188  brfalse.s loc_45190
0x4518a  ldloc.2
0x4518b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45190  endfinally
0x45191  ret
```
