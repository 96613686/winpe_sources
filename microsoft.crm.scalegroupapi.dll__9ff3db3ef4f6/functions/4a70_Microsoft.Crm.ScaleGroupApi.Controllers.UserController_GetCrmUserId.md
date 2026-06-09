# Microsoft.Crm.ScaleGroupApi.Controllers.UserController::GetCrmUserId

- ea: `0x4a70`
- end: `0x4aea`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.UserController::GetCrmUserId`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3dd0`
- `0x42e0`
- `0x4a10`

## callees

- `0x4a70`

## string_xrefs

- `0x4a88`: `DirectoryObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x4a70  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x4a75  stloc.0
0x4a76  ldloc.0
0x4a77  ldstr    aOrganizationid_0// "OrganizationId"
0x4a7c  ldarg.0
0x4a7d  box      [mscorlib]System.Guid
0x4a82  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4a87  ldloc.0
0x4a88  ldstr    aDirectoryobjec_0// "DirectoryObjectId"
0x4a8d  ldarg.1
0x4a8e  box      [mscorlib]System.Guid
0x4a93  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4a98  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4a9d  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x4aa2  ldc.i4.1
0x4aa3  newarr   [mscorlib]System.String
0x4aa8  dup
0x4aa9  ldc.i4.0
0x4aaa  ldstr    aCrmuserid// "CrmUserId"
0x4aaf  stelem.ref
0x4ab0  ldloc.0
0x4ab1  ldc.i4.s 0x5A
0x4ab3  ldstr    aGetcrmuserid// "GetCrmUserId"
0x4ab8  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x4abd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x4ac2  stloc.1
0x4ac3  ldloc.1
0x4ac4  brfalse.s loc_4AD3
0x4ac6  ldloc.1
0x4ac7  ldstr    aCrmuserid// "CrmUserId"
0x4acc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4ad1  brtrue.s loc_4AD9
0x4ad3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ad8  ret
0x4ad9  ldloc.1
0x4ada  ldstr    aCrmuserid// "CrmUserId"
0x4adf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4ae4  unbox.any [mscorlib]System.Guid
0x4ae9  ret
```
