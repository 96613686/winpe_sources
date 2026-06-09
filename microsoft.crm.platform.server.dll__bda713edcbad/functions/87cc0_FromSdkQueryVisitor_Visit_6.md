# FromSdkQueryVisitor::Visit_6

- ea: `0x87cc0`
- end: `0x87ec6`
- name: `FromSdkQueryVisitor::Visit_6`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x14400`
- `0x14610`
- `0x184f0`
- `0x19850`
- `0x19e50`
- `0x1a5a0`
- `0x1a8f0`
- `0x1a930`
- `0x1b220`
- `0x1b290`
- `0x1e3a0`
- `0x87cc0`
- `0x90e20`

## string_xrefs

- `0x87d38`: `EntityName ({0}) is not valid for conditions on LinkEntity`
- `0x87e10`: `Ambiguous reference (EntityName={0}). At least of on LinkEntity expressions has the same entity name as the main entity`

## pseudocode

```c

```

## disassembly

```asm
0x87cc0  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x87cc5  stloc.0
0x87cc6  ldloc.0
0x87cc7  ldarg.1
0x87cc8  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87ccd  ldarg.0
0x87cce  ldarg.0
0x87ccf  ldfld    int32 FromSdkQueryVisitor::_conditionCount
0x87cd4  ldc.i4.1
0x87cd5  add
0x87cd6  stloc.s  4
0x87cd8  ldloc.s  4
0x87cda  stfld    int32 FromSdkQueryVisitor::_conditionCount
0x87cdf  ldloc.s  4
0x87ce1  call     int32 Microsoft.Crm.Query.QueryHelper::get_MaximumConditionsAllowed()
0x87ce6  ble.s    loc_87CF9
0x87ce8  ldc.i4   0x8004430C
0x87ced  ldc.i4.0
0x87cee  newarr   [mscorlib]System.Object
0x87cf3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x87cf8  throw
0x87cf9  ldnull
0x87cfa  stloc.2
0x87cfb  ldloc.0
0x87cfc  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87d01  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87d06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x87d0b  brtrue   loc_87DAC
0x87d10  ldloc.0
0x87d11  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87d16  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87d1b  ldarg.0
0x87d1c  ldfld    string FromSdkQueryVisitor::_currentEntityName
0x87d21  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x87d26  brfalse  loc_87DAC
0x87d2b  ldarg.0
0x87d2c  ldfld    bool FromSdkQueryVisitor::_inLinkEntity
0x87d31  brfalse.s loc_87D61
0x87d33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87d38  ldstr    aEntityname0IsN// "EntityName ({0}) is not valid for condi"...
0x87d3d  ldc.i4.1
0x87d3e  newarr   [mscorlib]System.Object
0x87d43  dup
0x87d44  ldc.i4.0
0x87d45  ldloc.0
0x87d46  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87d4b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87d50  stelem.ref
0x87d51  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87d56  ldc.i4   0x80041108
0x87d5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x87d60  throw
0x87d61  ldarg.0
0x87d62  ldfld    class Microsoft.Crm.Query.EntityExpression FromSdkQueryVisitor::_entityExpression
0x87d67  ldloc.0
0x87d68  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87d6d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87d72  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.EntityExpression::GetLinkEntity(string linkEntityName)
0x87d77  stloc.s  5
0x87d79  ldloc.s  5
0x87d7b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x87d80  ldloc.s  5
0x87d82  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_LogicalEntityName()
0x87d87  ldc.i4.1
0x87d88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x87d8d  ldloc.0
0x87d8e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87d93  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_AttributeName()
0x87d98  ldc.i4.1
0x87d99  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x87d9e  stloc.1
0x87d9f  ldloc.s  5
0x87da1  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x87da6  stloc.2
0x87da7  br       loc_87E5D
0x87dac  ldloc.0
0x87dad  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87db2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87db7  ldarg.0
0x87db8  ldfld    string FromSdkQueryVisitor::_currentEntityName
0x87dbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87dc2  brfalse.s loc_87E39
0x87dc4  ldarg.0
0x87dc5  ldfld    class Microsoft.Crm.Query.EntityExpression FromSdkQueryVisitor::_entityExpression
0x87dca  callvirt instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x87dcf  call     T0x2B00002F
0x87dd4  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__8_0
0x87dd9  dup
0x87dda  brtrue.s loc_87DF3
0x87ddc  pop
0x87ddd  ldsfld   class <>c <>c::<>9
0x87de2  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression> <>c::<Visit>b__8_0(class Microsoft.Crm.Query.LinkEntityExpression exp)
0x87de8  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>>::.ctor(object, native int)
0x87ded  dup
0x87dee  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Query.LinkEntityExpression>> <>c::<>9__8_0
0x87df3  call     T0x2B000030
0x87df8  ldloc.0
0x87df9  ldftn    instance bool <>c__DisplayClass8_0::<Visit>b__1(class Microsoft.Crm.Query.LinkEntityExpression entity)
0x87dff  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.LinkEntityExpression, bool>::.ctor(object, native int)
0x87e04  call     T0x2B000031
0x87e09  brfalse.s loc_87E39
0x87e0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87e10  ldstr    aAmbiguousRefer_0// "Ambiguous reference (EntityName={0}). A"...
0x87e15  ldc.i4.1
0x87e16  newarr   [mscorlib]System.Object
0x87e1b  dup
0x87e1c  ldc.i4.0
0x87e1d  ldloc.0
0x87e1e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87e23  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_EntityName()
0x87e28  stelem.ref
0x87e29  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87e2e  ldc.i4   0x80041108
0x87e33  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x87e38  throw
0x87e39  ldarg.0
0x87e3a  ldfld    class Microsoft.Crm.Query.EntityExpression FromSdkQueryVisitor::_entityExpression
0x87e3f  ldarg.0
0x87e40  ldfld    string FromSdkQueryVisitor::_currentEntityName
0x87e45  ldc.i4.1
0x87e46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::GetEntity(string entityPlatformName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType nameMappingType)
0x87e4b  ldloc.0
0x87e4c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87e51  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_AttributeName()
0x87e56  ldc.i4.1
0x87e57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x87e5c  stloc.1
0x87e5d  ldnull
0x87e5e  stloc.3
0x87e5f  ldloc.0
0x87e60  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87e65  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x87e6a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Count()
0x87e6f  ldc.i4.0
0x87e70  ble.s    loc_87E88
0x87e72  ldloc.0
0x87e73  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87e78  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x87e7d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x87e82  call     instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x87e87  stloc.3
0x87e88  ldarg.0
0x87e89  ldloc.1
0x87e8a  ldloc.0
0x87e8b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression <>c__DisplayClass8_0::condition
0x87e90  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0x87e95  ldloc.3
0x87e96  ldarg.0
0x87e97  ldfld    class Microsoft.Crm.Query.EntityExpression FromSdkQueryVisitor::_entityExpression
0x87e9c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x87ea1  newobj   instance void Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, class [mscorlib]System.Array values, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x87ea6  stfld    class Microsoft.Crm.Query.ConditionExpression FromSdkQueryVisitor::_resultCondition
0x87eab  ldloc.2
0x87eac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x87eb1  brtrue.s loc_87EBF
0x87eb3  ldarg.0
0x87eb4  ldfld    class Microsoft.Crm.Query.ConditionExpression FromSdkQueryVisitor::_resultCondition
0x87eb9  ldloc.2
0x87eba  callvirt instance void Microsoft.Crm.Query.ConditionExpression::set_TableAlias(string value)
0x87ebf  ldloc.1
0x87ec0  call     void Microsoft.Crm.Query.ExpressionVisitor::ValidateMetaDataAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x87ec5  ret
```
