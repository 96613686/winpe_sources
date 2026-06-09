# Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::SetOptInSolutionInfo

- ea: `0xe830`
- end: `0xe8ab`
- name: `Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::SetOptInSolutionInfo`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xe590`

## callees

- `0xe830`

## string_xrefs

- `0xe893`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xe835`: `UpdateOptInSolutionInfo(): orgId = {0}, name = {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe830  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe835  ldstr    aUpdateoptinsol_1// "UpdateOptInSolutionInfo(): orgId = {0},"...
0xe83a  ldc.i4.2
0xe83b  newarr   [mscorlib]System.Object
0xe840  dup
0xe841  ldc.i4.0
0xe842  ldarga.s 0
0xe844  constrained. [mscorlib]System.Guid
0xe84a  callvirt instance string [mscorlib]System.Object::ToString()
0xe84f  stelem.ref
0xe850  dup
0xe851  ldc.i4.1
0xe852  ldarg.1
0xe853  stelem.ref
0xe854  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe859  ldc.i4.0
0xe85a  newarr   [mscorlib]System.Object
0xe85f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xe864  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xe869  stloc.0
0xe86a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe86f  stloc.1
0xe870  ldloc.1
0xe871  ldstr    aOptinsolutionn// "OptInSolutionName"
0xe876  ldarg.1
0xe877  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe87c  ldloc.0
0xe87d  ldstr    aOrganization// "Organization"
0xe882  ldarg.0
0xe883  box      [mscorlib]System.Guid
0xe888  ldloc.1
0xe889  ldc.i4   0x509
0xe88e  ldstr    aSetoptinsoluti// "SetOptInSolutionInfo"
0xe893  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xe898  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe89d  pop
0xe89e  leave.s  loc_E8AA
0xe8a0  ldloc.0
0xe8a1  brfalse.s loc_E8A9
0xe8a3  ldloc.0
0xe8a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8a9  endfinally
0xe8aa  ret
```
