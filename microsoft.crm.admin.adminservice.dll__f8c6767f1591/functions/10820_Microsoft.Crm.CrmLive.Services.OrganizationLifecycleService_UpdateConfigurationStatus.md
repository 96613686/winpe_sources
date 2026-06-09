# Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::UpdateConfigurationStatus

- ea: `0x10820`
- end: `0x10892`
- name: `Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::UpdateConfigurationStatus`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x10820`

## string_xrefs

- `0x10838`: `ConfigurationStatusCode`
- `0x1087a`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10875`: `UpdateConfigurationStatus`

## pseudocode

```c

```

## disassembly

```asm
0x10820  ldarg.1
0x10821  ldstr    aOrgid// "orgId"
0x10826  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1082b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x10830  stloc.0
0x10831  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10836  stloc.1
0x10837  ldloc.1
0x10838  ldstr    aConfigurations// "ConfigurationStatusCode"
0x1083d  ldarg.2
0x1083e  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0x10843  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10848  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1084d  stloc.2
0x1084e  ldloc.2
0x1084f  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x10854  ldarg.1
0x10855  box      [mscorlib]System.Guid
0x1085a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1085f  ldloc.0
0x10860  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10865  ldloc.1
0x10866  ldc.i4.1
0x10867  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1086c  dup
0x1086d  ldc.i4.0
0x1086e  ldloc.2
0x1086f  stelem.ref
0x10870  ldc.i4   0x147
0x10875  ldstr    aUpdateconfigur// "UpdateConfigurationStatus"
0x1087a  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1087f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x10884  pop
0x10885  leave.s  loc_10891
0x10887  ldloc.0
0x10888  brfalse.s loc_10890
0x1088a  ldloc.0
0x1088b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10890  endfinally
0x10891  ret
```
