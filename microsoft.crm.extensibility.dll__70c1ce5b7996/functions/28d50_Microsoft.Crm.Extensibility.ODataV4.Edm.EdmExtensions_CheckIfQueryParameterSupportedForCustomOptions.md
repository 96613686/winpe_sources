# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::CheckIfQueryParameterSupportedForCustomOptions

- ea: `0x28d50`
- end: `0x28dc8`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::CheckIfQueryParameterSupportedForCustomOptions`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x28c90`

## callees

- `0x28d50`

## string_xrefs

- `0x28d9b`: `$skiptoken`
- `0x28d81`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x28d50  ldarg.0
0x28d51  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x28d56  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x28d5b  stloc.0
0x28d5c  br.s     loc_28DAB
0x28d5e  ldloca.s 0
0x28d60  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x28d65  stloc.1
0x28d66  ldloc.1
0x28d67  ldstr    aSavedquery_1// "savedQuery"
0x28d6c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x28d71  brtrue.s loc_28DAB
0x28d73  ldloc.1
0x28d74  ldstr    aUserquery_1// "userQuery"
0x28d79  callvirt instance bool [mscorlib]System.String::Equals(string)
0x28d7e  brtrue.s loc_28DAB
0x28d80  ldloc.1
0x28d81  ldstr    aFetchxml// "fetchXml"
0x28d86  callvirt instance bool [mscorlib]System.String::Equals(string)
0x28d8b  brtrue.s loc_28DAB
0x28d8d  ldloc.1
0x28d8e  ldstr    aSolutionVersio// "solution-versions"
0x28d93  callvirt instance bool [mscorlib]System.String::Equals(string)
0x28d98  brtrue.s loc_28DAB
0x28d9a  ldloc.1
0x28d9b  ldstr    aSkiptoken// "$skiptoken"
0x28da0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x28da5  brtrue.s loc_28DAB
0x28da7  ldc.i4.0
0x28da8  stloc.2
0x28da9  leave.s  loc_28DC6
0x28dab  ldloca.s 0
0x28dad  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x28db2  brtrue.s loc_28D5E
0x28db4  leave.s  loc_28DC4
0x28db6  ldloca.s 0
0x28db8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x28dbe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28dc3  endfinally
0x28dc4  ldc.i4.1
0x28dc5  ret
0x28dc6  ldloc.2
0x28dc7  ret
```
