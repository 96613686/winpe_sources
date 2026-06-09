# Microsoft.Crm.ScaleGroupApi.RouteConfig::RegisterRoutes

- ea: `0x2b0`
- end: `0x2bc`
- name: `Microsoft.Crm.ScaleGroupApi.RouteConfig::RegisterRoutes`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa10`

## string_xrefs

- `0x2b1`: `{resource}.axd/{*pathInfo}`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  ldstr    aResourceAxdPat// "{resource}.axd/{*pathInfo}"
0x2b6  call     void [System.Web.Mvc]System.Web.Mvc.RouteCollectionExtensions::IgnoreRoute(class [System.Web]System.Web.Routing.RouteCollection, string)
0x2bb  ret
```
