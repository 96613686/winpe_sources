# Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor

- ea: `0x1a050`
- end: `0x1a05e`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor`
- size: `14`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a580`
- `0x1a660`
- `0x1a730`
- `0x1a800`
- `0x1a8d0`
- `0x1a9a0`
- `0x1aa70`
- `0x1ab40`

## callees

- `0x1a070`

## pseudocode

```c

```

## disassembly

```asm
0x1a050  ldarg.0
0x1a051  ldarg.1
0x1a052  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceContextInitializer`1<class Microsoft.Xrm.Sdk.IOrganizationService>::.ctor(class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>)
0x1a057  ldarg.0
0x1a058  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::Initialize()
0x1a05d  ret
```
