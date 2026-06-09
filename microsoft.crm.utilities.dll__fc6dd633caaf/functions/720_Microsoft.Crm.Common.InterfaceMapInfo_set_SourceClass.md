# Microsoft.Crm.Common.InterfaceMapInfo::set_SourceClass

- ea: `0x720`
- end: `0x72d`
- name: `Microsoft.Crm.Common.InterfaceMapInfo::set_SourceClass`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x770`

## pseudocode

```c

```

## disassembly

```asm
0x720  ldarg.0
0x721  ldstr    aSourceclass// "sourceclass"
0x726  ldarg.1
0x727  call     instance void [System.Configuration]System.Configuration.ConfigurationElement::set_Item(string, object)
0x72c  ret
```
