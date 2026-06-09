# Microsoft.Crm.Dependency.ComponentCollector::AddComponentsToSolutions

- ea: `0x5830`
- end: `0x5915`
- name: `Microsoft.Crm.Dependency.ComponentCollector::AddComponentsToSolutions`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x5180`

## callees

- `0x5830`
- `0x5920`
- `0x68f0`
- `0x6910`
- `0x6950`
- `0x6ca0`
- `0x73e0`

## string_xrefs

- `0x5850`: `SolutionComponent`
- `0x5889`: `componenttype`

## pseudocode

```c

```

## disassembly

```asm
0x5830  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0x5835  stloc.0
0x5836  ldarg.1
0x5837  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x583c  stloc.1
0x583d  br.s     loc_58A5
0x583f  ldloca.s 1
0x5841  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x5846  stloc.2
0x5847  ldarg.0
0x5848  ldloc.2
0x5849  call     instance bool Microsoft.Crm.Dependency.ComponentCollector::ShouldAddComponentToRootCalculation(class Microsoft.Crm.Dependency.ComponentCollectorRecord record)
0x584e  brfalse.s loc_58A5
0x5850  ldstr    aSolutioncompon// "SolutionComponent"
0x5855  ldarg.2
0x5856  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x585b  stloc.3
0x585c  ldloc.3
0x585d  ldstr    aSolutionid_0// "solutionid"
0x5862  ldloc.2
0x5863  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_OriginalSolutionId()
0x5868  box      [mscorlib]System.Guid
0x586d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5872  ldloc.3
0x5873  ldstr    aObjectid// "objectid"
0x5878  ldloc.2
0x5879  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x587e  box      [mscorlib]System.Guid
0x5883  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5888  ldloc.3
0x5889  ldstr    aComponenttype// "componenttype"
0x588e  ldloc.2
0x588f  callvirt instance int32 Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentType()
0x5894  box      [mscorlib]System.Int32
0x5899  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x589e  ldloc.0
0x589f  ldloc.3
0x58a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::Add(var<u1>)
0x58a5  ldloca.s 1
0x58a7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x58ac  brtrue.s loc_583F
0x58ae  leave.s  loc_58BE
0x58b0  ldloca.s 1
0x58b2  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x58b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58bd  endfinally
0x58be  ldloc.0
0x58bf  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Count()
0x58c4  ldc.i4.0
0x58c5  ble.s    loc_5914
0x58c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58cc  ldstr    aDependencyBegi_5// "Dependency_BEGIN_{0}.ProcessRecord: IDe"...
0x58d1  ldc.i4.1
0x58d2  newarr   [mscorlib]System.Object
0x58d7  dup
0x58d8  ldc.i4.0
0x58d9  ldarg.0
0x58da  stelem.ref
0x58db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x58e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x58e5  call     class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper()
0x58ea  ldloc.0
0x58eb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::ToArray()
0x58f0  ldarg.2
0x58f1  callvirt instance void Microsoft.Crm.Dependency.IDependencyHelper::FindAndAddRoots(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity[] entities, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58f6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58fb  ldstr    aDependencyEnd0_4// "Dependency_END_{0}.ProcessRecord: IDepe"...
0x5900  ldc.i4.1
0x5901  newarr   [mscorlib]System.Object
0x5906  dup
0x5907  ldc.i4.0
0x5908  ldarg.0
0x5909  stelem.ref
0x590a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x590f  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5914  ret
```
