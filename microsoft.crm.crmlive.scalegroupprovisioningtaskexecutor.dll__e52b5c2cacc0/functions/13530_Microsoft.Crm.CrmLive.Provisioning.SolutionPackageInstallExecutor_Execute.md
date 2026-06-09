# Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::Execute

- ea: `0x13530`
- end: `0x136d2`
- name: `Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::Execute`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x13530`
- `0x136e0`
- `0x136f0`
- `0x13700`
- `0x13710`

## string_xrefs

- `0x13561`: `[SolutionPackageInstall]: Executing SolutionPackageInstall for org with id = {0} and name = {1}.`
- `0x135a5`: `[SolutionPackageInstall]: Executing ImportAction for org with id = {0} and name = {1}. PackageListXmlFile = {2}, PackageBasePath = {3}`
- `0x135ec`: `[SolutionPackageInstall]: Successfully executed ImportAction for org with id = {0} and name = {1}.`
- `0x13619`: `Solution Package install succeeded for organization: Id = {0}, uniqueName = {1}.`
- `0x13642`: `[SolutionPackageInstall]: Org name is null or empty. Not executing SolutionPackageInstall.`
- `0x13653`: `Solution Package install did not execute for organization: Id = {0}, uniqueName = {1}.`
- `0x1367b`: `[SolutionPackageInstall]: SolutionPackageInstall execution failed for org with id = {0} and name = {1}. Error: {2}`
- `0x136a4`: `Solution Package install failed for organization: Id = {0}, uniqueName = {1}. Exception details: {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x13530  ldarg.1
0x13531  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13536  stloc.0
0x13537  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1353c  stloc.1
0x1353d  ldstr    aUnknown// "Unknown"
0x13542  stloc.2
0x13543  ldarg.0
0x13544  ldloc.0
0x13545  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x1354a  call     instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallRuntimeData Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::GetSolutionPackageInstallItemInfo(string itemData)
0x1354f  stloc.3
0x13550  ldloc.3
0x13551  brfalse.s loc_1357E
0x13553  ldloc.3
0x13554  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallRuntimeData::get_OrganizationNewId()
0x13559  stloc.1
0x1355a  ldloc.3
0x1355b  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallRuntimeData::get_OrganizationNewUniqueName()
0x13560  stloc.2
0x13561  ldstr    aSolutionpackag// "[SolutionPackageInstall]: Executing Sol"...
0x13566  ldc.i4.2
0x13567  newarr   [mscorlib]System.Object
0x1356c  dup
0x1356d  ldc.i4.0
0x1356e  ldloc.1
0x1356f  box      [mscorlib]System.Guid
0x13574  stelem.ref
0x13575  dup
0x13576  ldc.i4.1
0x13577  ldloc.2
0x13578  stelem.ref
0x13579  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1357e  ldloc.2
0x1357f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13584  brtrue   loc_13642
0x13589  ldarg.0
0x1358a  call     instance string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::GetActionsDirectoryPath()
0x1358f  stloc.s  4
0x13591  ldarg.0
0x13592  ldloc.s  4
0x13594  call     instance string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::GetSolutionPackageXmlListFile(string actionFileDirectoryPath)
0x13599  stloc.s  5
0x1359b  ldarg.0
0x1359c  ldloc.s  4
0x1359e  call     instance string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageInstallExecutor::GetSolutionPackageBasePath(string actionFileDirectoryPath)
0x135a3  stloc.s  6
0x135a5  ldstr    aSolutionpackag_0// "[SolutionPackageInstall]: Executing Imp"...
0x135aa  ldc.i4.4
0x135ab  newarr   [mscorlib]System.Object
0x135b0  dup
0x135b1  ldc.i4.0
0x135b2  ldloc.1
0x135b3  box      [mscorlib]System.Guid
0x135b8  stelem.ref
0x135b9  dup
0x135ba  ldc.i4.1
0x135bb  ldloc.2
0x135bc  stelem.ref
0x135bd  dup
0x135be  ldc.i4.2
0x135bf  ldloc.s  5
0x135c1  stelem.ref
0x135c2  dup
0x135c3  ldc.i4.3
0x135c4  ldloc.s  6
0x135c6  stelem.ref
0x135c7  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x135cc  ldloc.s  5
0x135ce  ldloc.s  6
0x135d0  ldloc.2
0x135d1  ldnull
0x135d2  ldloca.s 1
0x135d4  constrained. [mscorlib]System.Guid
0x135da  callvirt instance string [mscorlib]System.Object::ToString()
0x135df  ldnull
0x135e0  ldnull
0x135e1  newobj   instance void [Microsoft.Xrm.Tools.SolutionPackageWrapper]Microsoft.Xrm.Tools.SolutionPackageWrapper.ImportAction::.ctor(string, string, string, string, string, string, string)
0x135e6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Tools.SolutionPackageWrapper]Microsoft.Xrm.Tools.SolutionPackageWrapper.SolutionPackageInstallResult> [Microsoft.Xrm.Tools.SolutionPackageWrapper]Microsoft.Xrm.Tools.SolutionPackageWrapper.ImportAction::Execute()
0x135eb  pop
0x135ec  ldstr    aSolutionpackag_1// "[SolutionPackageInstall]: Successfully "...
0x135f1  ldc.i4.4
0x135f2  newarr   [mscorlib]System.Object
0x135f7  dup
0x135f8  ldc.i4.0
0x135f9  ldloc.1
0x135fa  box      [mscorlib]System.Guid
0x135ff  stelem.ref
0x13600  dup
0x13601  ldc.i4.1
0x13602  ldloc.2
0x13603  stelem.ref
0x13604  dup
0x13605  ldc.i4.2
0x13606  ldloc.s  5
0x13608  stelem.ref
0x13609  dup
0x1360a  ldc.i4.3
0x1360b  ldloc.s  6
0x1360d  stelem.ref
0x1360e  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x13613  ldc.i4.4
0x13614  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13619  ldstr    aSolutionPackag// "Solution Package install succeeded for "...
0x1361e  ldc.i4.2
0x1361f  newarr   [mscorlib]System.Object
0x13624  dup
0x13625  ldc.i4.0
0x13626  ldloc.1
0x13627  box      [mscorlib]System.Guid
0x1362c  stelem.ref
0x1362d  dup
0x1362e  ldc.i4.1
0x1362f  ldloc.2
0x13630  stelem.ref
0x13631  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13636  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x1363b  stloc.s  7
0x1363d  leave    loc_136CF
0x13642  ldstr    aSolutionpackag_2// "[SolutionPackageInstall]: Org name is n"...
0x13647  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1364c  ldc.i4.s 0xB
0x1364e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13653  ldstr    aSolutionPackag_0// "Solution Package install did not execut"...
0x13658  ldc.i4.2
0x13659  newarr   [mscorlib]System.Object
0x1365e  dup
0x1365f  ldc.i4.0
0x13660  ldloc.1
0x13661  box      [mscorlib]System.Guid
0x13666  stelem.ref
0x13667  dup
0x13668  ldc.i4.1
0x13669  ldloc.2
0x1366a  stelem.ref
0x1366b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13670  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x13675  stloc.s  7
0x13677  leave.s  loc_136CF
0x13679  stloc.s  8
0x1367b  ldstr    aSolutionpackag_3// "[SolutionPackageInstall]: SolutionPacka"...
0x13680  ldc.i4.3
0x13681  newarr   [mscorlib]System.Object
0x13686  dup
0x13687  ldc.i4.0
0x13688  ldloc.1
0x13689  box      [mscorlib]System.Guid
0x1368e  stelem.ref
0x1368f  dup
0x13690  ldc.i4.1
0x13691  ldloc.2
0x13692  stelem.ref
0x13693  dup
0x13694  ldc.i4.2
0x13695  ldloc.s  8
0x13697  stelem.ref
0x13698  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1369d  ldc.i4.s 0xB
0x1369f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x136a4  ldstr    aSolutionPackag_1// "Solution Package install failed for org"...
0x136a9  ldc.i4.3
0x136aa  newarr   [mscorlib]System.Object
0x136af  dup
0x136b0  ldc.i4.0
0x136b1  ldloc.1
0x136b2  box      [mscorlib]System.Guid
0x136b7  stelem.ref
0x136b8  dup
0x136b9  ldc.i4.1
0x136ba  ldloc.2
0x136bb  stelem.ref
0x136bc  dup
0x136bd  ldc.i4.2
0x136be  ldloc.s  8
0x136c0  stelem.ref
0x136c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x136c6  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x136cb  stloc.s  7
0x136cd  leave.s  loc_136CF
0x136cf  ldloc.s  7
0x136d1  ret
```
