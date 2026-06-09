# Microsoft.Crm.Common.InterfaceMapInfo::get_TargetClass

- ea: `0x730`
- end: `0x741`
- name: `Microsoft.Crm.Common.InterfaceMapInfo::get_TargetClass`
- size: `17`
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
0x730  ldarg.0
0x731  ldstr    aTargetclass// "targetclass"
0x736  call     instance object [System.Configuration]System.Configuration.ConfigurationElement::get_Item(string)
0x73b  castclass [mscorlib]System.String
0x740  ret
```
