# Microsoft.Crm.Common.InterfaceMapper::LoadMapping

- ea: `0x7a0`
- end: `0x7ab`
- name: `Microsoft.Crm.Common.InterfaceMapper::LoadMapping`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x970`

## callees

- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo> Microsoft.Crm.Common.InterfaceMapper::GetMapping()
0x7a5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Common.InterfaceMapInfo> Microsoft.Crm.Common.InterfaceMapper::_interfaceMap
0x7aa  ret
```
