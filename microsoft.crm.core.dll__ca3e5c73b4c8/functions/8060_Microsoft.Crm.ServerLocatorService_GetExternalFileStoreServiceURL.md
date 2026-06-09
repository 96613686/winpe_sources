# Microsoft.Crm.ServerLocatorService::GetExternalFileStoreServiceURL

- ea: `0x8060`
- end: `0x80dc`
- name: `Microsoft.Crm.ServerLocatorService::GetExternalFileStoreServiceURL`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8060`
- `0x9710`
- `0x1be90`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`

## string_xrefs

- `0x80b6`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x80b1`: `GetExternalFileStoreServiceURL`

## pseudocode

```c

```

## disassembly

```asm
0x8060  ldarg.1
0x8061  ldstr    aOrganizationid_0// "organizationId"
0x8066  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x806b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8070  stloc.0
0x8071  ldloc.0
0x8072  ldstr    aOrganizationid_1// "OrganizationId"
0x8077  ldarg.1
0x8078  box      [mscorlib]System.Guid
0x807d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8082  ldloc.0
0x8083  ldstr    aOrgapplication// "OrgApplicationType"
0x8088  ldc.i4.8
0x8089  box      [mscorlib]System.Int32
0x808e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8093  ldstr    aOrgapplication_0// "OrgApplicationMap"
0x8098  stloc.1
0x8099  ldstr    aConnectionstri_0// "ConnectionString"
0x809e  stloc.2
0x809f  ldarg.0
0x80a0  ldloc.1
0x80a1  ldc.i4.1
0x80a2  newarr   [mscorlib]System.String
0x80a7  dup
0x80a8  ldc.i4.0
0x80a9  ldloc.2
0x80aa  stelem.ref
0x80ab  ldloc.0
0x80ac  ldc.i4   0x3EF
0x80b1  ldstr    aGetexternalfil// "GetExternalFileStoreServiceURL"
0x80b6  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x80bb  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x80c0  stloc.3
0x80c1  ldloc.3
0x80c2  brfalse.s loc_80DA
0x80c4  ldloc.3
0x80c5  ldloc.2
0x80c6  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0x80cb  brfalse.s loc_80DA
0x80cd  ldloc.3
0x80ce  ldloc.2
0x80cf  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x80d4  castclass [mscorlib]System.String
0x80d9  ret
0x80da  ldnull
0x80db  ret
```
