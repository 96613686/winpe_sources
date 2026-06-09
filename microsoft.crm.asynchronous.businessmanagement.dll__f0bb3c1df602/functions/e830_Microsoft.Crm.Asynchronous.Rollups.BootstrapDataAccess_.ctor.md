# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::.ctor

- ea: `0xe830`
- end: `0xe862`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::.ctor`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xe7c0`
- `0xe810`

## string_xrefs

- `0xe850`: `RollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xe830  ldarg.0
0xe831  ldarg.2
0xe832  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xe837  ldarg.0
0xe838  ldarg.1
0xe839  stfld    string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::_name
0xe83e  ldarg.0
0xe83f  ldarg.2
0xe840  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe845  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xe84a  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::set_OrganizationContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext value)
0xe84f  ldarg.3
0xe850  ldstr    aRollupproperti// "RollupPropertiesId"
0xe855  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe85a  ldarg.0
0xe85b  ldarg.3
0xe85c  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::set_RollupPropertiesId(valuetype [mscorlib]System.Guid value)
0xe861  ret
```
