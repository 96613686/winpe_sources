# Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForDatabaseUpdate

- ea: `0xd8c0`
- end: `0xd91d`
- name: `Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForDatabaseUpdate`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17060`

## callees

- `0x72a0`
- `0xd8c0`
- `0xd920`
- `0xd960`
- `0xd9f0`
- `0xda00`
- `0xda20`
- `0xdbe0`
- `0xdd40`
- `0x10e20`

## pseudocode

```c

```

## disassembly

```asm
0xd8c0  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationActionCollection::.ctor()
0xd8c5  stloc.0
0xd8c6  ldloc.0
0xd8c7  ldarg.0
0xd8c8  ldc.i4.2
0xd8c9  ldc.i4.0
0xd8ca  newobj   instance void Microsoft.Crm.Tools.Admin.SetOrganizationDatabaseStateAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationStates state, int32 nominalProgressWeighting)
0xd8cf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd8d4  ldarg.1
0xd8d5  call     bool Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::ShouldRunPlatformUpdates(valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode mode)
0xd8da  brfalse.s loc_D8E4
0xd8dc  ldloc.0
0xd8dd  ldarg.0
0xd8de  call     class Microsoft.Crm.Tools.Admin.OrganizationActionCollection Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForPlatformUpdate(class Microsoft.Crm.Tools.Admin.OrganizationActionCollection businessProvisioningActions, class Microsoft.Crm.Tools.Admin.OrganizationOperation operation)
0xd8e3  stloc.0
0xd8e4  ldarg.1
0xd8e5  call     bool Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::ShouldRunSolutionUpdates(valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode mode)
0xd8ea  brfalse.s loc_D8F4
0xd8ec  ldloc.0
0xd8ed  ldarg.0
0xd8ee  call     class Microsoft.Crm.Tools.Admin.OrganizationActionCollection Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForSolutionsUpdate(class Microsoft.Crm.Tools.Admin.OrganizationActionCollection businessProvisioningActions, class Microsoft.Crm.Tools.Admin.OrganizationOperation operation)
0xd8f3  stloc.0
0xd8f4  ldloc.0
0xd8f5  ldarg.0
0xd8f6  ldc.i4.0
0xd8f7  newobj   instance void Microsoft.Crm.Tools.Admin.FlushPluginAssemblyCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd8fc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd901  ldloc.0
0xd902  ldarg.0
0xd903  ldc.i4.0
0xd904  newobj   instance void Microsoft.Crm.Tools.Admin.EnableSharedCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd909  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd90e  ldloc.0
0xd90f  ldarg.0
0xd910  ldc.i4.0
0xd911  newobj   instance void Microsoft.Crm.Tools.Admin.EnableLabelCacheSharingAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd916  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd91b  ldloc.0
0xd91c  ret
```
