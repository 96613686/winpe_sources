# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_CanRemoveCompletedJobs

- ea: `0xbbf0`
- end: `0xbc42`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_CanRemoveCompletedJobs`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbac0`
- `0xbbf0`

## string_xrefs

- `0xbc04`: `AsyncRemoveCompletedJobs`
- `0xbc14`: `AsyncRemoveCompletedJobs`
- `0xbc21`: `AsyncRemoveCompletedJobs`
- `0xbc30`: `AsyncRemoveCompletedJobs`

## pseudocode

```c

```

## disassembly

```asm
0xbbf0  ldarg.0
0xbbf1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_locatorService
0xbbf6  ldarg.0
0xbbf7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xbbfc  ldc.i4.1
0xbbfd  newarr   [mscorlib]System.String
0xbc02  dup
0xbc03  ldc.i4.0
0xbc04  ldstr    aAsyncremovecom// "AsyncRemoveCompletedJobs"
0xbc09  stelem.ref
0xbc0a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetOrganization(valuetype [mscorlib]System.Guid, string[])
0xbc0f  stloc.0
0xbc10  ldloc.0
0xbc11  brfalse.s loc_BC40
0xbc13  ldloc.0
0xbc14  ldstr    aAsyncremovecom// "AsyncRemoveCompletedJobs"
0xbc19  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xbc1e  brfalse.s loc_BC40
0xbc20  ldloc.0
0xbc21  ldstr    aAsyncremovecom// "AsyncRemoveCompletedJobs"
0xbc26  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbc2b  brtrue.s loc_BC2F
0xbc2d  ldc.i4.1
0xbc2e  ret
0xbc2f  ldloc.0
0xbc30  ldstr    aAsyncremovecom// "AsyncRemoveCompletedJobs"
0xbc35  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbc3a  unbox.any [mscorlib]System.Boolean
0xbc3f  ret
0xbc40  ldc.i4.1
0xbc41  ret
```
