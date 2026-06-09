# Microsoft.Crm.LegacyFeatureCheck.Common.VerifyLegacyPluginsAction::InternalExecute

- ea: `0x18c0`
- end: `0x1a74`
- name: `Microsoft.Crm.LegacyFeatureCheck.Common.VerifyLegacyPluginsAction::InternalExecute`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xf40`
- `0x12e0`
- `0x1300`
- `0x1340`
- `0x1360`
- `0x13c0`
- `0x13e0`
- `0x1400`
- `0x1590`
- `0x17a0`
- `0x17c0`
- `0x17e0`
- `0x1800`
- `0x1820`
- `0x18c0`
- `0x1be0`
- `0x1bf0`
- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x18c0  ldarg.1
0x18c1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly> Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginAssemblies()
0x18c6  stloc.0
0x18c7  ldloc.0
0x18c8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::get_Count()
0x18cd  ldc.i4.0
0x18ce  ble      loc_1A5B
0x18d3  ldloc.0
0x18d4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::GetEnumerator()
0x18d9  stloc.1
0x18da  br       loc_1A3F
0x18df  ldloca.s 1
0x18e1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::get_Current()
0x18e6  stloc.2
0x18e7  ldloc.2
0x18e8  ldarg.1
0x18e9  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectInNewAppDomain(class Microsoft.Crm.LegacyFeatureCheck.Organization organization)
0x18ee  ldarg.0
0x18ef  ldarg.1
0x18f0  ldc.i4.2
0x18f1  ldloc.2
0x18f2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Id()
0x18f7  ldstr    aName0Version1L// "Name: {0}, Version: {1}, Length: {2}, L"...
0x18fc  ldc.i4.5
0x18fd  newarr   [mscorlib]System.Object
0x1902  dup
0x1903  ldc.i4.0
0x1904  ldloc.2
0x1905  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Name()
0x190a  stelem.ref
0x190b  dup
0x190c  ldc.i4.1
0x190d  ldloc.2
0x190e  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Version()
0x1913  stelem.ref
0x1914  dup
0x1915  ldc.i4.2
0x1916  ldloc.2
0x1917  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Contents()
0x191c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1921  box      [mscorlib]System.Int32
0x1926  stelem.ref
0x1927  dup
0x1928  ldc.i4.3
0x1929  ldloc.2
0x192a  callvirt instance valuetype Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Source()
0x192f  box      Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation
0x1934  stelem.ref
0x1935  dup
0x1936  ldc.i4.4
0x1937  ldloc.2
0x1938  callvirt instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_IsV4Assembly()
0x193d  box      [mscorlib]System.Boolean
0x1942  stelem.ref
0x1943  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x1948  ldloc.2
0x1949  callvirt instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_IsV4Assembly()
0x194e  brfalse  loc_1A04
0x1953  ldarg.0
0x1954  ldarg.1
0x1955  ldc.i4.2
0x1956  ldloc.2
0x1957  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Id()
0x195c  ldstr    aAssembly0WithV// "Assembly \"{0}\" with version '{1}' ref"...
0x1961  ldc.i4.2
0x1962  newarr   [mscorlib]System.Object
0x1967  dup
0x1968  ldc.i4.0
0x1969  ldloc.2
0x196a  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Name()
0x196f  stelem.ref
0x1970  dup
0x1971  ldc.i4.1
0x1972  ldloc.2
0x1973  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Version()
0x1978  stelem.ref
0x1979  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x197e  ldloc.2
0x197f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_PluginSteps()
0x1984  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::GetEnumerator()
0x1989  stloc.3
0x198a  br.s     loc_19EB
0x198c  ldloca.s 3
0x198e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::get_Current()
0x1993  stloc.s  4
0x1995  ldloc.s  4
0x1997  callvirt instance bool Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_IsV4Plugin()
0x199c  brfalse.s loc_19EB
0x199e  ldarg.0
0x199f  ldarg.1
0x19a0  ldc.i4.1
0x19a1  ldloc.s  4
0x19a3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_PluginTypeId()
0x19a8  ldstr    a0RegisteredFor// "'{0}' registered for '{1}' of '{2}' app"...
0x19ad  ldc.i4.3
0x19ae  newarr   [mscorlib]System.Object
0x19b3  dup
0x19b4  ldc.i4.0
0x19b5  ldloc.s  4
0x19b7  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_PluginType()
0x19bc  stelem.ref
0x19bd  dup
0x19be  ldc.i4.1
0x19bf  ldloc.s  4
0x19c1  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_SdkMessage()
0x19c6  stelem.ref
0x19c7  dup
0x19c8  ldc.i4.2
0x19c9  ldloc.s  4
0x19cb  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_Entity()
0x19d0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x19d5  brtrue.s loc_19E0
0x19d7  ldloc.s  4
0x19d9  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginStep::get_Entity()
0x19de  br.s     loc_19E5
0x19e0  ldstr    aAllEntities// "All entities"
0x19e5  stelem.ref
0x19e6  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x19eb  ldloca.s 3
0x19ed  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::MoveNext()
0x19f2  brtrue.s loc_198C
0x19f4  leave.s  loc_1A04
0x19f6  ldloca.s 3
0x19f8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>
0x19fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a03  endfinally
0x1a04  leave.s  loc_1A3F
0x1a06  stloc.s  5
0x1a08  ldarg.0
0x1a09  ldarg.1
0x1a0a  ldc.i4.2
0x1a0b  ldloc.2
0x1a0c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Id()
0x1a11  ldstr    aErrorWhileInsp// "Error while inspecting Assembly \"{0}\""...
0x1a16  ldc.i4.3
0x1a17  newarr   [mscorlib]System.Object
0x1a1c  dup
0x1a1d  ldc.i4.0
0x1a1e  ldloc.2
0x1a1f  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Name()
0x1a24  stelem.ref
0x1a25  dup
0x1a26  ldc.i4.1
0x1a27  ldloc.2
0x1a28  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Version()
0x1a2d  stelem.ref
0x1a2e  dup
0x1a2f  ldc.i4.2
0x1a30  ldloc.s  5
0x1a32  callvirt instance string [mscorlib]System.Object::ToString()
0x1a37  stelem.ref
0x1a38  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x1a3d  leave.s  loc_1A3F
0x1a3f  ldloca.s 1
0x1a41  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::MoveNext()
0x1a46  brtrue   loc_18DF
0x1a4b  leave.s  loc_1A73
0x1a4d  ldloca.s 1
0x1a4f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>
0x1a55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a5a  endfinally
0x1a5b  ldarg.0
0x1a5c  ldarg.1
0x1a5d  ldc.i4.2
0x1a5e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a63  ldstr    aNoCustomPlugIn// "No custom plug-in assembly found"
0x1a68  ldc.i4.0
0x1a69  newarr   [mscorlib]System.Object
0x1a6e  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x1a73  ret
```
