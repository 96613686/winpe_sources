# Microsoft.Crm.Common.InterfaceMapper::get_InterfaceMapValues

- ea: `0x7b0`
- end: `0x7bb`
- name: `Microsoft.Crm.Common.InterfaceMapper::get_InterfaceMapValues`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x970`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo> Microsoft.Crm.Common.InterfaceMapper::_interfaceMap
0x7b5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo>::get_Values()
0x7ba  ret
```
