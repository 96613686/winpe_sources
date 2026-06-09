# Microsoft.Crm.Tools.Admin.PopulateDependencyNodesAction::Do

- ea: `0xf0c0`
- end: `0xf229`
- name: `Microsoft.Crm.Tools.Admin.PopulateDependencyNodesAction::Do`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0xf0c0`

## string_xrefs

- `0xf179`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xf140`: `\nDELETE TOP (SELECT count(*) - 1 \nFROM DependencyFeatureBase WHERE DependencyFeatureId = @LeoFeatureId) \nFROM DependencyFeatureBase WHERE DependencyFeatureId = @LeoFeatureId\n\nDELETE FROM FieldPermissionBase WHERE SolutionId\nNOT IN (SELECT SolutionId FROM SolutionBase)`

## pseudocode

```c

```

## disassembly

```asm
0xf0c0  ldarg.1
0xf0c1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xf0c6  stloc.0
0xf0c7  ldc.i4.2
0xf0c8  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::ImpersonateSelf(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SecurityImpersonationLevel)
0xf0cd  ldloc.0
0xf0ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xf0d3  ldarg.0
0xf0d4  ldfld    bool Microsoft.Crm.Tools.Admin.PopulateDependencyNodesAction::isXrm
0xf0d9  ldc.i4.0
0xf0da  ldc.i4.0
0xf0db  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xf0e0  stloc.1
0xf0e1  ldloc.1
0xf0e2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0e7  ldc.i4.0
0xf0e8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemExecutionOperationContext::.ctor()
0xf0ed  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext)
0xf0f2  ldloc.1
0xf0f3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xf0f8  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xf0fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier::SetNewTimeoutIfLonger(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, int32)
0xf102  stloc.2
0xf103  ldloc.1
0xf104  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf109  stloc.3
0xf10a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf10f  ldstr    aDependencyBegi// "Dependency_BEGIN_{0}.PopulateDependency"...
0xf114  ldc.i4.1
0xf115  newarr   [mscorlib]System.Object
0xf11a  dup
0xf11b  ldc.i4.0
0xf11c  ldarg.0
0xf11d  stelem.ref
0xf11e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf123  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xf128  ldloc.0
0xf129  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xf12e  ldc.i4.0
0xf12f  ldc.i4.0
0xf130  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xf135  stloc.s  4
0xf137  ldloc.s  4
0xf139  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xf13e  ldloc.s  4
0xf140  ldstr    aDeleteTopSelec// "\r\nDELETE TOP (SELECT count(*) - 1 \r"...
0xf145  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xf14a  stloc.s  5
0xf14c  ldloc.s  5
0xf14e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf153  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf158  ldstr    aLeofeatureid// "@LeoFeatureId"
0xf15d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.Solution.Dependency.DependencyFeatureConstants::LeoFeature
0xf162  box      [mscorlib]System.Guid
0xf167  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf16c  pop
0xf16d  ldloc.s  5
0xf16f  ldc.i4   0x71E
0xf174  ldstr    aDo// "Do"
0xf179  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xf17e  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xf183  pop
0xf184  leave.s  loc_F192
0xf186  ldloc.s  5
0xf188  brfalse.s loc_F191
0xf18a  ldloc.s  5
0xf18c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf191  endfinally
0xf192  ldloc.s  4
0xf194  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xf199  leave.s  loc_F1A7
0xf19b  ldloc.s  4
0xf19d  brfalse.s loc_F1A6
0xf19f  ldloc.s  4
0xf1a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf1a6  endfinally
0xf1a7  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::.ctor()
0xf1ac  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.InvalidDependencyService::.ctor()
0xf1b1  ldloc.1
0xf1b2  call     instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.InvalidDependencyService::DeleteAllInvalidDependencies(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf1b7  pop
0xf1b8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0xf1bd  ldloc.1
0xf1be  call     instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::DeleteAllDependencies(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf1c3  pop
0xf1c4  dup
0xf1c5  ldloc.1
0xf1c6  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::DeleteAllDependencyNodes(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf1cb  pop
0xf1cc  ldloc.1
0xf1cd  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::CreateAllDependencyNodes(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf1d2  leave.s  loc_F1DE
0xf1d4  ldloc.3
0xf1d5  brfalse.s loc_F1DD
0xf1d7  ldloc.3
0xf1d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf1dd  endfinally
0xf1de  ldloc.1
0xf1df  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xf1e4  leave.s  loc_F228
0xf1e6  pop
0xf1e7  ldloc.1
0xf1e8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xf1ed  rethrow
0xf1ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1f4  ldstr    aDependencyEnd0// "Dependency_END_{0}.PopulateDependencyNo"...
0xf1f9  ldc.i4.1
0xf1fa  newarr   [mscorlib]System.Object
0xf1ff  dup
0xf200  ldc.i4.0
0xf201  ldarg.0
0xf202  stelem.ref
0xf203  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf208  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xf20d  endfinally
0xf20e  ldloc.2
0xf20f  brfalse.s loc_F217
0xf211  ldloc.2
0xf212  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf217  endfinally
0xf218  ldloc.1
0xf219  brfalse.s loc_F221
0xf21b  ldloc.1
0xf21c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf221  endfinally
0xf222  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RevertToSelf()
0xf227  endfinally
0xf228  ret
```
