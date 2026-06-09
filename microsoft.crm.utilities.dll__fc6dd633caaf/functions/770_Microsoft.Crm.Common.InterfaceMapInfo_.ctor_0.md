# Microsoft.Crm.Common.InterfaceMapInfo::.ctor_0

- ea: `0x770`
- end: `0x785`
- name: `Microsoft.Crm.Common.InterfaceMapInfo::.ctor_0`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x720`
- `0x750`

## pseudocode

```c

```

## disassembly

```asm
0x770  ldarg.0
0x771  call     instance void [System.Configuration]System.Configuration.ConfigurationSection::.ctor()
0x776  ldarg.0
0x777  ldarg.1
0x778  call     instance void Microsoft.Crm.Common.InterfaceMapInfo::set_SourceClass(string value)
0x77d  ldarg.0
0x77e  ldarg.2
0x77f  call     instance void Microsoft.Crm.Common.InterfaceMapInfo::set_TargetClass(string value)
0x784  ret
```
