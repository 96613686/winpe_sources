# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PopulateSelectCommand

- ea: `0x32f0`
- end: `0x3383`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PopulateSelectCommand`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2760`

## callees

- `0x3390`
- `0x3470`
- `0x13aa0`
- `0x13ac0`

## pseudocode

```c

```

## disassembly

```asm
0x32f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x32f5  stloc.0
0x32f6  ldstr    aSelectTop01Fro// "SELECT TOP {0} {1} FROM {2} WITH (NOLOC"...
0x32fb  stloc.1
0x32fc  ldarg.2
0x32fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x3302  ldc.i4.2
0x3303  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetDatabaseTargetName(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget)
0x3308  stloc.2
0x3309  ldarg.2
0x330a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x330f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3314  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x3319  stloc.3
0x331a  ldarg.0
0x331b  ldarg.2
0x331c  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PopulateColumnsToSelect(class EntityAttributeMetadataMap entityAttributeMetadataMap)
0x3321  stloc.s  4
0x3323  ldarg.0
0x3324  ldarg.2
0x3325  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> EntityAttributeMetadataMap::get_DateTimeAttributeMetadata()
0x332a  ldarg.s  4
0x332c  ldloc.3
0x332d  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::AddWhereClauseConditions(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> attributes, valuetype [mscorlib]System.Guid lastEntityId, string entityIdColumnName)
0x3332  stloc.s  5
0x3334  ldloc.0
0x3335  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x333a  ldloc.1
0x333b  ldc.i4.5
0x333c  newarr   [mscorlib]System.Object
0x3341  dup
0x3342  ldc.i4.0
0x3343  ldarg.3
0x3344  box      [mscorlib]System.Int32
0x3349  stelem.ref
0x334a  dup
0x334b  ldc.i4.1
0x334c  ldloc.s  4
0x334e  stelem.ref
0x334f  dup
0x3350  ldc.i4.2
0x3351  ldloc.2
0x3352  stelem.ref
0x3353  dup
0x3354  ldc.i4.3
0x3355  ldloc.s  5
0x3357  stelem.ref
0x3358  dup
0x3359  ldc.i4.4
0x335a  ldarg.2
0x335b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x3360  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3365  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x336a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x336f  stelem.ref
0x3370  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x3375  pop
0x3376  ldarg.1
0x3377  ldloc.0
0x3378  callvirt instance string [mscorlib]System.Object::ToString()
0x337d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3382  ret
```
