# Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::.ctor

- ea: `0xe5c0`
- end: `0xe5d9`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xc520`
- `0xc5b0`

## callees

- `0xc4a0`
- `0xe5e0`

## pseudocode

```c

```

## disassembly

```asm
0xe5c0  ldarg.0
0xe5c1  ldarg.2
0xe5c2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_AsyncEvent()
0xe5c7  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0xe5cc  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0xe5d1  ldarg.0
0xe5d2  ldarg.1
0xe5d3  stfld    string Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::_name
0xe5d8  ret
```
