# Microsoft.Crm.ScaleGroupApi.FilterConfig::RegisterGlobalFilters

- ea: `0x290`
- end: `0x29c`
- name: `Microsoft.Crm.ScaleGroupApi.FilterConfig::RegisterGlobalFilters`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa10`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldarg.0
0x291  newobj   instance void [System.Web.Mvc]System.Web.Mvc.HandleErrorAttribute::.ctor()
0x296  callvirt instance void [System.Web.Mvc]System.Web.Mvc.GlobalFilterCollection::Add(object)
0x29b  ret
```
