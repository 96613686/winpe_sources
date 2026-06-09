# Microsoft.Crm.Asynchronous.BulkDeleteUserHasBulkDeletePrivilegeActivity::.ctor

- ea: `0xec0`
- end: `0xece`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteUserHasBulkDeletePrivilegeActivity::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0xec1`: `Microsoft.Crm.Asynchronous.BulkDeleteServiceUserHasBulkDeletePrivilegeActivity`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldarg.0
0xec1  ldstr    aMicrosoftCrmAs_3// "Microsoft.Crm.Asynchronous.BulkDeleteSe"...
0xec6  ldc.i4.1
0xec7  ldc.i4.1
0xec8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteUserHasBulkDeletePrivilegeActivity>::.ctor(string, bool, bool)
0xecd  ret
```
