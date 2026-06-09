# Microsoft.Crm.Admin.AdminService.ProvisioningAffinityGroupService::Create

- ea: `0x34900`
- end: `0x3498b`
- name: `Microsoft.Crm.Admin.AdminService.ProvisioningAffinityGroupService::Create`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x34900`
- `0x34b10`

## string_xrefs

- `0x34968`: `Create`
- `0x34913`: `Affinity group with the same name already exists.`
- `0x3496d`: `D:\a\1\s\src\CrmLive\Admin\ProvisioningAffinity\ProvisioningAffinityGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x34900  ldarg.1
0x34901  ldstr    aName_0// "name"
0x34906  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3490b  ldarg.1
0x3490c  call     bool Microsoft.Crm.Admin.AdminService.ProvisioningAffinityGroupService::DoesAffinityExist(string name)
0x34911  brfalse.s loc_3491E
0x34913  ldstr    aAffinityGroupW// "Affinity group with the same name alrea"...
0x34918  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3491d  throw
0x3491e  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x34923  stloc.0
0x34924  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34929  stloc.1
0x3492a  ldloc.1
0x3492b  ldstr    aId// "Id"
0x34930  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x34935  box      [mscorlib]System.Guid
0x3493a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3493f  ldloc.1
0x34940  ldstr    aName// "Name"
0x34945  ldarg.1
0x34946  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3494b  ldarg.2
0x3494c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x34951  brtrue.s loc_3495F
0x34953  ldloc.1
0x34954  ldstr    aDescription// "Description"
0x34959  ldarg.2
0x3495a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3495f  ldloc.0
0x34960  ldstr    aProvisioningaf_2// "ProvisioningAffinityGroup"
0x34965  ldloc.1
0x34966  ldc.i4.s 0x2E
0x34968  ldstr    aCreate// "Create"
0x3496d  ldstr    aDA1SSrcCrmlive_61// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Provi"...
0x34972  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x34977  unbox.any [mscorlib]System.Guid
0x3497c  stloc.2
0x3497d  leave.s  loc_34989
0x3497f  ldloc.0
0x34980  brfalse.s loc_34988
0x34982  ldloc.0
0x34983  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34988  endfinally
0x34989  ldloc.2
0x3498a  ret
```
