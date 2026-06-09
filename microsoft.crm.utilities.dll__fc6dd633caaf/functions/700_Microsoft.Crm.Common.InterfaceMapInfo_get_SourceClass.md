# Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass

- ea: `0x700`
- end: `0x711`
- name: `Microsoft.Crm.Common.InterfaceMapInfo::get_SourceClass`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x6d0`
- `0x7c0`
- `0x970`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  ldstr    aSourceclass// "sourceclass"
0x706  call     instance object [System.Configuration]System.Configuration.ConfigurationElement::get_Item(string)
0x70b  castclass [mscorlib]System.String
0x710  ret
```
