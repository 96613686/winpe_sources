# <>c::<GetFeatureControlDefinition>b__3_0

- ea: `0x678f0`
- end: `0x67a0d`
- name: `<>c::<GetFeatureControlDefinition>b__3_0`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x444f0`
- `0x67720`
- `0x67740`
- `0x67760`
- `0x67780`
- `0x677a0`
- `0x677c0`
- `0x677e0`
- `0x677f0`
- `0x678f0`

## string_xrefs

- `0x679d1`: `ConfigSku`
- `0x679f8`: `ParentFeatureName`

## pseudocode

```c

```

## disassembly

```asm
0x678f0  newobj   instance void FeatureControlDefinitionInfo::.ctor()
0x678f5  dup
0x678f6  ldarga.s 1
0x678f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x678fd  ldstr    aName// "Name"
0x67902  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x67907  castclass [mscorlib]System.String
0x6790c  callvirt instance void FeatureControlDefinitionInfo::set_Name(string value)
0x67911  dup
0x67912  ldarga.s 1
0x67914  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x67919  ldstr    aEnabled// "Enabled"
0x6791e  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x67923  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x67928  stloc.0
0x67929  ldloca.s 0
0x6792b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x67930  brtrue.s loc_67935
0x67932  ldc.i4.0
0x67933  br.s     loc_6793C
0x67935  ldloca.s 0
0x67937  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x6793c  callvirt instance void FeatureControlDefinitionInfo::set_Enabled(bool value)
0x67941  dup
0x67942  ldarga.s 1
0x67944  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x67949  ldstr    aId// "Id"
0x6794e  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x67953  unbox.any [mscorlib]System.Guid
0x67958  callvirt instance void FeatureControlDefinitionInfo::set_Id(valuetype [mscorlib]System.Guid value)
0x6795d  dup
0x6795e  ldtoken  Microsoft.Crm.FeatureLocation
0x67963  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67968  ldarga.s 1
0x6796a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x6796f  ldstr    aFeaturelocatio// "FeatureLocation"
0x67974  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x67979  castclass [mscorlib]System.String
0x6797e  ldc.i4.1
0x6797f  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x67984  unbox.any Microsoft.Crm.FeatureLocation
0x67989  callvirt instance void FeatureControlDefinitionInfo::set_FeatureLocation(valuetype Microsoft.Crm.FeatureLocation value)
0x6798e  dup
0x6798f  ldtoken  Microsoft.Crm.FeatureType
0x67994  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67999  ldarga.s 1
0x6799b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x679a0  ldstr    aFeaturetype// "FeatureType"
0x679a5  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x679aa  castclass [mscorlib]System.String
0x679af  ldc.i4.1
0x679b0  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x679b5  unbox.any Microsoft.Crm.FeatureType
0x679ba  callvirt instance void FeatureControlDefinitionInfo::set_FeatureType(valuetype Microsoft.Crm.FeatureType value)
0x679bf  dup
0x679c0  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSku
0x679c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x679ca  ldarga.s 1
0x679cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x679d1  ldstr    aConfigsku// "ConfigSku"
0x679d6  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x679db  castclass [mscorlib]System.String
0x679e0  ldc.i4.1
0x679e1  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x679e6  unbox.any Microsoft.Crm.SharedDatabase.ConfigSku
0x679eb  callvirt instance void FeatureControlDefinitionInfo::set_ConfigSku(valuetype Microsoft.Crm.SharedDatabase.ConfigSku value)
0x679f0  dup
0x679f1  ldarga.s 1
0x679f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x679f8  ldstr    aParentfeaturen// "ParentFeatureName"
0x679fd  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x67a02  castclass [mscorlib]System.String
0x67a07  callvirt instance void FeatureControlDefinitionInfo::set_ParentFeatureName(string value)
0x67a0c  ret
```
