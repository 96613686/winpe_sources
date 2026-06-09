# Microsoft.Crm.Tools.Admin.UpgradeNewSolutionAwareEntities::Do

- ea: `0xf930`
- end: `0xfb2c`
- name: `Microsoft.Crm.Tools.Admin.UpgradeNewSolutionAwareEntities::Do`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x71c0`
- `0x84f0`
- `0x8630`
- `0x99c0`
- `0xf930`

## string_xrefs

- `0xf98d`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xfa53`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`

## pseudocode

```c

```

## disassembly

```asm
0xf930  ldarg.1
0xf931  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xf936  stloc.0
0xf937  ldc.i4.2
0xf938  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::ImpersonateSelf(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SecurityImpersonationLevel)
0xf93d  ldloc.0
0xf93e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xf943  ldc.i4.0
0xf944  ldc.i4.0
0xf945  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xf94a  stloc.1
0xf94b  ldloc.1
0xf94c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf951  ldc.i4.0
0xf952  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemExecutionOperationContext::.ctor()
0xf957  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext)
0xf95c  ldloc.1
0xf95d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::DisableSolutionProcessing()
0xf962  ldloc.1
0xf963  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf968  stloc.2
0xf969  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xf96e  stloc.3
0xf96f  ldloc.1
0xf970  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xf975  ldstr    aSelectEntityid// "SELECT EntityId FROM SolutionAwareEntit"...
0xf97a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0xf97f  stloc.s  6
0xf981  ldloc.s  6
0xf983  ldc.i4   0x8EF
0xf988  ldstr    aDo// "Do"
0xf98d  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xf992  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xf997  stloc.s  7
0xf999  br.s     loc_F9B2
0xf99b  ldloc.3
0xf99c  ldloc.s  7
0xf99e  ldstr    aEntityid// "EntityId"
0xf9a3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xf9a8  unbox.any [mscorlib]System.Guid
0xf9ad  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xf9b2  ldloc.s  7
0xf9b4  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xf9b9  brtrue.s loc_F99B
0xf9bb  leave.s  loc_F9C9
0xf9bd  ldloc.s  7
0xf9bf  brfalse.s loc_F9C8
0xf9c1  ldloc.s  7
0xf9c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf9c8  endfinally
0xf9c9  leave.s  loc_F9D7
0xf9cb  ldloc.s  6
0xf9cd  brfalse.s loc_F9D6
0xf9cf  ldloc.s  6
0xf9d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf9d6  endfinally
0xf9d7  ldloc.3
0xf9d8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xf9dd  stloc.s  8
0xf9df  br.s     loc_FA0F
0xf9e1  ldloc.s  8
0xf9e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0xf9e8  stloc.s  9
0xf9ea  ldloc.1
0xf9eb  ldloc.s  9
0xf9ed  ldarg.0
0xf9ee  call     instance class Microsoft.Crm.Tools.Admin.OrganizationOperation Microsoft.Crm.Tools.Admin.OrganizationAction::get_OperationBase()
0xf9f3  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationOperation::get_SqlDirectory()
0xf9f8  call     class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.ObjectModel.SolutionsUpgrade.ISolutionAwareEntityUpgrader [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.ObjectModel.SolutionsUpgrade.SolutionAwareEntityUpgradeFactory::GetUpgrader(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Guid, string)
0xf9fd  dup
0xf9fe  ldloc.1
0xf9ff  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.ObjectModel.SolutionsUpgrade.ISolutionAwareEntityUpgrader::Upgrade(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfa04  ldloc.1
0xfa05  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xfa0a  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.ObjectModel.SolutionsUpgrade.ISolutionAwareEntityUpgrader::MarkAsCompleted(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0xfa0f  ldloc.s  8
0xfa11  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xfa16  brtrue.s loc_F9E1
0xfa18  leave.s  loc_FA26
0xfa1a  ldloc.s  8
0xfa1c  brfalse.s loc_FA25
0xfa1e  ldloc.s  8
0xfa20  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfa25  endfinally
0xfa26  ldstr    aTheFollowingEn// "The following Entities do no have a Sol"...
0xfa2b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xfa30  stloc.s  4
0xfa32  ldc.i4.0
0xfa33  stloc.s  5
0xfa35  ldloc.1
0xfa36  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xfa3b  ldstr    aSelectEntityid// "SELECT EntityId FROM SolutionAwareEntit"...
0xfa40  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0xfa45  stloc.s  0xA
0xfa47  ldloc.s  0xA
0xfa49  ldc.i4   0x90C
0xfa4e  ldstr    aDo// "Do"
0xfa53  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xfa58  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xfa5d  stloc.s  0xB
0xfa5f  br.s     loc_FAAE
0xfa61  ldloc.s  0xB
0xfa63  ldstr    aEntityid// "EntityId"
0xfa68  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xfa6d  unbox.any [mscorlib]System.Guid
0xfa72  stloc.s  0xC
0xfa74  ldc.i4.1
0xfa75  stloc.s  5
0xfa77  ldloc.s  4
0xfa79  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa7e  ldstr    a0_0// " '{0}'"
0xfa83  ldc.i4.1
0xfa84  newarr   [mscorlib]System.Object
0xfa89  dup
0xfa8a  ldc.i4.0
0xfa8b  ldloc.1
0xfa8c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfa91  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0xfa96  ldloc.s  0xC
0xfa98  box      [mscorlib]System.Guid
0xfa9d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0xfaa2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0xfaa7  stelem.ref
0xfaa8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xfaad  pop
0xfaae  ldloc.s  0xB
0xfab0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xfab5  brtrue.s loc_FA61
0xfab7  leave.s  loc_FAC5
0xfab9  ldloc.s  0xB
0xfabb  brfalse.s loc_FAC4
0xfabd  ldloc.s  0xB
0xfabf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfac4  endfinally
0xfac5  leave.s  loc_FAD3
0xfac7  ldloc.s  0xA
0xfac9  brfalse.s loc_FAD2
0xfacb  ldloc.s  0xA
0xfacd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfad2  endfinally
0xfad3  ldloc.s  5
0xfad5  brfalse.s loc_FAFE
0xfad7  ldstr    aUpgradenewsolu// "UpgradeNewSolutionAwareEntities action:"...
0xfadc  ldc.i4.1
0xfadd  newarr   [mscorlib]System.Object
0xfae2  dup
0xfae3  ldc.i4.0
0xfae4  ldloc.s  4
0xfae6  callvirt instance string [mscorlib]System.Object::ToString()
0xfaeb  stelem.ref
0xfaec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0xfaf1  ldloc.s  4
0xfaf3  callvirt instance string [mscorlib]System.Object::ToString()
0xfaf8  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0xfafd  throw
0xfafe  leave.s  loc_FB0A
0xfb00  ldloc.2
0xfb01  brfalse.s loc_FB09
0xfb03  ldloc.2
0xfb04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfb09  endfinally
0xfb0a  ldloc.1
0xfb0b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xfb10  leave.s  loc_FB2B
0xfb12  pop
0xfb13  ldloc.1
0xfb14  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xfb19  rethrow
0xfb1b  ldloc.1
0xfb1c  brfalse.s loc_FB24
0xfb1e  ldloc.1
0xfb1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfb24  endfinally
0xfb25  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RevertToSelf()
0xfb2a  endfinally
0xfb2b  ret
```
