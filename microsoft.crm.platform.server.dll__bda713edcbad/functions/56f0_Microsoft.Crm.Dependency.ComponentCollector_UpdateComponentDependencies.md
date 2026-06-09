# Microsoft.Crm.Dependency.ComponentCollector::UpdateComponentDependencies

- ea: `0x56f0`
- end: `0x57c3`
- name: `Microsoft.Crm.Dependency.ComponentCollector::UpdateComponentDependencies`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5180`

## callees

- `0x56f0`
- `0x6d10`
- `0x7350`

## string_xrefs

- `0x56f5`: `Dependency_BEGIN_{0}.UpdateComponentDependencies:(all)`
- `0x5729`: `Dependency_BEGIN_{0}.UpdateComponentDependencies:(componentType={1})`
- `0x5769`: `Dependency_BEGIN_{0}.UpdateComponentDependencies:(componentType={1})`
- `0x57a9`: `Dependency_END_{0}.UpdateComponentDependencies:(all)`

## pseudocode

```c

```

## disassembly

```asm
0x56f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56f5  ldstr    aDependencyBegi_2// "Dependency_BEGIN_{0}.UpdateComponentDep"...
0x56fa  ldc.i4.1
0x56fb  newarr   [mscorlib]System.Object
0x5700  dup
0x5701  ldc.i4.0
0x5702  ldarg.0
0x5703  stelem.ref
0x5704  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5709  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x570e  ldarg.1
0x570f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Keys()
0x5714  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::GetEnumerator()
0x5719  stloc.0
0x571a  br.s     loc_578B
0x571c  ldloca.s 0
0x571e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Current()
0x5723  stloc.1
0x5724  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5729  ldstr    aDependencyBegi_3// "Dependency_BEGIN_{0}.UpdateComponentDep"...
0x572e  ldc.i4.2
0x572f  newarr   [mscorlib]System.Object
0x5734  dup
0x5735  ldc.i4.0
0x5736  ldarg.0
0x5737  stelem.ref
0x5738  dup
0x5739  ldc.i4.1
0x573a  ldloc.1
0x573b  box      [mscorlib]System.Int32
0x5740  stelem.ref
0x5741  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5746  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x574b  ldloc.1
0x574c  ldarg.1
0x574d  ldloc.1
0x574e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x5753  ldarg.0
0x5754  ldfld    class Microsoft.Crm.Dependency.DependencyNodeDictionary Microsoft.Crm.Dependency.ComponentCollector::_nodeCache
0x5759  call     class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper(int32 componentType, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord> records, class Microsoft.Crm.Dependency.DependencyNodeDictionary cache)
0x575e  ldarg.2
0x575f  callvirt instance void Microsoft.Crm.Dependency.IDependencyHelper::UpdateDependencies(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5764  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5769  ldstr    aDependencyBegi_3// "Dependency_BEGIN_{0}.UpdateComponentDep"...
0x576e  ldc.i4.2
0x576f  newarr   [mscorlib]System.Object
0x5774  dup
0x5775  ldc.i4.0
0x5776  ldarg.0
0x5777  stelem.ref
0x5778  dup
0x5779  ldc.i4.1
0x577a  ldloc.1
0x577b  box      [mscorlib]System.Int32
0x5780  stelem.ref
0x5781  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5786  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x578b  ldloca.s 0
0x578d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::MoveNext()
0x5792  brtrue.s loc_571C
0x5794  leave.s  loc_57A4
0x5796  ldloca.s 0
0x5798  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>
0x579e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57a3  endfinally
0x57a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57a9  ldstr    aDependencyEnd0_2// "Dependency_END_{0}.UpdateComponentDepen"...
0x57ae  ldc.i4.1
0x57af  newarr   [mscorlib]System.Object
0x57b4  dup
0x57b5  ldc.i4.0
0x57b6  ldarg.0
0x57b7  stelem.ref
0x57b8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57bd  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x57c2  ret
```
