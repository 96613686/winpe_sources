# Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserOrganizations

- ea: `0x35b30`
- end: `0x35bae`
- name: `Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserOrganizations`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x35a20`

## string_xrefs

- `0x35ba2`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35b7f`: `DirectoryObjectId`
- `0x35b9d`: `CreateSystemUserOrganizations`

## pseudocode

```c

```

## disassembly

```asm
0x35b30  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35b35  stloc.0
0x35b36  ldloc.0
0x35b37  ldstr    aId// "Id"
0x35b3c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x35b41  box      [mscorlib]System.Guid
0x35b46  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b4b  ldloc.0
0x35b4c  ldstr    aUserid// "UserId"
0x35b51  ldarg.3
0x35b52  box      [mscorlib]System.Guid
0x35b57  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b5c  ldloc.0
0x35b5d  ldstr    aCrmuserid// "CrmUserId"
0x35b62  ldarg.1
0x35b63  box      [mscorlib]System.Guid
0x35b68  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b6d  ldloc.0
0x35b6e  ldstr    aOrganizationid_0// "OrganizationId"
0x35b73  ldarg.0
0x35b74  box      [mscorlib]System.Guid
0x35b79  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b7e  ldloc.0
0x35b7f  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x35b84  ldarg.2
0x35b85  box      [mscorlib]System.Guid
0x35b8a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b8f  ldarg.s  4
0x35b91  ldc.i4.0
0x35b92  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x35b97  ldloc.0
0x35b98  ldc.i4   0x219
0x35b9d  ldstr    aCreatesystemus// "CreateSystemUserOrganizations"
0x35ba2  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35ba7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(bool, string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x35bac  pop
0x35bad  ret
```
