# Microsoft.Crm.Common.InterfaceMappingConfigSection::get_InterfaceMap

- ea: `0x830`
- end: `0x841`
- name: `Microsoft.Crm.Common.InterfaceMappingConfigSection::get_InterfaceMap`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldarg.0
0x831  ldstr    aInterfacemap// "InterfaceMap"
0x836  call     instance object [System.Configuration]System.Configuration.ConfigurationElement::get_Item(string)
0x83b  castclass Microsoft.Crm.Common.InterfaceMapCollection
0x840  ret
```
