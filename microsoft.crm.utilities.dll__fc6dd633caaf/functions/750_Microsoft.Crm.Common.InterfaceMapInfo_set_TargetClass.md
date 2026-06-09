# Microsoft.Crm.Common.InterfaceMapInfo::set_TargetClass

- ea: `0x750`
- end: `0x75d`
- name: `Microsoft.Crm.Common.InterfaceMapInfo::set_TargetClass`
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
0x750  ldarg.0
0x751  ldstr    aTargetclass// "targetclass"
0x756  ldarg.1
0x757  call     instance void [System.Configuration]System.Configuration.ConfigurationElement::set_Item(string, object)
0x75c  ret
```
