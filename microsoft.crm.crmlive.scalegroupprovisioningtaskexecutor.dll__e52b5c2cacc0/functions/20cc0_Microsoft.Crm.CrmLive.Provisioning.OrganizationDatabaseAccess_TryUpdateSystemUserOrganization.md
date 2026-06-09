# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::TryUpdateSystemUserOrganization

- ea: `0x20cc0`
- end: `0x20d8a`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::TryUpdateSystemUserOrganization`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x20c80`
- `0x20ca0`

## callees

- `0x20cc0`

## string_xrefs

- `0x20d11`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x20d72`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x20d0c`: `TryUpdateSystemUserOrganization`
- `0x20d6d`: `TryUpdateSystemUserOrganization`

## pseudocode

```c

```

## disassembly

```asm
0x20cc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20cc5  stloc.0
0x20cc6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x20ccb  stloc.1
0x20ccc  ldloc.1
0x20ccd  ldstr    aOrganizationid_0// "OrganizationId"
0x20cd2  ldarg.0
0x20cd3  box      [mscorlib]System.Guid
0x20cd8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x20cdd  ldloc.1
0x20cde  ldstr    aCrmuserid// "CrmUserId"
0x20ce3  ldarg.1
0x20ce4  box      [mscorlib]System.Guid
0x20ce9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x20cee  ldloc.0
0x20cef  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x20cf4  ldc.i4.2
0x20cf5  newarr   [mscorlib]System.String
0x20cfa  dup
0x20cfb  ldc.i4.0
0x20cfc  ldstr    aId// "Id"
0x20d01  stelem.ref
0x20d02  dup
0x20d03  ldc.i4.1
0x20d04  ldarg.2
0x20d05  stelem.ref
0x20d06  ldloc.1
0x20d07  ldc.i4   0xE66
0x20d0c  ldstr    aTryupdatesyste// "TryUpdateSystemUserOrganization"
0x20d11  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x20d16  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20d1b  stloc.2
0x20d1c  ldloc.2
0x20d1d  brtrue.s loc_20D21
0x20d1f  leave.s  loc_20D89
0x20d21  ldc.i4.0
0x20d22  stloc.3
0x20d23  ldloc.2
0x20d24  ldarg.2
0x20d25  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x20d2a  brfalse.s loc_20D3B
0x20d2c  ldloc.2
0x20d2d  ldarg.2
0x20d2e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x20d33  unbox.any [mscorlib]System.Boolean
0x20d38  ldarg.3
0x20d39  beq.s    loc_20D3D
0x20d3b  ldc.i4.1
0x20d3c  stloc.3
0x20d3d  ldloc.3
0x20d3e  brfalse.s loc_20D7D
0x20d40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x20d45  stloc.s  4
0x20d47  ldloc.s  4
0x20d49  ldarg.2
0x20d4a  ldarg.3
0x20d4b  box      [mscorlib]System.Boolean
0x20d50  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x20d55  ldloc.0
0x20d56  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x20d5b  ldloc.2
0x20d5c  ldstr    aId// "Id"
0x20d61  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x20d66  ldloc.s  4
0x20d68  ldc.i4   0xE79
0x20d6d  ldstr    aTryupdatesyste// "TryUpdateSystemUserOrganization"
0x20d72  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x20d77  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20d7c  pop
0x20d7d  leave.s  loc_20D89
0x20d7f  ldloc.0
0x20d80  brfalse.s loc_20D88
0x20d82  ldloc.0
0x20d83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20d88  endfinally
0x20d89  ret
```
