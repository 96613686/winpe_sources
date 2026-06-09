# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::UseMultiTenantPackageDeployer_0

- ea: `0x6550`
- end: `0x65e3`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::UseMultiTenantPackageDeployer_0`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x64f0`
- `0x6540`

## callees

- `0x2bb0`
- `0x6550`
- `0x65f0`
- `0x6620`
- `0x8630`
- `0x8e30`

## pseudocode

```c

```

## disassembly

```asm
0x6550  ldstr    aSingleprocessp// "SingleProcessPackageDeploy"
0x6555  ldc.i4.0
0x6556  box      [mscorlib]System.Int32
0x655b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x6560  unbox.any [mscorlib]System.Int32
0x6565  stloc.0
0x6566  ldloc.0
0x6567  ldc.i4.1
0x6568  bne.un.s loc_657C
0x656a  ldarg.0
0x656b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x6570  ldstr    aMtpddecisionDe// "[MTPDDecision] Decision = true, Reason "...
0x6575  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDTrace(valuetype [mscorlib]System.Guid organizationId, string message)
0x657a  ldc.i4.1
0x657b  ret
0x657c  ldloc.0
0x657d  ldc.i4.2
0x657e  bne.un.s loc_6592
0x6580  ldarg.0
0x6581  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x6586  ldstr    aMtpddecisionDe_0// "[MTPDDecision] Decision = false, Single"...
0x658b  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDTrace(valuetype [mscorlib]System.Guid organizationId, string message)
0x6590  ldc.i4.0
0x6591  ret
0x6592  ldarg.1
0x6593  brtrue.s loc_65A7
0x6595  ldarg.0
0x6596  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x659b  ldstr    aMtpddecisionDe_1// "[MTPDDecision] Decision = true, Reason "...
0x65a0  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDTrace(valuetype [mscorlib]System.Guid organizationId, string message)
0x65a5  ldc.i4.1
0x65a6  ret
0x65a7  ldarg.0
0x65a8  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x65ad  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetPdFcbByOrgOpType(valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType opType)
0x65b2  stloc.1
0x65b3  ldloc.1
0x65b4  call     bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::IsFcbEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail detail)
0x65b9  stloc.2
0x65ba  ldarg.0
0x65bb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x65c0  ldstr    aMtpddecisionDe_2// "[MTPDDecision] Decision = {0}, Reason ="...
0x65c5  ldloc.2
0x65c6  box      [mscorlib]System.Boolean
0x65cb  ldloc.1
0x65cc  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x65d1  ldloc.2
0x65d2  box      [mscorlib]System.Boolean
0x65d7  call     string [mscorlib]System.String::Format(string, object, object, object)
0x65dc  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDTrace(valuetype [mscorlib]System.Guid organizationId, string message)
0x65e1  ldloc.2
0x65e2  ret
```
