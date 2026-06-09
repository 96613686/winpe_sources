# Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::CalculateTriggerAndProvisioningTime

- ea: `0x2c8f0`
- end: `0x2c9eb`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::CalculateTriggerAndProvisioningTime`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2c6c0`

## callees

- `0xff70`
- `0x2c860`
- `0x2c8f0`

## string_xrefs

- `0x2c90f`: `SecurityGroupUpdated`
- `0x2c99b`: `OrganizationCreated`

## pseudocode

```c

```

## disassembly

```asm
0x2c8f0  ldarg.s  6
0x2c8f2  ldstr    asc_361CC// ""
0x2c8f7  stind.ref
0x2c8f8  ldarg.s  7
0x2c8fa  ldc.r8   -1.0
0x2c903  stind.r8
0x2c904  ldarg.3
0x2c905  callvirt instance valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningTrigger [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::get_Trigger()
0x2c90a  ldc.i4.1
0x2c90b  bne.un.s loc_2C949
0x2c90d  ldarg.s  6
0x2c90f  ldstr    aSecuritygroupu// "SecurityGroupUpdated"
0x2c914  stind.ref
0x2c915  ldarg.3
0x2c916  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::get_TriggeredOn()
0x2c91b  stloc.0
0x2c91c  ldloca.s 0
0x2c91e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x2c923  brfalse  loc_2C9EA
0x2c928  ldarg.s  7
0x2c92a  ldarg.s  4
0x2c92c  ldarg.3
0x2c92d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::get_TriggeredOn()
0x2c932  stloc.0
0x2c933  ldloca.s 0
0x2c935  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2c93a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2c93f  stloc.1
0x2c940  ldloca.s 1
0x2c942  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2c947  stind.r8
0x2c948  ret
0x2c949  ldarg.0
0x2c94a  ldc.i4.1
0x2c94b  bne.un   loc_2C9EA
0x2c950  ldarg.1
0x2c951  brfalse  loc_2C9EA
0x2c956  ldarg.1
0x2c957  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x2c95c  brfalse  loc_2C9EA
0x2c961  ldarg.1
0x2c962  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x2c967  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AssignedPlan()
0x2c96c  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetUserAssignedPlanTimeStamp(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan assignedPlan)
0x2c971  stloc.2
0x2c972  ldarga.s 2
0x2c974  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x2c979  brfalse.s loc_2C9DD
0x2c97b  ldloca.s 2
0x2c97d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x2c982  brfalse.s loc_2C9DD
0x2c984  ldarga.s 2
0x2c986  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2c98b  ldloca.s 2
0x2c98d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2c992  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2c997  brfalse.s loc_2C9BC
0x2c999  ldarg.s  6
0x2c99b  ldstr    aOrganizationcr// "OrganizationCreated"
0x2c9a0  stind.ref
0x2c9a1  ldarg.s  7
0x2c9a3  ldarg.s  4
0x2c9a5  ldarga.s 2
0x2c9a7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2c9ac  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2c9b1  stloc.1
0x2c9b2  ldloca.s 1
0x2c9b4  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2c9b9  stind.r8
0x2c9ba  br.s     loc_2C9DD
0x2c9bc  ldarg.s  6
0x2c9be  ldstr    aUserlicensed// "UserLicensed"
0x2c9c3  stind.ref
0x2c9c4  ldarg.s  7
0x2c9c6  ldarg.s  4
0x2c9c8  ldloca.s 2
0x2c9ca  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x2c9cf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2c9d4  stloc.1
0x2c9d5  ldloca.s 1
0x2c9d7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2c9dc  stind.r8
0x2c9dd  ldarg.s  5
0x2c9df  ldc.i4.4
0x2c9e0  bne.un.s loc_2C9EA
0x2c9e2  ldarg.s  6
0x2c9e4  ldstr    aUsersignin// "UserSignIn"
0x2c9e9  stind.ref
0x2c9ea  ret
```
