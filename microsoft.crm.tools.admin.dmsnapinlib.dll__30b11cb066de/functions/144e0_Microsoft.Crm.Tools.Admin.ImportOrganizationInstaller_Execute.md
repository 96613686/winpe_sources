# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Execute

- ea: `0x144e0`
- end: `0x1462a`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Execute`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x41c0`
- `0x84f0`
- `0x8630`
- `0x8670`
- `0x8720`
- `0x8a30`
- `0x8a50`
- `0x8bf0`
- `0x144e0`
- `0x14630`
- `0x14c00`
- `0x15840`
- `0x16940`

## pseudocode

```c

```

## disassembly

```asm
0x144e0  ldarg.1
0x144e1  ldstr    aObj// "obj"
0x144e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x144eb  ldarg.1
0x144ec  castclass [mscorlib]System.Collections.IDictionary
0x144f1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x144f6  stloc.0
0x144f7  ldloc.0
0x144f8  ldloc.0
0x144f9  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x144fe  ldloc.0
0x144ff  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14504  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetCrmDatabaseVersion(string, string)
0x14509  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_ExistingDatabaseVersion(class [mscorlib]System.Version value)
0x1450e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.AssemblyResolver::.ctor()
0x14513  stloc.1
0x14514  ldloc.0
0x14515  call     bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsDirectlyImportable(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x1451a  brfalse.s loc_14537
0x1451c  ldstr    aOrganizationCa// "Organization can be directly imported i"...
0x14521  ldc.i4.0
0x14522  newarr   [mscorlib]System.Object
0x14527  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1452c  ldarg.0
0x1452d  ldloc.0
0x1452e  ldc.i4.1
0x1452f  ldc.i4.0
0x14530  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, [opt] bool patchOnImport, [opt] valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode orgDbUpdateMode)
0x14535  br.s     loc_14592
0x14537  ldloc.0
0x14538  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x1453d  ldloc.0
0x1453e  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14543  call     bool Microsoft.Crm.Tools.Admin.OrganizationUpgrader::IsOrganizationVersionSupportedForUpgrade(string sqlServerName, string organizationDatabaseName)
0x14548  brfalse.s loc_14563
0x1454a  ldstr    aOrganizationMu// "Organization must be upgraded and impor"...
0x1454f  ldc.i4.0
0x14550  newarr   [mscorlib]System.Object
0x14555  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1455a  ldarg.0
0x1455b  ldloc.0
0x1455c  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::ImportAndUpgrade(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x14561  br.s     loc_14592
0x14563  ldstr    aTheOrganizatio_2// "The organization database version {0} i"...
0x14568  ldc.i4.1
0x14569  newarr   [mscorlib]System.Object
0x1456e  dup
0x1456f  ldc.i4.0
0x14570  ldloc.0
0x14571  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0x14576  stelem.ref
0x14577  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1457c  ldstr    aOrganizationda_2// "OrganizationDatabaseVersionValidator.Fa"...
0x14581  ldc.i4.0
0x14582  newarr   [mscorlib]System.Object
0x14587  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1458c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x14591  throw
0x14592  leave.s  loc_1459E
0x14594  ldloc.1
0x14595  brfalse.s loc_1459D
0x14597  ldloc.1
0x14598  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1459d  endfinally
0x1459e  leave    loc_14628
0x145a3  stloc.2
0x145a4  ldarg.0
0x145a5  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x145aa  ldarg.0
0x145ab  ldc.i4.1
0x145ac  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x145b1  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x145b6  ldloc.2
0x145b7  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x145bc  stloc.3
0x145bd  ldloc.3
0x145be  brfalse.s loc_145CD
0x145c0  ldc.i4   0x8004B001
0x145c5  ldloc.3
0x145c6  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x145cb  beq.s    loc_14615
0x145cd  ldstr    aOrganizationIm_1// "Organization.Import.Failed.Log"
0x145d2  ldc.i4.3
0x145d3  newarr   [mscorlib]System.Object
0x145d8  dup
0x145d9  ldc.i4.0
0x145da  ldloc.0
0x145db  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x145e0  stelem.ref
0x145e1  dup
0x145e2  ldc.i4.1
0x145e3  ldloc.0
0x145e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x145e9  box      [mscorlib]System.Guid
0x145ee  stelem.ref
0x145ef  dup
0x145f0  ldc.i4.2
0x145f1  ldloc.2
0x145f2  stelem.ref
0x145f3  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x145f8  stloc.s  4
0x145fa  ldloc.s  4
0x145fc  ldc.i4.0
0x145fd  newarr   [mscorlib]System.Object
0x14602  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x14607  ldloc.s  4
0x14609  ldloc.2
0x1460a  ldc.i4   0x8004B001
0x1460f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x14614  throw
0x14615  ldloc.3
0x14616  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1461b  ldc.i4.0
0x1461c  newarr   [mscorlib]System.Object
0x14621  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x14626  rethrow
0x14628  ldnull
0x14629  ret
```
