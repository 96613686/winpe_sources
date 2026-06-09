# ExtensionTableConditionAggregator::GetSql

- ea: `0x92680`
- end: `0x929c6`
- name: `ExtensionTableConditionAggregator::GetSql`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x90f40`
- `0x90fc0`
- `0x911e0`
- `0x91220`
- `0x91280`
- `0x913a0`
- `0x92680`

## string_xrefs

- `0x927d9`: `FTSExtension0`
- `0x928cc`: `FTSExtension0`

## pseudocode

```c

```

## disassembly

```asm
0x92680  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x92685  stloc.0
0x92686  ldarg.0
0x92687  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>> QuickFindConditionAggregator::_nonFtsConditionsByAttributeTarget
0x9268c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::GetEnumerator()
0x92691  stloc.1
0x92692  br.s     loc_926A9
0x92694  ldloca.s 1
0x92696  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Current()
0x9269b  stloc.2
0x9269c  ldloc.0
0x9269d  ldarg.0
0x9269e  ldloc.2
0x9269f  call     instance string QuickFindConditionAggregator::GetPrimaryConditionSql(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>> conditionsByTarget)
0x926a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x926a9  ldloca.s 1
0x926ab  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::MoveNext()
0x926b0  brtrue.s loc_92694
0x926b2  leave.s  loc_926C2
0x926b4  ldloca.s 1
0x926b6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>
0x926bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x926c1  endfinally
0x926c2  ldarg.0
0x926c3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>> QuickFindConditionAggregator::_ftsConditionsByAttributeTarget
0x926c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::GetEnumerator()
0x926cd  stloc.1
0x926ce  br       loc_929A8
0x926d3  ldloca.s 1
0x926d5  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Current()
0x926da  stloc.3
0x926db  ldstr    asc_CC16C// ", "
0x926e0  ldloca.s 3
0x926e2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Value()
0x926e7  ldarg.0
0x926e8  ldftn    instance bool ExtensionTableConditionAggregator::<GetSql>b__2_0(class QuickFindConditionData x)
0x926ee  newobj   instance void class [mscorlib]System.Func`2<class QuickFindConditionData, bool>::.ctor(object, native int)
0x926f3  call     T0x2B0000D5
0x926f8  ldsfld   class [mscorlib]System.Func`2<class QuickFindConditionData, string> <>c::<>9__2_1
0x926fd  dup
0x926fe  brtrue.s loc_92717
0x92700  pop
0x92701  ldsfld   class <>c <>c::<>9
0x92706  ldftn    instance string <>c::<GetSql>b__2_1(class QuickFindConditionData x)
0x9270c  newobj   instance void class [mscorlib]System.Func`2<class QuickFindConditionData, string>::.ctor(object, native int)
0x92711  dup
0x92712  stsfld   class [mscorlib]System.Func`2<class QuickFindConditionData, string> <>c::<>9__2_1
0x92717  call     T0x2B0000D6
0x9271c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x92721  stloc.s  4
0x92723  ldloc.s  4
0x92725  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9272a  brtrue   loc_927F9
0x9272f  ldloca.s 3
0x92731  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Value()
0x92736  call     T0x2B0000D7
0x9273b  stloc.s  5
0x9273d  ldloc.s  5
0x9273f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata QuickFindConditionData::get_Attribute()
0x92744  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x92749  stloc.s  6
0x9274b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92750  call     string [mscorlib]System.Environment::get_NewLine()
0x92755  ldstr    aSelect27As0Fro// "SELECT \"{2}\".[{7}] AS [{0}] FROM [{1}"...
0x9275a  call     string [mscorlib]System.String::Concat(string, string)
0x9275f  ldc.i4.s 0xA
0x92761  newarr   [mscorlib]System.Object
0x92766  dup
0x92767  ldc.i4.0
0x92768  ldarg.0
0x92769  ldfld    class QuickFindConditionBuilder QuickFindConditionAggregator::_builder
0x9276e  ldfld    string QuickFindConditionBuilder::_keyColumnName
0x92773  stelem.ref
0x92774  dup
0x92775  ldc.i4.1
0x92776  ldarg.0
0x92777  ldfld    class QuickFindConditionBuilder QuickFindConditionAggregator::_builder
0x9277c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata QuickFindConditionBuilder::_entityMetadata
0x92781  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x92786  stelem.ref
0x92787  dup
0x92788  ldc.i4.2
0x92789  ldarg.0
0x9278a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> QuickFindConditionAggregator::_queryTargetNameToQueryTargetAlias
0x9278f  ldloca.s 3
0x92791  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Key()
0x92796  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9279b  stelem.ref
0x9279c  dup
0x9279d  ldc.i4.3
0x9279e  ldstr    aContainstable// "ContainsTable"
0x927a3  stelem.ref
0x927a4  dup
0x927a5  ldc.i4.4
0x927a6  ldloc.s  4
0x927a8  stelem.ref
0x927a9  dup
0x927aa  ldc.i4.5
0x927ab  ldarg.0
0x927ac  ldloc.s  5
0x927ae  callvirt instance string QuickFindConditionData::get_Condition()
0x927b3  call     instance string QuickFindConditionAggregator::GetSearchStringFromQuickFindTextCondition(string condition)
0x927b8  stelem.ref
0x927b9  dup
0x927ba  ldc.i4.6
0x927bb  ldloc.s  6
0x927bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x927c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x927c7  stelem.ref
0x927c8  dup
0x927c9  ldc.i4.7
0x927ca  ldloc.s  6
0x927cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x927d1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x927d6  stelem.ref
0x927d7  dup
0x927d8  ldc.i4.8
0x927d9  ldstr    aFtsextension0// "FTSExtension0"
0x927de  stelem.ref
0x927df  dup
0x927e0  ldc.i4.s 9
0x927e2  ldloca.s 3
0x927e4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Key()
0x927e9  stelem.ref
0x927ea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x927ef  stloc.s  7
0x927f1  ldloc.0
0x927f2  ldloc.s  7
0x927f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x927f9  ldloca.s 3
0x927fb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Value()
0x92800  ldarg.0
0x92801  ldftn    instance bool ExtensionTableConditionAggregator::<GetSql>b__2_2(class QuickFindConditionData x)
0x92807  newobj   instance void class [mscorlib]System.Func`2<class QuickFindConditionData, bool>::.ctor(object, native int)
0x9280c  call     T0x2B0000D5
0x92811  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class QuickFindConditionData>::GetEnumerator()
0x92816  stloc.s  8
0x92818  br       loc_9298E
0x9281d  ldloc.s  8
0x9281f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class QuickFindConditionData>::get_Current()
0x92824  stloc.s  9
0x92826  ldloc.s  9
0x92828  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata QuickFindConditionData::get_Attribute()
0x9282d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x92832  stloc.s  0xA
0x92834  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92839  call     string [mscorlib]System.Environment::get_NewLine()
0x9283e  ldstr    aSelect27As0Fro// "SELECT \"{2}\".[{7}] AS [{0}] FROM [{1}"...
0x92843  call     string [mscorlib]System.String::Concat(string, string)
0x92848  ldc.i4.s 0xA
0x9284a  newarr   [mscorlib]System.Object
0x9284f  dup
0x92850  ldc.i4.0
0x92851  ldarg.0
0x92852  ldfld    class QuickFindConditionBuilder QuickFindConditionAggregator::_builder
0x92857  ldfld    string QuickFindConditionBuilder::_keyColumnName
0x9285c  stelem.ref
0x9285d  dup
0x9285e  ldc.i4.1
0x9285f  ldarg.0
0x92860  ldfld    class QuickFindConditionBuilder QuickFindConditionAggregator::_builder
0x92865  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata QuickFindConditionBuilder::_entityMetadata
0x9286a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x9286f  stelem.ref
0x92870  dup
0x92871  ldc.i4.2
0x92872  ldarg.0
0x92873  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> QuickFindConditionAggregator::_queryTargetNameToQueryTargetAlias
0x92878  ldloca.s 3
0x9287a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Key()
0x9287f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x92884  stelem.ref
0x92885  dup
0x92886  ldc.i4.3
0x92887  ldstr    aContainstable// "ContainsTable"
0x9288c  stelem.ref
0x9288d  dup
0x9288e  ldc.i4.4
0x9288f  ldloc.s  9
0x92891  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata QuickFindConditionData::get_Attribute()
0x92896  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x9289b  stelem.ref
0x9289c  dup
0x9289d  ldc.i4.5
0x9289e  ldarg.0
0x9289f  ldloc.s  9
0x928a1  callvirt instance string QuickFindConditionData::get_Condition()
0x928a6  call     instance string QuickFindConditionAggregator::GetSearchStringFromQuickFindTextCondition(string condition)
0x928ab  stelem.ref
0x928ac  dup
0x928ad  ldc.i4.6
0x928ae  ldloc.s  0xA
0x928b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x928b5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x928ba  stelem.ref
0x928bb  dup
0x928bc  ldc.i4.7
0x928bd  ldloc.s  0xA
0x928bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x928c4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x928c9  stelem.ref
0x928ca  dup
0x928cb  ldc.i4.8
0x928cc  ldstr    aFtsextension0// "FTSExtension0"
0x928d1  stelem.ref
0x928d2  dup
0x928d3  ldc.i4.s 9
0x928d5  ldloca.s 3
0x928d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::get_Key()
0x928dc  stelem.ref
0x928dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x928e2  stloc.s  0xB
0x928e4  ldloc.s  0xB
0x928e6  ldarg.0
0x928e7  ldloc.s  9
0x928e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata QuickFindConditionData::get_Attribute()
0x928ee  call     instance string QuickFindConditionAggregator::GetModifiedFlsConditionJoinsForFts(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x928f3  call     string [mscorlib]System.String::Concat(string, string)
0x928f8  stloc.s  0xB
0x928fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x928ff  ldstr    aWhere0_1// " where ({0})"
0x92904  ldc.i4.1
0x92905  newarr   [mscorlib]System.Object
0x9290a  dup
0x9290b  ldc.i4.0
0x9290c  ldarg.0
0x9290d  ldloc.s  9
0x9290f  call     instance string QuickFindConditionAggregator::GetFlsConditionsForFts(class QuickFindConditionData conditionData)
0x92914  stelem.ref
0x92915  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9291a  stloc.s  0xC
0x9291c  ldloc.s  0xA
0x9291e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_InheritanceTypeAttribute()
0x92923  brfalse.s loc_9297F
0x92925  ldloc.s  0xC
0x92927  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9292c  brtrue.s loc_9293C
0x9292e  ldloc.s  0xC
0x92930  ldstr    aAnd_2// " and "
0x92935  call     string [mscorlib]System.String::Concat(string, string)
0x9293a  br.s     loc_92941
0x9293c  ldstr    aWhere// " where "
0x92941  stloc.s  0xC
0x92943  ldloc.s  0xC
0x92945  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9294a  ldstr    a01_24// "({0} = {1})"
0x9294f  ldc.i4.2
0x92950  newarr   [mscorlib]System.Object
0x92955  dup
0x92956  ldc.i4.0
0x92957  ldloc.s  0xA
0x92959  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_InheritanceTypeAttribute()
0x9295e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x92963  stelem.ref
0x92964  dup
0x92965  ldc.i4.1
0x92966  ldloc.s  0xA
0x92968  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9296d  box      [mscorlib]System.Int32
0x92972  stelem.ref
0x92973  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x92978  call     string [mscorlib]System.String::Concat(string, string)
0x9297d  stloc.s  0xC
0x9297f  ldloc.0
0x92980  ldloc.s  0xB
0x92982  ldloc.s  0xC
0x92984  call     string [mscorlib]System.String::Concat(string, string)
0x92989  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9298e  ldloc.s  8
0x92990  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x92995  brtrue   loc_9281D
0x9299a  leave.s  loc_929A8
0x9299c  ldloc.s  8
0x9299e  brfalse.s loc_929A7
0x929a0  ldloc.s  8
0x929a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x929a7  endfinally
0x929a8  ldloca.s 1
0x929aa  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>::MoveNext()
0x929af  brtrue   loc_926D3
0x929b4  leave.s  loc_929C4
0x929b6  ldloca.s 1
0x929b8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<class QuickFindConditionData>>
0x929be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x929c3  endfinally
0x929c4  ldloc.0
0x929c5  ret
```
