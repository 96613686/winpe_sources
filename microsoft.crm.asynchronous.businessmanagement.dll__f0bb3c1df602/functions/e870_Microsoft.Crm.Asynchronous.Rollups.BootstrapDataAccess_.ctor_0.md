# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::.ctor_0

- ea: `0xe870`
- end: `0xe89b`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::.ctor_0`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xbd10`
- `0xc1b0`

## callees

- `0xe7c0`
- `0xe810`

## string_xrefs

- `0xe889`: `RollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xe870  ldarg.0
0xe871  ldarg.1
0xe872  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xe877  ldarg.0
0xe878  ldarg.1
0xe879  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe87e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xe883  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::set_OrganizationContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext value)
0xe888  ldarg.2
0xe889  ldstr    aRollupproperti// "RollupPropertiesId"
0xe88e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe893  ldarg.0
0xe894  ldarg.2
0xe895  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::set_RollupPropertiesId(valuetype [mscorlib]System.Guid value)
0xe89a  ret
```
