# Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeRollupView

- ea: `0x53bf0`
- end: `0x53cf5`
- name: `Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeRollupView`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x538d0`

## callees

- `0x53bf0`

## string_xrefs

- `0x53c45`: `Cascade link type '{0}' is invalid for Rollup View. The referencing entity must support activities. [Relationship name '{1}'].`
- `0x53c83`: `Cascade link type '{0}' is invalid for Rollup View.Cascade Rollup View is only supported on relationships where the referenced entity is either Account, Contact or Opportunity.  [Relationship name '{1}'].`
- `0x53cc2`: `Cascade link type '{0}' is invalid for Rollup View. Support values are: Cascade, NoCascade. [Relationship name '{1}'].`

## pseudocode

```c

```

## disassembly

```asm
0x53bf0  ldarg.0
0x53bf1  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeRollupView()
0x53bf6  ldc.i4.1
0x53bf7  bne.un   loc_53CB5
0x53bfc  ldarg.0
0x53bfd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_IsCustomRelationship()
0x53c02  brtrue.s loc_53C2D
0x53c04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53c09  ldstr    aCascadeRollupV// "Cascade Rollup View is only supported o"...
0x53c0e  ldc.i4.1
0x53c0f  newarr   [mscorlib]System.Object
0x53c14  dup
0x53c15  ldc.i4.0
0x53c16  ldarg.0
0x53c17  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x53c1c  stelem.ref
0x53c1d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53c22  ldc.i4   0x80048204
0x53c27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53c2c  throw
0x53c2d  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x53c32  ldarg.2
0x53c33  ldarg.3
0x53c34  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x53c39  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::HasActivityRelationship(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x53c3e  brtrue.s loc_53C77
0x53c40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53c45  ldstr    aCascadeLinkTyp_4// "Cascade link type '{0}' is invalid for "...
0x53c4a  ldc.i4.2
0x53c4b  newarr   [mscorlib]System.Object
0x53c50  dup
0x53c51  ldc.i4.0
0x53c52  ldarg.0
0x53c53  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeRollupView()
0x53c58  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53c5d  stelem.ref
0x53c5e  dup
0x53c5f  ldc.i4.1
0x53c60  ldarg.0
0x53c61  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x53c66  stelem.ref
0x53c67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53c6c  ldc.i4   0x80048204
0x53c71  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53c76  throw
0x53c77  ldarg.1
0x53c78  ldc.i4.1
0x53c79  sub
0x53c7a  ldc.i4.2
0x53c7b  bgt.un.s loc_53C7E
0x53c7d  ret
0x53c7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53c83  ldstr    aCascadeLinkTyp_5// "Cascade link type '{0}' is invalid for "...
0x53c88  ldc.i4.2
0x53c89  newarr   [mscorlib]System.Object
0x53c8e  dup
0x53c8f  ldc.i4.0
0x53c90  ldarg.0
0x53c91  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeRollupView()
0x53c96  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53c9b  stelem.ref
0x53c9c  dup
0x53c9d  ldc.i4.1
0x53c9e  ldarg.0
0x53c9f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x53ca4  stelem.ref
0x53ca5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53caa  ldc.i4   0x80048204
0x53caf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53cb4  throw
0x53cb5  ldarg.0
0x53cb6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeRollupView()
0x53cbb  brfalse.s loc_53CF4
0x53cbd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53cc2  ldstr    aCascadeLinkTyp_6// "Cascade link type '{0}' is invalid for "...
0x53cc7  ldc.i4.2
0x53cc8  newarr   [mscorlib]System.Object
0x53ccd  dup
0x53cce  ldc.i4.0
0x53ccf  ldarg.0
0x53cd0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_CascadeRollupView()
0x53cd5  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x53cda  stelem.ref
0x53cdb  dup
0x53cdc  ldc.i4.1
0x53cdd  ldarg.0
0x53cde  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_Name()
0x53ce3  stelem.ref
0x53ce4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53ce9  ldc.i4   0x80048204
0x53cee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x53cf3  throw
0x53cf4  ret
```
