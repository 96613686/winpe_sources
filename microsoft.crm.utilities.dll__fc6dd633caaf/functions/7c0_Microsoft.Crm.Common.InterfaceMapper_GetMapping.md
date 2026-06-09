# Microsoft.Crm.Common.InterfaceMapper::GetMapping

- ea: `0x7c0`
- end: `0x820`
- name: `Microsoft.Crm.Common.InterfaceMapper::GetMapping`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7a0`

## callees

- `0x700`
- `0x7c0`
- `0x830`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo>::.ctor()
0x7c5  stloc.0
0x7c6  ldstr    aInterfacemappi// "InterfaceMapping"
0x7cb  call     object [System.Configuration]System.Configuration.ConfigurationManager::GetSection(string)
0x7d0  castclass Microsoft.Crm.Common.InterfaceMappingConfigSection
0x7d5  stloc.1
0x7d6  ldloc.1
0x7d7  brfalse.s loc_81E
0x7d9  ldloc.1
0x7da  callvirt instance class Microsoft.Crm.Common.InterfaceMapCollection Microsoft.Crm.Common.InterfaceMappingConfigSection::get_InterfaceMap()
0x7df  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Configuration]System.Configuration.ConfigurationElementCollection::GetEnumerator()
0x7e4  stloc.2
0x7e5  br.s     loc_800
0x7e7  ldloc.2
0x7e8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7ed  castclass Microsoft.Crm.Common.InterfaceMapInfo
0x7f2  stloc.3
0x7f3  ldloc.0
0x7f4  ldloc.3
0x7f5  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass()
0x7fa  ldloc.3
0x7fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo>::Add(var<u1>, !!T0)
0x800  ldloc.2
0x801  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x806  brtrue.s loc_7E7
0x808  leave.s  loc_81E
0x80a  ldloc.2
0x80b  isinst   [mscorlib]System.IDisposable
0x810  stloc.s  4
0x812  ldloc.s  4
0x814  brfalse.s loc_81D
0x816  ldloc.s  4
0x818  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x81d  endfinally
0x81e  ldloc.0
0x81f  ret
```
