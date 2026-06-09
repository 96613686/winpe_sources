# Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::InstallSolution

- ea: `0x18ab0`
- end: `0x18bdc`
- name: `Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::InstallSolution`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18a00`

## callees

- `0x189e0`
- `0x18ab0`

## string_xrefs

- `0x18ba3`: `Failed to install Solution={0}, FileName={1} for OrgId= {2}`

## pseudocode

```c

```

## disassembly

```asm
0x18ab0  ldarg.3
0x18ab1  ldstr    aSolutionbytes// "solutionBytes"
0x18ab6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x18abb  ldc.i4   0x409
0x18ac0  stloc.0
0x18ac1  ldarg.0
0x18ac2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18ac7  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetConnectionTimeout()
0x18acc  ldc.i4.0
0x18acd  ldc.i4.0
0x18ace  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x18ad3  ldarg.0
0x18ad4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18ad9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DllMethodActionsUtility::CreateExecutionContext(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x18ade  stloc.1
0x18adf  ldloc.1
0x18ae0  ldc.i4.1
0x18ae1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x18ae6  ldloc.1
0x18ae7  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrganizationBaseLanguage::GetOrganizationBaseLanguage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18aec  stloc.0
0x18aed  ldloc.1
0x18aee  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x18af3  leave.s  loc_18B08
0x18af5  pop
0x18af6  ldloc.1
0x18af7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x18afc  rethrow
0x18afe  ldloc.1
0x18aff  brfalse.s loc_18B07
0x18b01  ldloc.1
0x18b02  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b07  endfinally
0x18b08  ldarg.0
0x18b09  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18b0e  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x18b13  ldc.i4.0
0x18b14  ldc.i4.0
0x18b15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x18b1a  ldarg.0
0x18b1b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18b20  ldloc.0
0x18b21  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DllMethodActionsUtility::CreateExecutionContextForImportCustomSolution(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid, int32)
0x18b26  stloc.2
0x18b27  ldloc.2
0x18b28  ldc.i4.0
0x18b29  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x18b2e  ldloc.2
0x18b2f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18b34  stloc.3
0x18b35  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.AssemblyResolver::.ctor()
0x18b3a  stloc.s  4
0x18b3c  ldarg.0
0x18b3d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18b42  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SetMetadataCacheConfigForUpdates::.ctor(valuetype [mscorlib]System.Guid)
0x18b47  stloc.s  5
0x18b49  ldc.i4.0
0x18b4a  ldc.i4.1
0x18b4b  ldarg.3
0x18b4c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x18b51  ldc.i4.0
0x18b52  ldc.i4.1
0x18b53  ldloc.2
0x18b54  ldc.i4.0
0x18b55  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::.ctor(bool, bool, unsigned int8[], valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x18b5a  stloc.s  6
0x18b5c  ldloc.s  6
0x18b5e  ldc.i4.1
0x18b5f  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport(bool)
0x18b64  leave.s  loc_18B72
0x18b66  ldloc.s  6
0x18b68  brfalse.s loc_18B71
0x18b6a  ldloc.s  6
0x18b6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b71  endfinally
0x18b72  leave.s  loc_18B80
0x18b74  ldloc.s  5
0x18b76  brfalse.s loc_18B7F
0x18b78  ldloc.s  5
0x18b7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b7f  endfinally
0x18b80  leave.s  loc_18B8E
0x18b82  ldloc.s  4
0x18b84  brfalse.s loc_18B8D
0x18b86  ldloc.s  4
0x18b88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b8d  endfinally
0x18b8e  leave.s  loc_18B9A
0x18b90  ldloc.3
0x18b91  brfalse.s loc_18B99
0x18b93  ldloc.3
0x18b94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b99  endfinally
0x18b9a  ldloc.2
0x18b9b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x18ba0  leave.s  loc_18BDB
0x18ba2  pop
0x18ba3  ldstr    aFailedToInstal_5// "Failed to install Solution={0}, FileNam"...
0x18ba8  ldc.i4.3
0x18ba9  newarr   [mscorlib]System.Object
0x18bae  dup
0x18baf  ldc.i4.0
0x18bb0  ldarg.1
0x18bb1  stelem.ref
0x18bb2  dup
0x18bb3  ldc.i4.1
0x18bb4  ldarg.2
0x18bb5  stelem.ref
0x18bb6  dup
0x18bb7  ldc.i4.2
0x18bb8  ldarg.0
0x18bb9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::get_OrganizationId()
0x18bbe  box      [mscorlib]System.Guid
0x18bc3  stelem.ref
0x18bc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x18bc9  ldloc.2
0x18bca  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x18bcf  rethrow
0x18bd1  ldloc.2
0x18bd2  brfalse.s loc_18BDA
0x18bd4  ldloc.2
0x18bd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18bda  endfinally
0x18bdb  ret
```
