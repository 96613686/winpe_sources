# Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectAssembly

- ea: `0x1500`
- end: `0x158d`
- name: `Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectAssembly`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x13e0`
- `0x13f0`
- `0x1400`
- `0x1420`
- `0x1460`
- `0x1470`
- `0x14a0`
- `0x1500`
- `0x17e0`
- `0x1830`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarg.0
0x1501  ldftn    instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::CurrentDomain_ReflectionOnlyAssemblyResolve(object sender, class [mscorlib]System.ResolveEventArgs args)
0x1507  newobj   instance void [mscorlib]System.ResolveEventHandler::.ctor(object, native int)
0x150c  stloc.0
0x150d  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1512  ldloc.0
0x1513  callvirt instance void [mscorlib]System.AppDomain::add_ReflectionOnlyAssemblyResolve(class [mscorlib]System.ResolveEventHandler)
0x1518  call     void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::PreLoadV4Assemblies()
0x151d  ldarg.0
0x151e  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::LoadAssembly()
0x1523  stloc.1
0x1524  ldarg.0
0x1525  ldarg.0
0x1526  ldloc.1
0x1527  call     instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::DoesAssemblyReferenceV4Interfaces(class [mscorlib]System.Reflection.Assembly loadedAssembly)
0x152c  call     instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_IsV4Assembly(bool value)
0x1531  ldarg.0
0x1532  call     instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_IsV4Assembly()
0x1537  brfalse.s loc_157E
0x1539  ldarg.0
0x153a  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_PluginSteps()
0x153f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::GetEnumerator()
0x1544  stloc.2
0x1545  br.s     loc_1565
0x1547  ldloca.s 2
0x1549  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::get_Current()
0x154e  stloc.3
0x154f  ldarg.0
0x1550  ldloc.1
0x1551  ldloc.3
0x1552  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_PluginType()
0x1557  call     instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::IsV4Plugin(class [mscorlib]System.Reflection.Assembly loadedAssembly, string pluginTypeName)
0x155c  brfalse.s loc_1565
0x155e  ldloc.3
0x155f  ldc.i4.1
0x1560  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::set_IsV4Plugin(bool value)
0x1565  ldloca.s 2
0x1567  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::MoveNext()
0x156c  brtrue.s loc_1547
0x156e  leave.s  loc_158C
0x1570  ldloca.s 2
0x1572  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>
0x1578  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157d  endfinally
0x157e  leave.s  loc_158C
0x1580  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1585  ldloc.0
0x1586  callvirt instance void [mscorlib]System.AppDomain::remove_ReflectionOnlyAssemblyResolve(class [mscorlib]System.ResolveEventHandler)
0x158b  endfinally
0x158c  ret
```
