# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgInstall

- ea: `0x12690`
- end: `0x127a4`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgInstall`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12510`

## callees

- `0x12690`
- `0x127b0`

## string_xrefs

- `0x1274a`: `Database update install failed for orgId = {0}.  Continuing with other orgs.  Exception: {1}`
- `0x1269b`: `AutomaticallyInstallDatabaseUpdates`
- `0x126f2`: `Database update install was successful for orgId = {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x12690  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12695  stloc.0
0x12696  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1269b  ldstr    aAutomaticallyi// "AutomaticallyInstallDatabaseUpdates"
0x126a0  callvirt T0x2B000012
0x126a5  brfalse  loc_127A2
0x126aa  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgReleaseFilePath()
0x126af  stloc.1
0x126b0  ldarg.1
0x126b1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x126b6  stloc.2
0x126b7  br       loc_12781
0x126bc  ldloc.2
0x126bd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x126c2  unbox.any [mscorlib]System.Guid
0x126c7  stloc.3
0x126c8  ldloc.3
0x126c9  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x126ce  ldloc.1
0x126cf  ldc.i4.1
0x126d0  ldc.i4   0x409
0x126d5  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::InstallUpdate(string, bool, int32)
0x126da  ldloc.3
0x126db  call     void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::InstallOptinUpdatesIfApplicable(valuetype [mscorlib]System.Guid orgId)
0x126e0  ldloc.0
0x126e1  ldloc.3
0x126e2  box      [mscorlib]System.Guid
0x126e7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x126ec  pop
0x126ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x126f2  ldstr    aDatabaseUpdate_1// "Database update install was successful "...
0x126f7  ldc.i4.1
0x126f8  newarr   [mscorlib]System.Object
0x126fd  dup
0x126fe  ldc.i4.0
0x126ff  ldloca.s 3
0x12701  constrained. [mscorlib]System.Guid
0x12707  callvirt instance string [mscorlib]System.Object::ToString()
0x1270c  stelem.ref
0x1270d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12712  ldc.i4.0
0x12713  newarr   [mscorlib]System.Object
0x12718  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1271d  leave.s  loc_12781
0x1271f  stloc.s  4
0x12721  ldarg.0
0x12722  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_updateErrors
0x12727  ldloc.3
0x12728  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x1272d  ldloc.3
0x1272e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationFriendlyName(valuetype [mscorlib]System.Guid)
0x12733  ldloc.s  4
0x12735  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateErrorInfo::.ctor(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Exception)
0x1273a  box      [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateErrorInfo
0x1273f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12744  pop
0x12745  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1274a  ldstr    aDatabaseUpdate// "Database update install failed for orgI"...
0x1274f  ldc.i4.2
0x12750  newarr   [mscorlib]System.Object
0x12755  dup
0x12756  ldc.i4.0
0x12757  ldloca.s 3
0x12759  constrained. [mscorlib]System.Guid
0x1275f  callvirt instance string [mscorlib]System.Object::ToString()
0x12764  stelem.ref
0x12765  dup
0x12766  ldc.i4.1
0x12767  ldloc.s  4
0x12769  callvirt instance string [mscorlib]System.Object::ToString()
0x1276e  stelem.ref
0x1276f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12774  ldc.i4.0
0x12775  newarr   [mscorlib]System.Object
0x1277a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1277f  leave.s  loc_12781
0x12781  ldloc.2
0x12782  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12787  brtrue   loc_126BC
0x1278c  leave.s  loc_127A2
0x1278e  ldloc.2
0x1278f  isinst   [mscorlib]System.IDisposable
0x12794  stloc.s  5
0x12796  ldloc.s  5
0x12798  brfalse.s loc_127A1
0x1279a  ldloc.s  5
0x1279c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x127a1  endfinally
0x127a2  ldloc.0
0x127a3  ret
```
