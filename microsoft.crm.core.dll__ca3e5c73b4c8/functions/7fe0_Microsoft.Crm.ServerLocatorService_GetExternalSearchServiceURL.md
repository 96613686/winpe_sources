# Microsoft.Crm.ServerLocatorService::GetExternalSearchServiceURL

- ea: `0x7fe0`
- end: `0x805c`
- name: `Microsoft.Crm.ServerLocatorService::GetExternalSearchServiceURL`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7fe0`
- `0x9710`
- `0x1be90`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`

## string_xrefs

- `0x8036`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8031`: `GetExternalSearchServiceURL`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  ldarg.1
0x7fe1  ldstr    aOrganizationid_0// "organizationId"
0x7fe6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x7feb  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x7ff0  stloc.0
0x7ff1  ldloc.0
0x7ff2  ldstr    aOrganizationid_1// "OrganizationId"
0x7ff7  ldarg.1
0x7ff8  box      [mscorlib]System.Guid
0x7ffd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8002  ldloc.0
0x8003  ldstr    aOrgapplication// "OrgApplicationType"
0x8008  ldc.i4.1
0x8009  box      [mscorlib]System.Int32
0x800e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8013  ldstr    aOrgapplication_0// "OrgApplicationMap"
0x8018  stloc.1
0x8019  ldstr    aConnectionstri_0// "ConnectionString"
0x801e  stloc.2
0x801f  ldarg.0
0x8020  ldloc.1
0x8021  ldc.i4.1
0x8022  newarr   [mscorlib]System.String
0x8027  dup
0x8028  ldc.i4.0
0x8029  ldloc.2
0x802a  stelem.ref
0x802b  ldloc.0
0x802c  ldc.i4   0x3DA
0x8031  ldstr    aGetexternalsea// "GetExternalSearchServiceURL"
0x8036  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x803b  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8040  stloc.3
0x8041  ldloc.3
0x8042  brfalse.s loc_805A
0x8044  ldloc.3
0x8045  ldloc.2
0x8046  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0x804b  brfalse.s loc_805A
0x804d  ldloc.3
0x804e  ldloc.2
0x804f  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8054  castclass [mscorlib]System.String
0x8059  ret
0x805a  ldnull
0x805b  ret
```
