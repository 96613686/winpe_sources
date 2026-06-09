# Microsoft.Crm.WebServices.ExportXmlService::ExportFullSolution

- ea: `0xda20`
- end: `0xda8b`
- name: `Microsoft.Crm.WebServices.ExportXmlService::ExportFullSolution`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xda20`
- `0xdaf0`
- `0xdb80`

## pseudocode

```c

```

## disassembly

```asm
0xda20  ldarg.0
0xda21  ldarg.1
0xda22  ldarg.2
0xda23  call     instance void Microsoft.Crm.WebServices.ExportXmlService::BlockExportOfPatchedSolution(string name, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xda28  ldarg.0
0xda29  ldarg.2
0xda2a  call     instance void Microsoft.Crm.WebServices.ExportXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xda2f  ldarg.1
0xda30  brtrue.s loc_DA3D
0xda32  ldstr    aSolutionname// "solutionName"
0xda37  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xda3c  throw
0xda3d  ldarg.1
0xda3e  ldstr    aDefault// "Default"
0xda43  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xda48  brfalse.s loc_DA69
0xda4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xda4f  ldstr    aExportfullsolu// "ExportFullSolution is only supported fo"...
0xda54  ldc.i4.1
0xda55  newarr   [mscorlib]System.Object
0xda5a  dup
0xda5b  ldc.i4.0
0xda5c  ldarg.1
0xda5d  stelem.ref
0xda5e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xda63  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xda68  throw
0xda69  ldc.i4.1
0xda6a  ldc.i4.1
0xda6b  ldc.i4.1
0xda6c  ldc.i4.1
0xda6d  ldc.i4.1
0xda6e  ldc.i4.1
0xda6f  ldc.i4.1
0xda70  ldc.i4.1
0xda71  ldc.i4.1
0xda72  ldc.i4.1
0xda73  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters::.ctor(bool, bool, bool, bool, bool, bool, bool, bool, bool, bool)
0xda78  stloc.0
0xda79  ldarg.2
0xda7a  ldarg.1
0xda7b  ldc.i4.0
0xda7c  ldnull
0xda7d  ldloc.0
0xda7e  ldc.i4.1
0xda7f  ldc.i4.1
0xda80  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportXml::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, bool, class [mscorlib]System.Version, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters, bool, bool)
0xda85  callvirt instance unsigned int8[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportXml::RunExport()
0xda8a  ret
```
