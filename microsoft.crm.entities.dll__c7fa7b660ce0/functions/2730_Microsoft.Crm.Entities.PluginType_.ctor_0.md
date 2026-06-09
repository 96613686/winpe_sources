# Microsoft.Crm.Entities.PluginType::.ctor_0

- ea: `0x2730`
- end: `0x273d`
- name: `Microsoft.Crm.Entities.PluginType::.ctor_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x2731`: `PluginType`

## pseudocode

```c

```

## disassembly

```asm
0x2730  ldarg.0
0x2731  ldstr    aPlugintype// "PluginType"
0x2736  ldarg.1
0x2737  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x273c  ret
```
