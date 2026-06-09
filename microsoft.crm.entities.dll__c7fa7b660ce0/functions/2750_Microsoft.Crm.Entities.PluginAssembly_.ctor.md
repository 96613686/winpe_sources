# Microsoft.Crm.Entities.PluginAssembly::.ctor

- ea: `0x2750`
- end: `0x275d`
- name: `Microsoft.Crm.Entities.PluginAssembly::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x2751`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x2750  ldarg.0
0x2751  ldstr    aPluginassembly// "PluginAssembly"
0x2756  ldarg.1
0x2757  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x275c  ret
```
