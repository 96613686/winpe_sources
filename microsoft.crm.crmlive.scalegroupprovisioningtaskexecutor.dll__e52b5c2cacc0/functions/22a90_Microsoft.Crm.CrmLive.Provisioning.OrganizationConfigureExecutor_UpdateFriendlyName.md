# Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::UpdateFriendlyName

- ea: `0x22a90`
- end: `0x22b1d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::UpdateFriendlyName`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x22740`

## callees

- `0x22a90`

## string_xrefs

- `0x22ac2`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationConfigureExecutor.cs`
- `0x22b11`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationConfigureExecutor.cs`
- `0x22abd`: `UpdateFriendlyName`
- `0x22b0c`: `UpdateFriendlyName`

## pseudocode

```c

```

## disassembly

```asm
0x22a90  ldarg.2
0x22a91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22a96  brfalse.s loc_22A99
0x22a98  ret
0x22a99  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x22a9e  stloc.0
0x22a9f  ldloc.0
0x22aa0  ldstr    aFriendlyname// "FriendlyName"
0x22aa5  ldarg.2
0x22aa6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22aab  ldarg.0
0x22aac  ldstr    aOrganization// "Organization"
0x22ab1  ldarg.1
0x22ab2  box      [mscorlib]System.Guid
0x22ab7  ldloc.0
0x22ab8  ldc.i4   0xF0
0x22abd  ldstr    aUpdatefriendly// "UpdateFriendlyName"
0x22ac2  ldstr    aDDbsShDccm2110_35// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x22ac7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x22acc  pop
0x22acd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x22ad2  stloc.0
0x22ad3  ldloc.0
0x22ad4  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0x22ad9  ldarg.2
0x22ada  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22adf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x22ae4  stloc.1
0x22ae5  ldloc.1
0x22ae6  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x22aeb  ldarg.1
0x22aec  box      [mscorlib]System.Guid
0x22af1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22af6  ldarg.0
0x22af7  ldstr    aOrganizationli// "OrganizationLifecycle"
0x22afc  ldloc.0
0x22afd  ldc.i4.1
0x22afe  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x22b03  dup
0x22b04  ldc.i4.0
0x22b05  ldloc.1
0x22b06  stelem.ref
0x22b07  ldc.i4   0xF7
0x22b0c  ldstr    aUpdatefriendly// "UpdateFriendlyName"
0x22b11  ldstr    aDDbsShDccm2110_35// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x22b16  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x22b1b  pop
0x22b1c  ret
```
