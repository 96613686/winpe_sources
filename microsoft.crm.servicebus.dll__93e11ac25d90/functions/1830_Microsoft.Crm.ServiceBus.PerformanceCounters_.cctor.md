# Microsoft.Crm.ServiceBus.PerformanceCounters::.cctor

- ea: `0x1830`
- end: `0x1841`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::.cctor`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x1830`: `CRM Router Service`

## pseudocode

```c

```

## disassembly

```asm
0x1830  ldstr    aCrmRouterServi// "CRM Router Service"
0x1835  stsfld   string Microsoft.Crm.ServiceBus.PerformanceCounters::RouterCategoryName
0x183a  ldnull
0x183b  stsfld   class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::_current
0x1840  ret
```
