# Microsoft.Crm.Tools.Admin.ImportAppsSolution::InstallSolution

- ea: `0x5c90`
- end: `0x5d7f`
- name: `Microsoft.Crm.Tools.Admin.ImportAppsSolution::InstallSolution`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5be0`

## callees

- `0x5bc0`
- `0x5c90`

## string_xrefs

- `0x5d4a`: `Failed to install solution {0} at location {1} : {2}`

## pseudocode

```c

```

## disassembly

```asm
0x5c90  ldarg.3
0x5c91  ldstr    aSolutionbytes// "solutionBytes"
0x5c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c9b  ldarg.0
0x5c9c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ImportAppsSolution::get_OrganizationId()
0x5ca1  ldc.i4.0
0x5ca2  ldc.i4.0
0x5ca3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x5ca8  stloc.0
0x5ca9  ldloc.0
0x5caa  ldarg.0
0x5cab  ldfld    int32 Microsoft.Crm.Tools.Admin.ImportAppsSolution::_orgLanguageCode
0x5cb0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::SetLanguageCode(int32)
0x5cb5  ldarg.0
0x5cb6  ldfld    bool Microsoft.Crm.Tools.Admin.ImportAppsSolution::_isOrgUpgrade
0x5cbb  brfalse.s loc_5CD2
0x5cbd  ldloc.0
0x5cbe  ldc.i4.0
0x5cbf  ldc.i4.1
0x5cc0  ldc.i4.8
0x5cc1  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x5cc6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext::.ctor(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.OperationContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x5ccb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext)
0x5cd0  br.s     loc_5CD9
0x5cd2  ldloc.0
0x5cd3  ldc.i4.0
0x5cd4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x5cd9  nop
0x5cda  ldloc.0
0x5cdb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ce0  stloc.1
0x5ce1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.AssemblyResolver::.ctor()
0x5ce6  stloc.2
0x5ce7  ldarg.0
0x5ce8  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ImportAppsSolution::get_OrganizationId()
0x5ced  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SetMetadataCacheConfigForUpdates::.ctor(valuetype [mscorlib]System.Guid)
0x5cf2  stloc.3
0x5cf3  ldc.i4.0
0x5cf4  ldc.i4.1
0x5cf5  ldarg.3
0x5cf6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5cfb  ldc.i4.0
0x5cfc  ldc.i4.1
0x5cfd  ldloc.0
0x5cfe  ldc.i4.0
0x5cff  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::.ctor(bool, bool, unsigned int8[], valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x5d04  stloc.s  4
0x5d06  ldloc.s  4
0x5d08  ldc.i4.1
0x5d09  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport(bool)
0x5d0e  leave.s  loc_5D1C
0x5d10  ldloc.s  4
0x5d12  brfalse.s loc_5D1B
0x5d14  ldloc.s  4
0x5d16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d1b  endfinally
0x5d1c  leave.s  loc_5D28
0x5d1e  ldloc.3
0x5d1f  brfalse.s loc_5D27
0x5d21  ldloc.3
0x5d22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d27  endfinally
0x5d28  leave.s  loc_5D34
0x5d2a  ldloc.2
0x5d2b  brfalse.s loc_5D33
0x5d2d  ldloc.2
0x5d2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d33  endfinally
0x5d34  leave.s  loc_5D40
0x5d36  ldloc.1
0x5d37  brfalse.s loc_5D3F
0x5d39  ldloc.1
0x5d3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d3f  endfinally
0x5d40  ldloc.0
0x5d41  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x5d46  leave.s  loc_5D7E
0x5d48  stloc.s  5
0x5d4a  ldstr    aFailedToInstal// "Failed to install solution {0} at locat"...
0x5d4f  ldc.i4.3
0x5d50  newarr   [mscorlib]System.Object
0x5d55  dup
0x5d56  ldc.i4.0
0x5d57  ldarg.1
0x5d58  stelem.ref
0x5d59  dup
0x5d5a  ldc.i4.1
0x5d5b  ldarg.2
0x5d5c  stelem.ref
0x5d5d  dup
0x5d5e  ldc.i4.2
0x5d5f  ldloc.s  5
0x5d61  callvirt instance string [mscorlib]System.Object::ToString()
0x5d66  stelem.ref
0x5d67  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x5d6c  ldloc.0
0x5d6d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x5d72  rethrow
0x5d74  ldloc.0
0x5d75  brfalse.s loc_5D7D
0x5d77  ldloc.0
0x5d78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d7d  endfinally
0x5d7e  ret
```
