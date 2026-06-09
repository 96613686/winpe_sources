# Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::Execute

- ea: `0x17070`
- end: `0x171e0`
- name: `Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::Execute`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callees

- `0x24f0`
- `0x2510`
- `0x2530`
- `0x2550`
- `0x2570`
- `0x2590`
- `0x25a0`
- `0x25e0`
- `0x2b60`
- `0x7640`
- `0x7ca0`
- `0x8600`
- `0x9870`
- `0x9d30`
- `0x9e50`
- `0x141c0`
- `0x141d0`
- `0x17040`
- `0x17050`
- `0x17070`
- `0x171e0`

## string_xrefs

- `0x170cb`: `Failed to enable org after update. Org could be in disabled state.`
- `0x1719f`: `databaseupdated`

## pseudocode

```c

```

## disassembly

```asm
0x17070  ldc.i4.0
0x17071  stloc.0
0x17072  ldnull
0x17073  stloc.s  4
0x17075  call     class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.DBImportHelper::GetVersionInstalled()
0x1707a  stloc.2
0x1707b  ldarg.0
0x1707c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x17081  call     class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.DBImportHelper::GetExistingDBVersion(valuetype [mscorlib]System.Guid OrganizationId)
0x17086  stloc.1
0x17087  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x1708c  stloc.s  5
0x1708e  ldc.i4.0
0x1708f  conv.i8
0x17090  stloc.s  6
0x17092  ldloc.s  5
0x17094  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x17099  ldarg.0
0x1709a  call     instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x1709f  ldarg.0
0x170a0  call     instance void Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::ProcessFailedActions()
0x170a5  leave    loc_171DF
0x170aa  ldc.i4.1
0x170ab  stloc.0
0x170ac  stloc.s  4
0x170ae  rethrow
0x170b0  nop
0x170b1  call     class Microsoft.Crm.Tools.Admin.OrganizationController Microsoft.Crm.Tools.Admin.OrganizationController::get_Instance()
0x170b6  ldarg.0
0x170b7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x170bc  ldc.i4.1
0x170bd  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationController::SetState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState organizationState)
0x170c2  leave.s  loc_170DD
0x170c4  ldarg.0
0x170c5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x170ca  ldc.i4.3
0x170cb  ldstr    aFailedToEnable// "Failed to enable org after update. Org "...
0x170d0  ldc.i4.0
0x170d1  newarr   [mscorlib]System.Object
0x170d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x170db  leave.s  loc_170DD
0x170dd  ldloc.s  5
0x170df  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x170e4  ldloc.s  5
0x170e6  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x170eb  ldc.i4   0x3E8
0x170f0  conv.i8
0x170f1  div
0x170f2  stloc.s  6
0x170f4  ldarg.0
0x170f5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x170fa  call     class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.DBImportHelper::GetExistingDBVersion(valuetype [mscorlib]System.Guid OrganizationId)
0x170ff  stloc.3
0x17100  ldarg.0
0x17101  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x17106  ldloc.1
0x17107  ldnull
0x17108  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1710d  brtrue.s loc_17116
0x1710f  ldstr    aNull// "Null"
0x17114  br.s     loc_1711C
0x17116  ldloc.1
0x17117  callvirt instance string [mscorlib]System.Object::ToString()
0x1711c  ldloc.2
0x1711d  ldnull
0x1711e  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x17123  brtrue.s loc_1712C
0x17125  ldstr    aNull// "Null"
0x1712a  br.s     loc_17132
0x1712c  ldloc.2
0x1712d  callvirt instance string [mscorlib]System.Object::ToString()
0x17132  ldloc.3
0x17133  ldnull
0x17134  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x17139  brtrue.s loc_17142
0x1713b  ldstr    aNull// "Null"
0x17140  br.s     loc_17148
0x17142  ldloc.3
0x17143  callvirt instance string [mscorlib]System.Object::ToString()
0x17148  ldloc.0
0x17149  ldc.i4.0
0x1714a  ceq
0x1714c  ldloc.s  4
0x1714e  brtrue.s loc_17157
0x17150  ldstr    aNull// "Null"
0x17155  br.s     loc_17163
0x17157  ldloc.s  4
0x17159  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1715e  callvirt instance string [mscorlib]System.Object::ToString()
0x17163  ldloc.s  4
0x17165  brtrue.s loc_1716E
0x17167  ldstr    aNull// "Null"
0x1716c  br.s     loc_17175
0x1716e  ldloc.s  4
0x17170  callvirt instance string [mscorlib]System.Object::ToString()
0x17175  ldloc.s  6
0x17177  ldarg.0
0x17178  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x1717d  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0x17182  ldarg.0
0x17183  call     instance valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::get_Mode()
0x17188  ldarg.0
0x17189  call     instance valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::get_Source()
0x1718e  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::AppliedOrganizationDBUpdate(valuetype [mscorlib]System.Guid organizationId, string beforeDBVersion, string installDBVersion, string afterDBVersion, bool result, string errorMessage, string exception, int64 timeTaken, bool isXrmOrg, valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode dbUpdateMode, valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource dbUpdateSource)
0x17193  ldarg.0
0x17194  call     instance class Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrgLifecycleDataSyncNotificationService()
0x17199  newobj   instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::.ctor()
0x1719e  dup
0x1719f  ldstr    aDatabaseupdate// "databaseupdated"
0x171a4  stfld    string Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::Name
0x171a9  dup
0x171aa  ldarg.0
0x171ab  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::_organizationId
0x171b0  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x171b5  dup
0x171b6  ldloc.s  6
0x171b8  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_TimeTakenInSeconds(int64 value)
0x171bd  dup
0x171be  ldloc.1
0x171bf  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_BeforeDbVersion(class [mscorlib]System.Version value)
0x171c4  dup
0x171c5  ldloc.2
0x171c6  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_InstallDbVersion(class [mscorlib]System.Version value)
0x171cb  dup
0x171cc  ldloc.3
0x171cd  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_AfterDbVersion(class [mscorlib]System.Version value)
0x171d2  dup
0x171d3  ldloc.0
0x171d4  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_HasFailed(bool value)
0x171d9  callvirt instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService::SendNotification(class Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification notification)
0x171de  endfinally
0x171df  ret
```
