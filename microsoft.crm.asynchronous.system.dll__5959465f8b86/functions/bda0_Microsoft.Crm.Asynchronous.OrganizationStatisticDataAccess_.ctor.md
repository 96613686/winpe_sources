# Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::.ctor

- ea: `0xbda0`
- end: `0xbdae`
- name: `Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::.ctor`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb4c0`
- `0xb640`
- `0xb8b0`
- `0xb990`
- `0xb9c0`

## pseudocode

```c

```

## disassembly

```asm
0xbda0  ldarg.0
0xbda1  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::.ctor()
0xbda6  ldarg.0
0xbda7  ldarg.1
0xbda8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::_organizationId
0xbdad  ret
```
