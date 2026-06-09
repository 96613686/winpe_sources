# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteConfigDBUpdates

- ea: `0x28600`
- end: `0x2867e`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteConfigDBUpdates`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x28560`

## callees

- `0x28600`

## string_xrefs

- `0x28620`: `{0} DBUpdates failed for scalegroup {1}. Exception details: {2}.`
- `0x28654`: `{0} DBUpdates succeeded for scalegroup {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x28600  ldarg.0
0x28601  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_Uninstall()
0x28606  brfalse.s loc_28610
0x28608  ldc.i4.4
0x28609  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyConfigDBUpdatesForUninstall(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x2860e  br.s     loc_28616
0x28610  ldc.i4.4
0x28611  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyConfigDBUpdates(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x28616  leave.s  loc_2864E
0x28618  stloc.0
0x28619  ldc.i4.s 0xB
0x2861b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28620  ldstr    a0DbupdatesFail// "{0} DBUpdates failed for scalegroup {1}"...
0x28625  ldc.i4.3
0x28626  newarr   [mscorlib]System.Object
0x2862b  dup
0x2862c  ldc.i4.0
0x2862d  ldarg.0
0x2862e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_DatabaseType()
0x28633  stelem.ref
0x28634  dup
0x28635  ldc.i4.1
0x28636  ldarg.0
0x28637  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_ScaleGroupName()
0x2863c  stelem.ref
0x2863d  dup
0x2863e  ldc.i4.2
0x2863f  ldloc.0
0x28640  stelem.ref
0x28641  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28646  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2864b  stloc.1
0x2864c  leave.s  loc_2867C
0x2864e  ldc.i4.4
0x2864f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28654  ldstr    a0DbupdatesSucc// "{0} DBUpdates succeeded for scalegroup "...
0x28659  ldc.i4.2
0x2865a  newarr   [mscorlib]System.Object
0x2865f  dup
0x28660  ldc.i4.0
0x28661  ldarg.0
0x28662  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_DatabaseType()
0x28667  stelem.ref
0x28668  dup
0x28669  ldc.i4.1
0x2866a  ldarg.0
0x2866b  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_ScaleGroupName()
0x28670  stelem.ref
0x28671  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28676  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2867b  ret
0x2867c  ldloc.1
0x2867d  ret
```
