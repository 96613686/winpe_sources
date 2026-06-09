# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOrganizationCorrelationSettings

- ea: `0x8900`
- end: `0x8953`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOrganizationCorrelationSettings`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x88f0`

## callees

- `0x8900`

## pseudocode

```c

```

## disassembly

```asm
0x8900  ldc.i4.0
0x8901  stloc.0
0x8902  ldarg.0
0x8903  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8908  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x890d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailCorrelationEnabled()
0x8912  brfalse.s loc_8945
0x8914  ldloc.0
0x8915  ldc.i4.1
0x8916  or
0x8917  stloc.0
0x8918  ldarg.0
0x8919  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x891e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x8923  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaximumTrackingNumber()
0x8928  ldc.i4.0
0x8929  ble.s    loc_892F
0x892b  ldloc.0
0x892c  ldc.i4.2
0x892d  or
0x892e  stloc.0
0x892f  ldarg.0
0x8930  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8935  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x893a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableSmartMatching()
0x893f  brfalse.s loc_8945
0x8941  ldloc.0
0x8942  ldc.i4.4
0x8943  or
0x8944  stloc.0
0x8945  ldarg.1
0x8946  ldc.i4   0x255
0x894b  ldloc.0
0x894c  conv.u1
0x894d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8952  ret
```
