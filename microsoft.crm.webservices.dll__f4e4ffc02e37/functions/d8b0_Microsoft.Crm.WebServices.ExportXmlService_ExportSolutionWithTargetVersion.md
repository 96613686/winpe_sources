# Microsoft.Crm.WebServices.ExportXmlService::ExportSolutionWithTargetVersion

- ea: `0xd8b0`
- end: `0xda15`
- name: `Microsoft.Crm.WebServices.ExportXmlService::ExportSolutionWithTargetVersion`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd880`

## callees

- `0xd8b0`
- `0xdaf0`
- `0xdb30`
- `0xdb80`

## pseudocode

```c

```

## disassembly

```asm
0xd8b0  ldarg.0
0xd8b1  ldarg.1
0xd8b2  ldarg.s  0xF
0xd8b4  call     instance void Microsoft.Crm.WebServices.ExportXmlService::BlockExportOfPatchedSolution(string name, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8b9  ldarg.0
0xd8ba  ldarg.s  0xF
0xd8bc  call     instance void Microsoft.Crm.WebServices.ExportXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8c1  ldnull
0xd8c2  stloc.0
0xd8c3  ldarg.3
0xd8c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd8c9  brtrue   loc_D9D0
0xd8ce  ldstr    aAllowsolutione// "AllowSolutionExportAsTestHook"
0xd8d3  ldc.i4.0
0xd8d4  box      [mscorlib]System.Int32
0xd8d9  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xd8de  unbox.any [mscorlib]System.Int32
0xd8e3  ldc.i4.1
0xd8e4  beq.s    loc_D8F1
0xd8e6  ldstr    aExportingToATa// "Exporting to a target version is not su"...
0xd8eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xd8f0  throw
0xd8f1  ldarg.1
0xd8f2  ldstr    aDefault// "Default"
0xd8f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd8fc  brfalse.s loc_D934
0xd8fe  ldarg.s  0xF
0xd900  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xd905  ldstr    aAllowdefaultso// "AllowDefaultSolutionExport"
0xd90a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xd90f  brtrue.s loc_D934
0xd911  ldstr    aAllowdefaultso_0// "AllowDefaultSolutionExportAsTestHook"
0xd916  ldc.i4.0
0xd917  box      [mscorlib]System.Int32
0xd91c  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xd921  unbox.any [mscorlib]System.Int32
0xd926  ldc.i4.1
0xd927  beq.s    loc_D934
0xd929  ldstr    aDefaultSolutio// "Default solution does not support expor"...
0xd92e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xd933  throw
0xd934  ldarg.3
0xd935  ldloca.s 0
0xd937  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xd93c  brtrue.s loc_D945
0xd93e  ldarg.3
0xd93f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0xd944  throw
0xd945  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::.ctor()
0xd94a  ldarg.s  0xF
0xd94c  call     instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::RetrieveVersion(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd951  ldloca.s 2
0xd953  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xd958  brfalse.s loc_D9C5
0xd95a  ldloc.2
0xd95b  callvirt instance int32 [mscorlib]System.Version::get_Major()
0xd960  ldloc.0
0xd961  callvirt instance int32 [mscorlib]System.Version::get_Major()
0xd966  bne.un.s loc_D97F
0xd968  ldloc.2
0xd969  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0xd96e  ldloc.0
0xd96f  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0xd974  blt.s    loc_D97F
0xd976  ldloc.0
0xd977  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0xd97c  ldc.i4.0
0xd97d  bge.s    loc_D9D0
0xd97f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd984  ldstr    aExportAsTarget// "Export as targetVersion should between "...
0xd989  ldc.i4.3
0xd98a  newarr   [mscorlib]System.Object
0xd98f  dup
0xd990  ldc.i4.0
0xd991  ldloc.2
0xd992  ldc.i4.2
0xd993  callvirt instance string [mscorlib]System.Version::ToString(int32)
0xd998  stelem.ref
0xd999  dup
0xd99a  ldc.i4.1
0xd99b  ldloc.2
0xd99c  callvirt instance int32 [mscorlib]System.Version::get_Major()
0xd9a1  box      [mscorlib]System.Int32
0xd9a6  ldstr    a0_0// ".0"
0xd9ab  call     instance string [mscorlib]System.String::ToUpperInvariant()
0xd9b0  call     string [mscorlib]System.String::Concat(object, object)
0xd9b5  stelem.ref
0xd9b6  dup
0xd9b7  ldc.i4.2
0xd9b8  ldloc.0
0xd9b9  stelem.ref
0xd9ba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd9bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xd9c4  throw
0xd9c5  ldstr    aErrorRetrievin// "Error retrieving CRM Database version."
0xd9ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xd9cf  throw
0xd9d0  ldarg.0
0xd9d1  ldarg.1
0xd9d2  ldloc.0
0xd9d3  ldarg.s  0xF
0xd9d5  call     instance void Microsoft.Crm.WebServices.ExportXmlService::BlockPreAraPatchExport(string name, class [mscorlib]System.Version targetVersion, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd9da  ldarg.1
0xd9db  brtrue.s loc_D9E8
0xd9dd  ldstr    aSolutionname// "solutionName"
0xd9e2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd9e7  throw
0xd9e8  ldc.i4.0
0xd9e9  ldarg.s  5
0xd9eb  ldarg.s  6
0xd9ed  ldarg.s  7
0xd9ef  ldarg.s  8
0xd9f1  ldarg.s  9
0xd9f3  ldarg.s  0xA
0xd9f5  ldarg.s  0xC
0xd9f7  ldarg.s  0xD
0xd9f9  ldarg.s  0xE
0xd9fb  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters::.ctor(bool, bool, bool, bool, bool, bool, bool, bool, bool, bool)
0xda00  stloc.1
0xda01  ldarg.s  0xF
0xda03  ldarg.1
0xda04  ldarg.2
0xda05  ldloc.0
0xda06  ldloc.1
0xda07  ldarg.s  0xB
0xda09  ldc.i4.0
0xda0a  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportXml::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, bool, class [mscorlib]System.Version, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters, bool, bool)
0xda0f  callvirt instance unsigned int8[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportXml::RunExport()
0xda14  ret
```
