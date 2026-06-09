# Microsoft.Crm.Dependency.ComponentCollector::CreateComponentDependencies

- ea: `0x5610`
- end: `0x56e3`
- name: `Microsoft.Crm.Dependency.ComponentCollector::CreateComponentDependencies`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5180`

## callees

- `0x5610`
- `0x6d10`
- `0x7340`

## string_xrefs

- `0x5615`: `Dependency_BEGIN_{0}.CreateComponentDependencies:(all)`
- `0x5649`: `Dependency_BEGIN_{0}.CreateComponentDependencies:(componentType={1})`
- `0x5689`: `Dependency_END_{0}.CreateComponentDependencies:(componentType={1})`
- `0x56c9`: `Dependency_END_{0}.CreateComponentDependencies:(all)`

## pseudocode

```c

```

## disassembly

```asm
0x5610  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5615  ldstr    aDependencyBegi_0// "Dependency_BEGIN_{0}.CreateComponentDep"...
0x561a  ldc.i4.1
0x561b  newarr   [mscorlib]System.Object
0x5620  dup
0x5621  ldc.i4.0
0x5622  ldarg.0
0x5623  stelem.ref
0x5624  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5629  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x562e  ldarg.1
0x562f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Keys()
0x5634  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::GetEnumerator()
0x5639  stloc.0
0x563a  br.s     loc_56AB
0x563c  ldloca.s 0
0x563e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Current()
0x5643  stloc.1
0x5644  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5649  ldstr    aDependencyBegi_1// "Dependency_BEGIN_{0}.CreateComponentDep"...
0x564e  ldc.i4.2
0x564f  newarr   [mscorlib]System.Object
0x5654  dup
0x5655  ldc.i4.0
0x5656  ldarg.0
0x5657  stelem.ref
0x5658  dup
0x5659  ldc.i4.1
0x565a  ldloc.1
0x565b  box      [mscorlib]System.Int32
0x5660  stelem.ref
0x5661  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5666  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x566b  ldloc.1
0x566c  ldarg.1
0x566d  ldloc.1
0x566e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x5673  ldarg.0
0x5674  ldfld    class Microsoft.Crm.Dependency.DependencyNodeDictionary Microsoft.Crm.Dependency.ComponentCollector::_nodeCache
0x5679  call     class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper(int32 componentType, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord> records, class Microsoft.Crm.Dependency.DependencyNodeDictionary cache)
0x567e  ldarg.2
0x567f  callvirt instance void Microsoft.Crm.Dependency.IDependencyHelper::CreateDependencies(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5684  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5689  ldstr    aDependencyEnd0_0// "Dependency_END_{0}.CreateComponentDepen"...
0x568e  ldc.i4.2
0x568f  newarr   [mscorlib]System.Object
0x5694  dup
0x5695  ldc.i4.0
0x5696  ldarg.0
0x5697  stelem.ref
0x5698  dup
0x5699  ldc.i4.1
0x569a  ldloc.1
0x569b  box      [mscorlib]System.Int32
0x56a0  stelem.ref
0x56a1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x56ab  ldloca.s 0
0x56ad  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::MoveNext()
0x56b2  brtrue.s loc_563C
0x56b4  leave.s  loc_56C4
0x56b6  ldloca.s 0
0x56b8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>
0x56be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56c3  endfinally
0x56c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56c9  ldstr    aDependencyEnd0_1// "Dependency_END_{0}.CreateComponentDepen"...
0x56ce  ldc.i4.1
0x56cf  newarr   [mscorlib]System.Object
0x56d4  dup
0x56d5  ldc.i4.0
0x56d6  ldarg.0
0x56d7  stelem.ref
0x56d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x56e2  ret
```
