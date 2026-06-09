# Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_2

- ea: `0x169a0`
- end: `0x16cf5`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_2`
- size: `853`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14370`
- `0x14380`
- `0x14390`
- `0x143a0`
- `0x143c0`
- `0x14400`
- `0x14420`
- `0x169a0`
- `0x17fb0`
- `0x184f0`
- `0x187b0`
- `0x187c0`
- `0x19850`
- `0x1a5a0`
- `0x1a8f0`
- `0x1b220`
- `0x1b290`
- `0x1e3a0`
- `0x1e3d0`
- `0x52e20`
- `0x52e60`
- `0x87370`

## string_xrefs

- `0x16a3d`: `link-entity`
- `0x16bac`: `Ambiguous reference (entityname={0}). At least one of link-entity nodes has the same entity name as the main entity`

## pseudocode

```c

```

## disassembly

```asm
0x169a0  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x169a5  stloc.0
0x169a6  ldarg.0
0x169a7  ldarg.0
0x169a8  ldfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::conditionCount
0x169ad  ldc.i4.1
0x169ae  add
0x169af  stloc.s  6
0x169b1  ldloc.s  6
0x169b3  stfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::conditionCount
0x169b8  ldloc.s  6
0x169ba  call     int32 Microsoft.Crm.Query.QueryHelper::get_MaximumConditionsAllowed()
0x169bf  ble.s    loc_169D2
0x169c1  ldc.i4   0x8004430C
0x169c6  ldc.i4.0
0x169c7  newarr   [mscorlib]System.Object
0x169cc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x169d1  throw
0x169d2  ldarg.0
0x169d3  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x169d8  stloc.1
0x169d9  ldloc.1
0x169da  ldstr    aOperator// "operator"
0x169df  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x169e4  stloc.2
0x169e5  ldarg.1
0x169e6  ldloc.2
0x169e7  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.QuerySerializationUtil::ConditionOperatorFromString(string)
0x169ec  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator value)
0x169f1  ldloc.1
0x169f2  ldstr    aAttribute_0// "attribute"
0x169f7  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x169fc  stloc.3
0x169fd  ldloc.0
0x169fe  ldloc.1
0x169ff  ldstr    aEntityname_0// "entityname"
0x16a04  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16a09  stfld    string <>c__DisplayClass5_0::referencedEntityName
0x16a0e  ldloc.0
0x16a0f  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16a14  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16a19  brtrue.s loc_16A53
0x16a1b  ldarg.0
0x16a1c  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bInLinkEntity
0x16a21  brfalse.s loc_16A53
0x16a23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16a28  ldstr    aThe0AttributeI// "The {0} attribute is not a valid attrib"...
0x16a2d  ldc.i4.2
0x16a2e  newarr   [mscorlib]System.Object
0x16a33  dup
0x16a34  ldc.i4.0
0x16a35  ldstr    aEntityname_0// "entityname"
0x16a3a  stelem.ref
0x16a3b  dup
0x16a3c  ldc.i4.1
0x16a3d  ldstr    aLinkEntity// "link-entity"
0x16a42  stelem.ref
0x16a43  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16a48  ldc.i4   0x80041108
0x16a4d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16a52  throw
0x16a53  ldarg.1
0x16a54  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Crm.Query.ConditionExpression::get_ConditionOperator()
0x16a59  ldc.i4.s 0x2D
0x16a5b  bne.un.s loc_16AA4
0x16a5d  ldloc.3
0x16a5e  ldstr    aPrimarykey// "primarykey"
0x16a63  callvirt instance bool [mscorlib]System.String::Equals(string)
0x16a68  brtrue.s loc_16A8E
0x16a6a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16a6f  ldstr    aThe0AttributeI_0// "The {0} attribute is not a valid attrib"...
0x16a74  ldc.i4.1
0x16a75  newarr   [mscorlib]System.Object
0x16a7a  dup
0x16a7b  ldc.i4.0
0x16a7c  ldloc.3
0x16a7d  stelem.ref
0x16a7e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16a83  ldc.i4   0x80041108
0x16a88  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16a8d  throw
0x16a8e  ldarg.1
0x16a8f  ldarg.0
0x16a90  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16a95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x16a9a  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x16a9f  br       loc_16C03
0x16aa4  ldloc.0
0x16aa5  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16aaa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16aaf  brtrue   loc_16B48
0x16ab4  ldloc.0
0x16ab5  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16aba  ldarg.0
0x16abb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16ac0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x16ac5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x16aca  brfalse.s loc_16B48
0x16acc  ldarg.0
0x16acd  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16ad2  ldloc.0
0x16ad3  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16ad8  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.EntityExpression::GetLinkEntity(string linkEntityName)
0x16add  stloc.s  7
0x16adf  ldloc.s  7
0x16ae1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x16ae6  ldloc.s  7
0x16ae8  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_LogicalEntityName()
0x16aed  ldc.i4.1
0x16aee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16af3  stloc.s  8
0x16af5  ldarg.1
0x16af6  ldloc.s  8
0x16af8  ldloc.3
0x16af9  ldc.i4.1
0x16afa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16aff  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x16b04  ldarg.1
0x16b05  ldarg.0
0x16b06  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::skipMissingAttributes
0x16b0b  brtrue.s loc_16B18
0x16b0d  ldloc.s  8
0x16b0f  ldloc.3
0x16b10  ldc.i4.1
0x16b11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16b16  br.s     loc_16B21
0x16b18  ldloc.s  8
0x16b1a  ldloc.3
0x16b1b  ldc.i4.1
0x16b1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16b21  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x16b26  ldarg.1
0x16b27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x16b2c  brtrue.s loc_16B2F
0x16b2e  ret
0x16b2f  ldarg.1
0x16b30  ldloc.s  7
0x16b32  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x16b37  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_TableAlias(string value)
0x16b3c  ldarg.1
0x16b3d  ldc.i4.1
0x16b3e  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_IsReferencedEntityLinkEntity(bool value)
0x16b43  br       loc_16C03
0x16b48  ldloc.0
0x16b49  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16b4e  ldarg.0
0x16b4f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16b54  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x16b59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16b5e  brfalse.s loc_16BD0
0x16b60  ldarg.0
0x16b61  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16b66  callvirt instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x16b6b  call     T0x2B00002F
0x16b70  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__5_0
0x16b75  dup
0x16b76  brtrue.s loc_16B8F
0x16b78  pop
0x16b79  ldsfld   class <>c <>c::<>9
0x16b7e  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression> <>c::<Visit>b__5_0(class Microsoft.Crm.Query.LinkEntityExpression exp)
0x16b84  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>>::.ctor(object, native int)
0x16b89  dup
0x16b8a  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__5_0
0x16b8f  call     T0x2B000030
0x16b94  ldloc.0
0x16b95  ldftn    instance bool <>c__DisplayClass5_0::<Visit>b__1(class Microsoft.Crm.Query.LinkEntityExpression entity)
0x16b9b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, bool>::.ctor(object, native int)
0x16ba0  call     T0x2B000031
0x16ba5  brfalse.s loc_16BD0
0x16ba7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bac  ldstr    aAmbiguousRefer// "Ambiguous reference (entityname={0}). A"...
0x16bb1  ldc.i4.1
0x16bb2  newarr   [mscorlib]System.Object
0x16bb7  dup
0x16bb8  ldc.i4.0
0x16bb9  ldloc.0
0x16bba  ldfld    string <>c__DisplayClass5_0::referencedEntityName
0x16bbf  stelem.ref
0x16bc0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16bc5  ldc.i4   0x80041108
0x16bca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16bcf  throw
0x16bd0  ldarg.1
0x16bd1  ldarg.0
0x16bd2  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::skipMissingAttributes
0x16bd7  brtrue.s loc_16BE8
0x16bd9  ldarg.0
0x16bda  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16bdf  ldloc.3
0x16be0  ldc.i4.1
0x16be1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16be6  br.s     loc_16BF5
0x16be8  ldarg.0
0x16be9  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16bee  ldloc.3
0x16bef  ldc.i4.1
0x16bf0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16bf5  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x16bfa  ldarg.1
0x16bfb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x16c00  brtrue.s loc_16C03
0x16c02  ret
0x16c03  ldarg.1
0x16c04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x16c09  ldarg.0
0x16c0a  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Query.DeserializeFetchVisitor::_attributesAccounted
0x16c0f  call     void Microsoft.Crm.Query.QueryHelper::ValidateMaxCalculatedFieldAllowed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> accountedAttributes)
0x16c14  ldarg.1
0x16c15  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x16c1a  call     void Microsoft.Crm.Query.ExpressionVisitor::ValidateMetaDataAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x16c1f  ldarg.0
0x16c20  ldfld    valuetype Microsoft.Crm.Query.ParsingConditionValuesOption Microsoft.Crm.Query.DeserializeFetchVisitor::parsingConditionValuesOption
0x16c25  ldc.i4.0
0x16c26  ceq
0x16c28  ldarg.0
0x16c29  ldfld    valuetype Microsoft.Crm.Query.ParsingConditionValuesOption Microsoft.Crm.Query.DeserializeFetchVisitor::parsingConditionValuesOption
0x16c2e  ldc.i4.1
0x16c2f  beq.s    loc_16C3A
0x16c31  ldarg.0
0x16c32  ldfld    valuetype Microsoft.Crm.Query.ParsingConditionValuesOption Microsoft.Crm.Query.DeserializeFetchVisitor::parsingConditionValuesOption
0x16c37  ldc.i4.2
0x16c38  bne.un.s loc_16C4D
0x16c3a  ldarg.0
0x16c3b  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16c40  brtrue.s loc_16C4D
0x16c42  ldarg.0
0x16c43  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::_isReportContext
0x16c48  ldc.i4.0
0x16c49  ceq
0x16c4b  br.s     loc_16C4E
0x16c4d  ldc.i4.0
0x16c4e  stloc.s  4
0x16c50  ldloc.1
0x16c51  ldstr    aValue_0// "value"
0x16c56  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16c5b  stloc.s  5
0x16c5d  ldloc.s  4
0x16c5f  or
0x16c60  brfalse.s loc_16C6D
0x16c62  ldloc.1
0x16c63  ldarg.1
0x16c64  ldloc.s  4
0x16c66  call     void Microsoft.Crm.Query.SerializableHelper::ConditionOperatorReader(class [System.Xml.Linq]System.Xml.Linq.XElement node, class Microsoft.Crm.Query.ConditionExpression condition, bool ignoreInvalidConditionValues)
0x16c6b  br.s     loc_16C90
0x16c6d  ldarg.0
0x16c6e  ldfld    valuetype Microsoft.Crm.Query.ParsingConditionValuesOption Microsoft.Crm.Query.DeserializeFetchVisitor::parsingConditionValuesOption
0x16c73  ldc.i4.2
0x16c74  bne.un.s loc_16C90
0x16c76  ldarg.0
0x16c77  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16c7c  brfalse.s loc_16C90
0x16c7e  ldloc.s  5
0x16c80  brfalse.s loc_16C90
0x16c82  ldarg.1
0x16c83  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Query.ConditionExpression::get_Values()
0x16c88  ldloc.s  5
0x16c8a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x16c8f  pop
0x16c90  ldarg.0
0x16c91  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16c96  ldarg.0
0x16c97  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16c9c  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_IsLeadingWildCardQuery()
0x16ca1  ldc.i4.0
0x16ca2  ceq
0x16ca4  and
0x16ca5  brfalse.s loc_16CC2
0x16ca7  ldloc.s  5
0x16ca9  brfalse.s loc_16CC2
0x16cab  ldloc.s  5
0x16cad  ldc.i4.s 0x25
0x16caf  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x16cb4  brtrue.s loc_16CC2
0x16cb6  ldarg.0
0x16cb7  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16cbc  ldc.i4.1
0x16cbd  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_IsLeadingWildCardQuery(bool value)
0x16cc2  ldarg.0
0x16cc3  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16cc8  ldarg.0
0x16cc9  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16cce  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_IsLeadingWildCardQuery()
0x16cd3  ldc.i4.0
0x16cd4  ceq
0x16cd6  and
0x16cd7  brfalse.s loc_16CF4
0x16cd9  ldloc.s  5
0x16cdb  brfalse.s loc_16CF4
0x16cdd  ldloc.s  5
0x16cdf  ldc.i4.s 0x25
0x16ce1  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x16ce6  brtrue.s loc_16CF4
0x16ce8  ldarg.0
0x16ce9  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16cee  ldc.i4.1
0x16cef  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_IsLeadingWildCardQuery(bool value)
0x16cf4  ret
```
