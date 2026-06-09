# Microsoft.Crm.Dependency.ComponentCollector::DetermineWhetherComponentsExist

- ea: `0x5e70`
- end: `0x5f91`
- name: `Microsoft.Crm.Dependency.ComponentCollector::DetermineWhetherComponentsExist`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x5970`

## callees

- `0x5e70`
- `0x5fa0`
- `0x68f0`
- `0x6aa0`

## string_xrefs

- `0x5e71`: `recordsByComponentType`
- `0x5eaa`: `Dependency_BEGIN_{0}.DetermineWhetherComponentsExist(ComponentType={1})`
- `0x5f52`: `Dependency_END_{0}.DetermineWhetherComponentsExist(ComponentType={1})`

## pseudocode

```c

```

## disassembly

```asm
0x5e70  ldarg.1
0x5e71  ldstr    aRecordsbycompo// "recordsByComponentType"
0x5e76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5e7b  ldarg.2
0x5e7c  ldstr    aContext// "context"
0x5e81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5e86  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::.ctor()
0x5e8b  stloc.0
0x5e8c  ldarg.1
0x5e8d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Keys()
0x5e92  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::GetEnumerator()
0x5e97  stloc.1
0x5e98  br       loc_5F74
0x5e9d  ldloca.s 1
0x5e9f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Current()
0x5ea4  stloc.2
0x5ea5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5eaa  ldstr    aDependencyBegi_7// "Dependency_BEGIN_{0}.DetermineWhetherCo"...
0x5eaf  ldc.i4.2
0x5eb0  newarr   [mscorlib]System.Object
0x5eb5  dup
0x5eb6  ldc.i4.0
0x5eb7  ldarg.0
0x5eb8  stelem.ref
0x5eb9  dup
0x5eba  ldc.i4.1
0x5ebb  ldloc.2
0x5ebc  box      [mscorlib]System.Int32
0x5ec1  stelem.ref
0x5ec2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ec7  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5ecc  ldloc.0
0x5ecd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::Clear()
0x5ed2  ldarg.1
0x5ed3  ldloc.2
0x5ed4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x5ed9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x5ede  stloc.3
0x5edf  br.s     loc_5F1F
0x5ee1  ldloca.s 3
0x5ee3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x5ee8  stloc.s  4
0x5eea  ldloc.0
0x5eeb  ldloc.s  4
0x5eed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x5ef2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::ContainsKey(var<u1>)
0x5ef7  brtrue.s loc_5F0B
0x5ef9  ldloc.0
0x5efa  ldloc.s  4
0x5efc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x5f01  newobj   instance void Microsoft.Crm.Dependency.ComponentCollectorRecordCollection::.ctor()
0x5f06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::Add(var<u1>, !!T0)
0x5f0b  ldloc.0
0x5f0c  ldloc.s  4
0x5f0e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x5f13  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x5f18  ldloc.s  4
0x5f1a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::Add(var<u1>)
0x5f1f  ldloca.s 3
0x5f21  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x5f26  brtrue.s loc_5EE1
0x5f28  leave.s  loc_5F38
0x5f2a  ldloca.s 3
0x5f2c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x5f32  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f37  endfinally
0x5f38  ldarg.0
0x5f39  ldloc.2
0x5f3a  ldloc.0
0x5f3b  ldloc.0
0x5f3c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Keys()
0x5f41  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x5f46  ldarg.2
0x5f47  ldarg.3
0x5f48  call     instance void Microsoft.Crm.Dependency.ComponentCollector::Evaluate(int32 componentType, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection> recordsByComponentId, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids, class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection> invalidDependencies)
0x5f4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f52  ldstr    aDependencyEnd0_6// "Dependency_END_{0}.DetermineWhetherComp"...
0x5f57  ldc.i4.2
0x5f58  newarr   [mscorlib]System.Object
0x5f5d  dup
0x5f5e  ldc.i4.0
0x5f5f  ldarg.0
0x5f60  stelem.ref
0x5f61  dup
0x5f62  ldc.i4.1
0x5f63  ldloc.2
0x5f64  box      [mscorlib]System.Int32
0x5f69  stelem.ref
0x5f6a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5f6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5f74  ldloca.s 1
0x5f76  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::MoveNext()
0x5f7b  brtrue   loc_5E9D
0x5f80  leave.s  loc_5F90
0x5f82  ldloca.s 1
0x5f84  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>
0x5f8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f8f  endfinally
0x5f90  ret
```
