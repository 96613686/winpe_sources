# Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::UninstallOptinIfPresent

- ea: `0xe590`
- end: `0xe699`
- name: `Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::UninstallOptinIfPresent`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xe3e0`

## callees

- `0x8e30`
- `0xe590`
- `0xe830`

## string_xrefs

- `0xe599`: `December2012ProductUpdate`
- `0xe5d4`: `December2012ProductUpdate`
- `0xe5a9`: `ServiceEnhancements610`
- `0xe5db`: `ServiceEnhancements610`

## pseudocode

```c

```

## disassembly

```asm
0xe590  ldc.i4.0
0xe591  stloc.0
0xe592  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningSolutionService::.ctor()
0xe597  stloc.1
0xe598  ldloc.1
0xe599  ldstr    aDecember2012pr// "December2012ProductUpdate"
0xe59e  ldarg.1
0xe59f  callvirt instance valuetype [mscorlib]System.Guid class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrieveSolutionId(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe5a4  pop
0xe5a5  leave.s  loc_E5C1
0xe5a7  pop
0xe5a8  ldloc.1
0xe5a9  ldstr    aServiceenhance// "ServiceEnhancements610"
0xe5ae  ldarg.1
0xe5af  callvirt instance valuetype [mscorlib]System.Guid class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrieveSolutionId(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe5b4  pop
0xe5b5  ldc.i4.1
0xe5b6  stloc.0
0xe5b7  leave.s  loc_E5BF
0xe5b9  pop
0xe5ba  leave    loc_E698
0xe5bf  leave.s  loc_E5C1
0xe5c1  ldloc.0
0xe5c2  brtrue.s loc_E5CB
0xe5c4  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.OptInSolutionConstants::Fall12OptInSolutionId
0xe5c9  br.s     loc_E5D0
0xe5cb  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.OptInSolutionConstants::LeoOptInSolutionId
0xe5d0  stloc.2
0xe5d1  ldloc.0
0xe5d2  brtrue.s loc_E5DB
0xe5d4  ldstr    aDecember2012pr// "December2012ProductUpdate"
0xe5d9  br.s     loc_E5E0
0xe5db  ldstr    aServiceenhance// "ServiceEnhancements610"
0xe5e0  stloc.3
0xe5e1  ldarg.1
0xe5e2  ldloc.2
0xe5e3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoOptInUninstallOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid)
0xe5e8  stloc.s  4
0xe5ea  ldarg.1
0xe5eb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe5f0  stloc.s  5
0xe5f2  ldc.i4.4
0xe5f3  ldarg.0
0xe5f4  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::organizationInfo
0xe5f9  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0xe5fe  beq.s    loc_E603
0xe600  ldc.i4.0
0xe601  br.s     loc_E604
0xe603  ldc.i4.1
0xe604  dup
0xe605  brfalse.s loc_E62F
0xe607  ldarg.1
0xe608  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xe60d  ldstr    aUpgradeaction// "UpgradeAction"
0xe612  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xe617  brtrue.s loc_E62F
0xe619  ldarg.1
0xe61a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xe61f  ldstr    aUpgradeaction// "UpgradeAction"
0xe624  ldc.i4.1
0xe625  box      [mscorlib]System.Boolean
0xe62a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xe62f  ldloc.1
0xe630  ldloc.2
0xe631  ldstr    aSolution// "Solution"
0xe636  ldarg.1
0xe637  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe63c  ldarg.1
0xe63d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe642  brfalse.s loc_E667
0xe644  ldarg.1
0xe645  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xe64a  ldstr    aUpgradeaction// "UpgradeAction"
0xe64f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xe654  brfalse.s loc_E667
0xe656  ldarg.1
0xe657  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xe65c  ldstr    aUpgradeaction// "UpgradeAction"
0xe661  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0xe666  pop
0xe667  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0xe66c  ldarg.1
0xe66d  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe672  ldarg.1
0xe673  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe678  ldloc.3
0xe679  call     void Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::SetOptInSolutionInfo(valuetype [mscorlib]System.Guid organizationId, string solutionName)
0xe67e  leave.s  loc_E698
0xe680  ldloc.s  5
0xe682  brfalse.s loc_E68B
0xe684  ldloc.s  5
0xe686  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe68b  endfinally
0xe68c  ldloc.s  4
0xe68e  brfalse.s loc_E697
0xe690  ldloc.s  4
0xe692  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe697  endfinally
0xe698  ret
```
