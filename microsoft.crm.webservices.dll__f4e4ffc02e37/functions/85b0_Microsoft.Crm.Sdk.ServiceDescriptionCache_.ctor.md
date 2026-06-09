# Microsoft.Crm.Sdk.ServiceDescriptionCache::.ctor

- ea: `0x85b0`
- end: `0x85cd`
- name: `Microsoft.Crm.Sdk.ServiceDescriptionCache::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8600`

## callees

- `0x10220`

## string_xrefs

- `0x85b1`: `ServiceDescriptionCache`

## pseudocode

```c

```

## disassembly

```asm
0x85b0  ldarg.0
0x85b1  ldstr    aServicedescrip_0// "ServiceDescriptionCache"
0x85b6  ldc.i4.0
0x85b7  newarr   [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0x85bc  call     instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCache`2<string, class Microsoft.Crm.Sdk.ServiceDescription>::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType[])
0x85c1  ldarg.0
0x85c2  newobj   instance void ServiceDescriptionCacheLoader::.ctor()
0x85c7  call     instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Sdk.ServiceDescription>::SetLoader(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0>)
0x85cc  ret
```
