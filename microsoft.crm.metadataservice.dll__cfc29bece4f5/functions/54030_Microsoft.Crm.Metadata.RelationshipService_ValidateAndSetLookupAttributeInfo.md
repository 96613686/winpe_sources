# Microsoft.Crm.Metadata.RelationshipService::ValidateAndSetLookupAttributeInfo

- ea: `0x54030`
- end: `0x541e2`
- name: `Microsoft.Crm.Metadata.RelationshipService::ValidateAndSetLookupAttributeInfo`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x53ea0`

## callees

- `0x45da0`
- `0x45db0`
- `0x45dc0`
- `0x45dd0`
- `0x46500`
- `0x4cee0`
- `0x4cf00`
- `0x4d140`
- `0x4d180`
- `0x4d3c0`
- `0x4d3d0`
- `0x4d400`
- `0x4d410`
- `0x4d440`
- `0x4d450`
- `0x4d480`
- `0x4d490`
- `0x54030`
- `0x541f0`

## string_xrefs

- `0x54057`: `Lookup attribute [{0}] on Entity [{1}] for Relationship [{2}] was not created.`
- `0x540be`: `NameView attribute for lookup [{0}] on Entity [{1}] for Relationship [{2}] was not created.`
- `0x54134`: `YomiNameView attribute for lookup [{0}] on Entity [{1}] for Relationship [{2}] was not created.`
- `0x5419f`: `IdType attribute for lookup [{0}] on Entity [{1}] for Relationship [{2}] was not created.`

## pseudocode

```c

```

## disassembly

```asm
0x54030  ldarg.0
0x54031  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::get_LookupAttributeId()
0x54036  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5403b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54040  brfalse.s loc_54093
0x54042  ldarg.1
0x54043  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_LookupAttributeId()
0x54048  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5404d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54052  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54057  ldstr    aLookupAttribut// "Lookup attribute [{0}] on Entity [{1}] "...
0x5405c  ldc.i4.3
0x5405d  newarr   [mscorlib]System.Object
0x54062  dup
0x54063  ldc.i4.0
0x54064  ldarg.0
0x54065  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x5406a  stelem.ref
0x5406b  dup
0x5406c  ldc.i4.1
0x5406d  ldarg.0
0x5406e  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x54073  stelem.ref
0x54074  dup
0x54075  ldc.i4.2
0x54076  ldarg.0
0x54077  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x5407c  stelem.ref
0x5407d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54082  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x54087  ldarg.0
0x54088  ldarg.1
0x54089  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_LookupAttributeId()
0x5408e  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_LookupAttributeId(valuetype [mscorlib]System.Guid value)
0x54093  ldarg.0
0x54094  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::get_NameViewAttributeId()
0x54099  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5409e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x540a3  brfalse.s loc_540FA
0x540a5  ldarg.s  4
0x540a7  brtrue.s loc_540FA
0x540a9  ldarg.1
0x540aa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_NameViewAttributeId()
0x540af  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x540b4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x540b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x540be  ldstr    aNameviewAttrib// "NameView attribute for lookup [{0}] on "...
0x540c3  ldc.i4.3
0x540c4  newarr   [mscorlib]System.Object
0x540c9  dup
0x540ca  ldc.i4.0
0x540cb  ldarg.0
0x540cc  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x540d1  stelem.ref
0x540d2  dup
0x540d3  ldc.i4.1
0x540d4  ldarg.0
0x540d5  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x540da  stelem.ref
0x540db  dup
0x540dc  ldc.i4.2
0x540dd  ldarg.0
0x540de  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x540e3  stelem.ref
0x540e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x540e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x540ee  ldarg.0
0x540ef  ldarg.1
0x540f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_NameViewAttributeId()
0x540f5  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_NameViewAttributeId(valuetype [mscorlib]System.Guid value)
0x540fa  ldarg.0
0x540fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::get_YomiNameViewAttributeId()
0x54100  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54105  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5410a  brfalse.s loc_54170
0x5410c  ldarg.s  4
0x5410e  brtrue.s loc_54170
0x54110  ldarg.1
0x54111  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_YomiNameViewAttributeId()
0x54116  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5411b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54120  brtrue.s loc_5412E
0x54122  ldarg.2
0x54123  ldarg.3
0x54124  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.LookupAttributeHelper::GetPrimaryFieldYomiAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54129  ldnull
0x5412a  ceq
0x5412c  br.s     loc_5412F
0x5412e  ldc.i4.1
0x5412f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54134  ldstr    aYominameviewAt// "YomiNameView attribute for lookup [{0}]"...
0x54139  ldc.i4.3
0x5413a  newarr   [mscorlib]System.Object
0x5413f  dup
0x54140  ldc.i4.0
0x54141  ldarg.0
0x54142  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x54147  stelem.ref
0x54148  dup
0x54149  ldc.i4.1
0x5414a  ldarg.0
0x5414b  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x54150  stelem.ref
0x54151  dup
0x54152  ldc.i4.2
0x54153  ldarg.0
0x54154  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x54159  stelem.ref
0x5415a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5415f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x54164  ldarg.0
0x54165  ldarg.1
0x54166  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_YomiNameViewAttributeId()
0x5416b  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_YomiNameViewAttributeId(valuetype [mscorlib]System.Guid value)
0x54170  ldarg.0
0x54171  callvirt instance bool Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsPartOfPolymorphicRelationships()
0x54176  brfalse.s loc_541DB
0x54178  ldarg.0
0x54179  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IdTypeAttributeId()
0x5417e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54183  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54188  brfalse.s loc_541DB
0x5418a  ldarg.1
0x5418b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_IdTypeAttributeId()
0x54190  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54195  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5419a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5419f  ldstr    aIdtypeAttribut// "IdType attribute for lookup [{0}] on En"...
0x541a4  ldc.i4.3
0x541a5  newarr   [mscorlib]System.Object
0x541aa  dup
0x541ab  ldc.i4.0
0x541ac  ldarg.0
0x541ad  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x541b2  stelem.ref
0x541b3  dup
0x541b4  ldc.i4.1
0x541b5  ldarg.0
0x541b6  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0x541bb  stelem.ref
0x541bc  dup
0x541bd  ldc.i4.2
0x541be  ldarg.0
0x541bf  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x541c4  stelem.ref
0x541c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x541ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x541cf  ldarg.0
0x541d0  ldarg.1
0x541d1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.ILookupAttributeIdSet::get_IdTypeAttributeId()
0x541d6  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IdTypeAttributeId(valuetype [mscorlib]System.Guid value)
0x541db  ldarg.0
0x541dc  call     void Microsoft.Crm.Metadata.RelationshipService::SetLookupChildAttributeNames(class Microsoft.Crm.Metadata.RelationshipCreateInfo relationshipInfo)
0x541e1  ret
```
