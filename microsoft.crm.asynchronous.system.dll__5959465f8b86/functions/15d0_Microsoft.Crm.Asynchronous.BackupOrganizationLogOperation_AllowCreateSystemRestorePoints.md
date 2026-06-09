# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::AllowCreateSystemRestorePoints

- ea: `0x15d0`
- end: `0x16d4`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::AllowCreateSystemRestorePoints`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x15c0`
- `0x15d0`

## string_xrefs

- `0x1611`: `Organization {0} is not in healthy state. The OrganizationLifecycleStatus is {1}, the OrganizationLifecycleConfigurationStatus is {2}`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  call     bool Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::IsSystemRestorePointsFeatureEnabled()
0x15d5  brtrue.s loc_15D9
0x15d7  ldc.i4.0
0x15d8  ret
0x15d9  ldc.i4.0
0x15da  stloc.0
0x15db  ldstr    aGetOrganizatio// "Get organization lifecycle"
0x15e0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0x15e5  stloc.1
0x15e6  ldloc.1
0x15e7  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext)
0x15ec  ldarg.0
0x15ed  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetOrganizationLifecycle(valuetype [mscorlib]System.Guid)
0x15f2  stloc.2
0x15f3  ldloc.2
0x15f4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::get_ConfigurationState()
0x15f9  ldc.i4.4
0x15fa  bne.un.s loc_1607
0x15fc  ldloc.2
0x15fd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::get_OrganizationLifecycleState()
0x1602  ldc.i4.7
0x1603  ceq
0x1605  br.s     loc_1608
0x1607  ldc.i4.0
0x1608  stloc.0
0x1609  ldloc.0
0x160a  brtrue.s loc_167C
0x160c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1611  ldstr    aOrganization0I// "Organization {0} is not in healthy stat"...
0x1616  ldc.i4.3
0x1617  newarr   [mscorlib]System.Object
0x161c  dup
0x161d  ldc.i4.0
0x161e  ldarg.0
0x161f  box      [mscorlib]System.Guid
0x1624  stelem.ref
0x1625  dup
0x1626  ldc.i4.1
0x1627  ldtoken  [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0x162c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1631  ldloc.2
0x1632  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::get_OrganizationLifecycleState()
0x1637  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0x163c  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x1641  stelem.ref
0x1642  dup
0x1643  ldc.i4.2
0x1644  ldtoken  [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0x1649  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x164e  ldloc.2
0x164f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::get_ConfigurationState()
0x1654  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0x1659  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x165e  stelem.ref
0x165f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1664  stloc.3
0x1665  ldarg.0
0x1666  ldc.i4.s 0x15
0x1668  ldstr    a0// "{0}"
0x166d  ldc.i4.1
0x166e  newarr   [mscorlib]System.Object
0x1673  dup
0x1674  ldc.i4.0
0x1675  ldloc.3
0x1676  stelem.ref
0x1677  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x167c  leave.s  loc_1688
0x167e  ldloc.1
0x167f  brfalse.s loc_1687
0x1681  ldloc.1
0x1682  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1687  endfinally
0x1688  leave.s  loc_16D2
0x168a  stloc.s  4
0x168c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1691  ldstr    aCanTGetOlcData// "Can't get OLC data for organization {0}"...
0x1696  ldc.i4.2
0x1697  newarr   [mscorlib]System.Object
0x169c  dup
0x169d  ldc.i4.0
0x169e  ldarg.0
0x169f  box      [mscorlib]System.Guid
0x16a4  stelem.ref
0x16a5  dup
0x16a6  ldc.i4.1
0x16a7  ldloc.s  4
0x16a9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16ae  stelem.ref
0x16af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16b4  stloc.s  5
0x16b6  ldloc.s  4
0x16b8  ldarg.0
0x16b9  ldc.i4.s 0x15
0x16bb  ldstr    a0// "{0}"
0x16c0  ldc.i4.1
0x16c1  newarr   [mscorlib]System.Object
0x16c6  dup
0x16c7  ldc.i4.0
0x16c8  ldloc.s  5
0x16ca  stelem.ref
0x16cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16d0  rethrow
0x16d2  ldloc.0
0x16d3  ret
```
