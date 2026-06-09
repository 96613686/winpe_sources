# Microsoft.Crm.Common.InterfaceMapCollection::GetElementKey

- ea: `0x6d0`
- end: `0x6dc`
- name: `Microsoft.Crm.Common.InterfaceMapCollection::GetElementKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x700`

## pseudocode

```c

```

## disassembly

```asm
0x6d0  ldarg.1
0x6d1  castclass Microsoft.Crm.Common.InterfaceMapInfo
0x6d6  callvirt instance string Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass()
0x6db  ret
```
