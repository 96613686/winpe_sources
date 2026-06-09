# Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::GetCrmUserId

- ea: `0x4f50`
- end: `0x4fca`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::GetCrmUserId`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4e70`

## callees

- `0x4f50`

## string_xrefs

- `0x4f68`: `DirectoryObjectId`
- `0x4f98`: `d:\dbs\sh\dccm2\1101_190851\cmd\30\src\CrmLive\ScaleGroupApi\Controllers\UserSecurityRoleController.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4f50  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x4f55  stloc.0
0x4f56  ldloc.0
0x4f57  ldstr    aOrganizationid_0// "OrganizationId"
0x4f5c  ldarg.0
0x4f5d  box      [mscorlib]System.Guid
0x4f62  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f67  ldloc.0
0x4f68  ldstr    aDirectoryobjec_0// "DirectoryObjectId"
0x4f6d  ldarg.1
0x4f6e  box      [mscorlib]System.Guid
0x4f73  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4f78  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4f7d  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x4f82  ldc.i4.1
0x4f83  newarr   [mscorlib]System.String
0x4f88  dup
0x4f89  ldc.i4.0
0x4f8a  ldstr    aCrmuserid// "CrmUserId"
0x4f8f  stelem.ref
0x4f90  ldloc.0
0x4f91  ldc.i4.s 0x51
0x4f93  ldstr    aGetcrmuserid// "GetCrmUserId"
0x4f98  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x4f9d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x4fa2  stloc.1
0x4fa3  ldloc.1
0x4fa4  brfalse.s loc_4FB3
0x4fa6  ldloc.1
0x4fa7  ldstr    aCrmuserid// "CrmUserId"
0x4fac  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4fb1  brtrue.s loc_4FB9
0x4fb3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4fb8  ret
0x4fb9  ldloc.1
0x4fba  ldstr    aCrmuserid// "CrmUserId"
0x4fbf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4fc4  unbox.any [mscorlib]System.Guid
0x4fc9  ret
```
