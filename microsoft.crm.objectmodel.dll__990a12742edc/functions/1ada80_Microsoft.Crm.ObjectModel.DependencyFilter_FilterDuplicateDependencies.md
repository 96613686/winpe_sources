# Microsoft.Crm.ObjectModel.DependencyFilter::FilterDuplicateDependencies

- ea: `0x1ada80`
- end: `0x1adc9f`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::FilterDuplicateDependencies`
- size: `543`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x19a4d0`
- `0x1af4c0`

## callees

- `0x1ada80`
- `0x1b1010`
- `0x1b1050`
- `0x1b1070`

## string_xrefs

- `0x1adaed`: `requiredcomponentobjectid`
- `0x1adadb`: `requiredcomponenttype`
- `0x1adb00`: `dependentcomponentobjectid`
- `0x1adb10`: `dependentcomponenttype`
- `0x1adbe2`: `SolutionComponent`
- `0x1adbf1`: `SolutionComponent`
- `0x1adc7e`: `Only SolutionComponent or Dependency entities can be filtered, not {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1ada80  ldarg.1
0x1ada81  ldstr    aOriginal// "original"
0x1ada86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ada8b  ldarg.2
0x1ada8c  ldstr    aContext// "context"
0x1ada91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ada96  ldarg.1
0x1ada97  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x1ada9c  ldstr    aDependency_0// "Dependency"
0x1adaa1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1adaa6  brfalse  loc_1ADBDC
0x1adaab  ldstr    aDependency_0// "Dependency"
0x1adab0  ldarg.2
0x1adab1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1adab6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1adabb  stloc.0
0x1adabc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::.ctor()
0x1adac1  stloc.1
0x1adac2  ldarg.1
0x1adac3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1adac8  stloc.2
0x1adac9  br       loc_1ADBB8
0x1adace  ldloc.2
0x1adacf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1adad4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1adad9  stloc.3
0x1adada  ldloc.3
0x1adadb  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1adae0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adae5  unbox.any [mscorlib]System.Int32
0x1adaea  stloc.s  4
0x1adaec  ldloc.3
0x1adaed  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1adaf2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adaf7  unbox.any [mscorlib]System.Guid
0x1adafc  stloc.s  5
0x1adafe  ldarg.0
0x1adaff  ldloc.3
0x1adb00  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1adb05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adb0a  unbox.any [mscorlib]System.Guid
0x1adb0f  ldloc.3
0x1adb10  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1adb15  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adb1a  unbox.any [mscorlib]System.Int32
0x1adb1f  call     instance string Microsoft.Crm.ObjectModel.DependencyFilter::CreateKey(valuetype [mscorlib]System.Guid objectId, int32 componentType)
0x1adb24  stloc.s  6
0x1adb26  ldloc.1
0x1adb27  ldloc.s  4
0x1adb29  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::ContainsKey(var<u1>)
0x1adb2e  brtrue.s loc_1ADB3D
0x1adb30  ldloc.1
0x1adb31  ldloc.s  4
0x1adb33  newobj   instance void Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap::.ctor()
0x1adb38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::Add(var<u1>, !!T0)
0x1adb3d  ldloc.1
0x1adb3e  ldloc.s  4
0x1adb40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::get_Item(void)
0x1adb45  ldloc.s  5
0x1adb47  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ObjectModel.StringKeyCollection>::ContainsKey(var<u1>)
0x1adb4c  brtrue.s loc_1ADB82
0x1adb4e  ldloc.0
0x1adb4f  ldloc.3
0x1adb50  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1adb55  pop
0x1adb56  ldloc.1
0x1adb57  ldloc.s  4
0x1adb59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::get_Item(void)
0x1adb5e  ldloc.s  5
0x1adb60  newobj   instance void Microsoft.Crm.ObjectModel.StringKeyCollection::.ctor()
0x1adb65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ObjectModel.StringKeyCollection>::Add(var<u1>, !!T0)
0x1adb6a  ldloc.1
0x1adb6b  ldloc.s  4
0x1adb6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::get_Item(void)
0x1adb72  ldloc.s  5
0x1adb74  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ObjectModel.StringKeyCollection>::get_Item(void)
0x1adb79  ldloc.s  6
0x1adb7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1adb80  br.s     loc_1ADBB8
0x1adb82  ldloc.1
0x1adb83  ldloc.s  4
0x1adb85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::get_Item(void)
0x1adb8a  ldloc.s  5
0x1adb8c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ObjectModel.StringKeyCollection>::get_Item(void)
0x1adb91  ldloc.s  6
0x1adb93  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1adb98  brtrue.s loc_1ADBB8
0x1adb9a  ldloc.0
0x1adb9b  ldloc.3
0x1adb9c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1adba1  pop
0x1adba2  ldloc.1
0x1adba3  ldloc.s  4
0x1adba5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.ObjectModel.GuidToStringKeyCollectionMap>::get_Item(void)
0x1adbaa  ldloc.s  5
0x1adbac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ObjectModel.StringKeyCollection>::get_Item(void)
0x1adbb1  ldloc.s  6
0x1adbb3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1adbb8  ldloc.2
0x1adbb9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1adbbe  brtrue   loc_1ADACE
0x1adbc3  leave    loc_1ADC9D
0x1adbc8  ldloc.2
0x1adbc9  isinst   [mscorlib]System.IDisposable
0x1adbce  stloc.s  7
0x1adbd0  ldloc.s  7
0x1adbd2  brfalse.s loc_1ADBDB
0x1adbd4  ldloc.s  7
0x1adbd6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1adbdb  endfinally
0x1adbdc  ldarg.1
0x1adbdd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x1adbe2  ldstr    aSolutioncompon// "SolutionComponent"
0x1adbe7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1adbec  brfalse  loc_1ADC79
0x1adbf1  ldstr    aSolutioncompon// "SolutionComponent"
0x1adbf6  ldarg.2
0x1adbf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1adbfc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1adc01  stloc.0
0x1adc02  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x1adc07  stloc.s  8
0x1adc09  ldarg.1
0x1adc0a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1adc0f  stloc.2
0x1adc10  br.s     loc_1ADC5B
0x1adc12  ldloc.2
0x1adc13  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1adc18  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1adc1d  stloc.s  9
0x1adc1f  ldloc.s  8
0x1adc21  ldloc.s  9
0x1adc23  ldstr    aObjectid// "objectid"
0x1adc28  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adc2d  unbox.any [mscorlib]System.Guid
0x1adc32  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x1adc37  brtrue.s loc_1ADC5B
0x1adc39  ldloc.0
0x1adc3a  ldloc.s  9
0x1adc3c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1adc41  pop
0x1adc42  ldloc.s  8
0x1adc44  ldloc.s  9
0x1adc46  ldstr    aObjectid// "objectid"
0x1adc4b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adc50  unbox.any [mscorlib]System.Guid
0x1adc55  ldc.i4.1
0x1adc56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0x1adc5b  ldloc.2
0x1adc5c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1adc61  brtrue.s loc_1ADC12
0x1adc63  leave.s  loc_1ADC9D
0x1adc65  ldloc.2
0x1adc66  isinst   [mscorlib]System.IDisposable
0x1adc6b  stloc.s  7
0x1adc6d  ldloc.s  7
0x1adc6f  brfalse.s loc_1ADC78
0x1adc71  ldloc.s  7
0x1adc73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1adc78  endfinally
0x1adc79  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1adc7e  ldstr    aOnlySolutionco// "Only SolutionComponent or Dependency en"...
0x1adc83  ldc.i4.1
0x1adc84  newarr   [mscorlib]System.Object
0x1adc89  dup
0x1adc8a  ldc.i4.0
0x1adc8b  ldarg.1
0x1adc8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x1adc91  stelem.ref
0x1adc92  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1adc97  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1adc9c  throw
0x1adc9d  ldloc.0
0x1adc9e  ret
```
