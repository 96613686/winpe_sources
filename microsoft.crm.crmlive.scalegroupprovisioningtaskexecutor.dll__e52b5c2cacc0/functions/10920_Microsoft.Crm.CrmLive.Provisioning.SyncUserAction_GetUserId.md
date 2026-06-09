# Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::GetUserId

- ea: `0x10920`
- end: `0x1097f`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::GetUserId`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x106c0`

## string_xrefs

- `0x10974`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SyncUserAction.cs`
- `0x10938`: `DirectoryObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x10920  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10925  stloc.0
0x10926  ldloc.0
0x10927  ldstr    aOrganizationid_0// "OrganizationId"
0x1092c  ldarg.0
0x1092d  box      [mscorlib]System.Guid
0x10932  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10937  ldloc.0
0x10938  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x1093d  ldarg.1
0x1093e  box      [mscorlib]System.Guid
0x10943  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10948  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1094d  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x10952  ldc.i4.1
0x10953  newarr   [mscorlib]System.String
0x10958  dup
0x10959  ldc.i4.0
0x1095a  ldstr    aCrmuserid// "CrmUserId"
0x1095f  stelem.ref
0x10960  ldc.i4.1
0x10961  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x10966  dup
0x10967  ldc.i4.0
0x10968  ldloc.0
0x10969  stelem.ref
0x1096a  ldc.i4   0x1A4
0x1096f  ldstr    aGetuserid// "GetUserId"
0x10974  ldstr    aDDbsShDccm2110_21// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x10979  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1097e  ret
```
