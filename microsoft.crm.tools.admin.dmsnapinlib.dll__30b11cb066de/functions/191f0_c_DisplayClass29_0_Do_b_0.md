# <>c__DisplayClass29_0::<Do>b__0

- ea: `0x191f0`
- end: `0x1939f`
- name: `<>c__DisplayClass29_0::<Do>b__0`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5ee0`
- `0x6980`
- `0x7200`
- `0x7210`
- `0x8630`
- `0x8e30`
- `0x16cc0`
- `0x16d30`
- `0x191f0`

## string_xrefs

- `0x19344`: `InstallDynamicsSolutionsAction: `
- `0x192df`: `IsEnabledForUpdate = {0}, SkipStepForUpdate = {1}, Organization operation type = {2}`

## pseudocode

```c

```

## disassembly

```asm
0x191f0  ldarg.0
0x191f1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo> <>c__DisplayClass29_0::solutionsToProcess
0x191f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo>::GetEnumerator()
0x191fb  stloc.0
0x191fc  br       loc_19387
0x19201  ldloc.0
0x19202  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo>::get_Current()
0x19207  stloc.1
0x19208  ldarg.0
0x19209  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x1920e  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x19213  stloc.s  4
0x19215  ldloca.s 4
0x19217  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x1921c  ldarg.0
0x1921d  ldfld    bool <>c__DisplayClass29_0::isOrgUpdate
0x19222  brfalse.s loc_19241
0x19224  ldarg.0
0x19225  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x1922a  ldfld    class Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::OrgUpdateUtility
0x1922f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x19234  ldloc.1
0x19235  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x1923a  callvirt instance bool Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ShouldSkipUpdateStep(string buildVersionString, string stepName)
0x1923f  br.s     loc_19242
0x19241  ldc.i4.0
0x19242  stloc.2
0x19243  ldarg.0
0x19244  ldfld    bool <>c__DisplayClass29_0::isOrgUpdate
0x19249  brfalse.s loc_19256
0x1924b  ldloc.1
0x1924c  callvirt instance bool [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_IsEnabledForUpdate()
0x19251  ldc.i4.0
0x19252  ceq
0x19254  br.s     loc_19257
0x19256  ldc.i4.0
0x19257  stloc.3
0x19258  ldloc.2
0x19259  brtrue.s loc_192CA
0x1925b  ldloc.3
0x1925c  brtrue.s loc_192CA
0x1925e  ldarg.0
0x1925f  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x19264  ldloc.1
0x19265  ldloc.1
0x19266  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_FullFileName()
0x1926b  ldarg.0
0x1926c  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x19271  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::DoOne(class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo solutionInfo, string fileFullPathAndName, class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x19276  leave    loc_19387
0x1927b  stloc.s  5
0x1927d  ldarg.0
0x1927e  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x19283  ldc.i4.1
0x19284  call     instance void Microsoft.Crm.Tools.Admin.OrganizationAction::set_HasFailed(bool value)
0x19289  ldarg.0
0x1928a  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x1928f  call     instance bool Microsoft.Crm.Tools.Admin.OrganizationAction::get_DoNotThrowOnFailure()
0x19294  brtrue.s loc_19298
0x19296  rethrow
0x19298  ldarg.0
0x19299  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x1929e  ldstr    aIgnoringFailur// "Ignoring failure in import of {0} as Do"...
0x192a3  ldloc.1
0x192a4  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x192a9  ldarg.0
0x192aa  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x192af  call     instance bool Microsoft.Crm.Tools.Admin.OrganizationAction::get_DoNotThrowOnFailure()
0x192b4  box      [mscorlib]System.Boolean
0x192b9  call     string [mscorlib]System.String::Format(string, object, object)
0x192be  ldloc.s  5
0x192c0  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x192c5  leave    loc_19387
0x192ca  ldstr    aSkippedProcess// "Skipped processing {0} for {1}. "
0x192cf  ldloc.1
0x192d0  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x192d5  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x192da  call     string [mscorlib]System.String::Format(string, object, object)
0x192df  ldstr    aIsenabledforup// "IsEnabledForUpdate = {0}, SkipStepForUp"...
0x192e4  ldloc.1
0x192e5  callvirt instance bool [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_IsEnabledForUpdate()
0x192ea  box      [mscorlib]System.Boolean
0x192ef  ldloc.2
0x192f0  box      [mscorlib]System.Boolean
0x192f5  ldarg.0
0x192f6  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x192fb  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x19300  box      [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType
0x19305  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1930a  call     string [mscorlib]System.String::Concat(string, string)
0x1930f  stloc.s  6
0x19311  ldarg.0
0x19312  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x19317  ldloc.s  6
0x19319  ldnull
0x1931a  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x1931f  ldarg.0
0x19320  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x19325  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1932a  ldarg.0
0x1932b  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass29_0::organizationInfo
0x19330  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x19335  stloc.s  7
0x19337  ldloca.s 7
0x19339  constrained. [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType
0x1933f  callvirt instance string [mscorlib]System.Object::ToString()
0x19344  ldstr    aInstalldynamic_1// "InstallDynamicsSolutionsAction: "
0x19349  ldloc.1
0x1934a  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x1934f  call     string [mscorlib]System.String::Concat(string, string)
0x19354  ldsfld   string [mscorlib]System.String::Empty
0x19359  ldc.i4.0
0x1935a  ldsfld   string [mscorlib]System.String::Empty
0x1935f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x19364  ldc.i4.0
0x19365  conv.i8
0x19366  ldsfld   string [mscorlib]System.String::Empty
0x1936b  ldsfld   string [mscorlib]System.String::Empty
0x19370  ldsfld   string [mscorlib]System.String::Empty
0x19375  ldarg.0
0x19376  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass29_0::<>4__this
0x1937b  call     instance string Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetDatabaseVersionString()
0x19380  ldc.i4.0
0x19381  ldc.i4.1
0x19382  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmActionTelemetryHelper::OrganizationActionCompleted(valuetype [mscorlib]System.Guid, string, string, string, bool, string, string, int64, string, string, string, string, bool, bool)
0x19387  ldloc.0
0x19388  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1938d  brtrue   loc_19201
0x19392  leave.s  loc_1939E
0x19394  ldloc.0
0x19395  brfalse.s loc_1939D
0x19397  ldloc.0
0x19398  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1939d  endfinally
0x1939e  ret
```
