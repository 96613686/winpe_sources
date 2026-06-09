# Microsoft.Crm.WebServices.AspNetServiceDescriptionCache::.ctor

- ea: `0xd680`
- end: `0xd69d`
- name: `Microsoft.Crm.WebServices.AspNetServiceDescriptionCache::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd700`

## callees

- `0x10760`

## string_xrefs

- `0xd681`: `AspNetServiceDescriptionCache`

## pseudocode

```c

```

## disassembly

```asm
0xd680  ldarg.0
0xd681  ldstr    aAspnetserviced// "AspNetServiceDescriptionCache"
0xd686  ldc.i4.0
0xd687  newarr   [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0xd68c  call     instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCache`2<class Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey, class [System.Web.Services]System.Web.Services.Description.ServiceDescription>::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType[])
0xd691  ldarg.0
0xd692  newobj   instance void AspNetServiceDescriptionLoader::.ctor()
0xd697  call     instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey, class [System.Web.Services]System.Web.Services.Description.ServiceDescription>::SetLoader(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0>)
0xd69c  ret
```
