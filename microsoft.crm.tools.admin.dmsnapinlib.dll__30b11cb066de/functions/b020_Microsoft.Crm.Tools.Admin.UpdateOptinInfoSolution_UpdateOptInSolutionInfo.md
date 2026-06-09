# Microsoft.Crm.Tools.Admin.UpdateOptinInfoSolution::UpdateOptInSolutionInfo

- ea: `0xb020`
- end: `0xb0ab`
- name: `Microsoft.Crm.Tools.Admin.UpdateOptinInfoSolution::UpdateOptInSolutionInfo`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xb000`

## callees

- `0xb020`

## string_xrefs

- `0xb025`: `UpdateOptInSolutionInfo(): orgId = {0}, name = {1}, version = {2}.`
- `0xb08e`: `UpdateOptInSolutionInfo`
- `0xb093`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\PostXrmOrganizationCreatedConfiguration.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb020  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb025  ldstr    aUpdateoptinsol// "UpdateOptInSolutionInfo(): orgId = {0},"...
0xb02a  ldc.i4.3
0xb02b  newarr   [mscorlib]System.Object
0xb030  dup
0xb031  ldc.i4.0
0xb032  ldarga.s 0
0xb034  constrained. [mscorlib]System.Guid
0xb03a  callvirt instance string [mscorlib]System.Object::ToString()
0xb03f  stelem.ref
0xb040  dup
0xb041  ldc.i4.1
0xb042  ldarg.1
0xb043  stelem.ref
0xb044  dup
0xb045  ldc.i4.2
0xb046  ldarg.2
0xb047  stelem.ref
0xb048  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb04d  ldc.i4.0
0xb04e  newarr   [mscorlib]System.Object
0xb053  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xb058  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xb05d  stloc.0
0xb05e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb063  stloc.1
0xb064  ldloc.1
0xb065  ldstr    aOptinsolutionn// "OptInSolutionName"
0xb06a  ldarg.1
0xb06b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb070  ldloc.1
0xb071  ldstr    aOptinsolutionv// "OptInSolutionVersion"
0xb076  ldarg.2
0xb077  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb07c  ldloc.0
0xb07d  ldstr    aOrganization// "Organization"
0xb082  ldarg.0
0xb083  box      [mscorlib]System.Guid
0xb088  ldloc.1
0xb089  ldc.i4   0x263
0xb08e  ldstr    aUpdateoptinsol_0// "UpdateOptInSolutionInfo"
0xb093  ldstr    aDDbsShDccm2110_7// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xb098  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xb09d  pop
0xb09e  leave.s  loc_B0AA
0xb0a0  ldloc.0
0xb0a1  brfalse.s loc_B0A9
0xb0a3  ldloc.0
0xb0a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb0a9  endfinally
0xb0aa  ret
```
