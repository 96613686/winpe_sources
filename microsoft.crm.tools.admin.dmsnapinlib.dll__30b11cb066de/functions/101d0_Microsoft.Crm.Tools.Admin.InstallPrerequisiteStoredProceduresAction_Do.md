# Microsoft.Crm.Tools.Admin.InstallPrerequisiteStoredProceduresAction::Do

- ea: `0x101d0`
- end: `0x10217`
- name: `Microsoft.Crm.Tools.Admin.InstallPrerequisiteStoredProceduresAction::Do`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`

## string_xrefs

- `0x101e5`: `UpdateStoredProcedures.xml`

## pseudocode

```c

```

## disassembly

```asm
0x101d0  ldarg.1
0x101d1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x101d6  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgReleaseFilePath()
0x101db  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetActionFilePathFromReleaseFile(string)
0x101e0  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x101e5  ldstr    aUpdatestoredpr// "UpdateStoredProcedures.xml"
0x101ea  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x101ef  stloc.0
0x101f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x101f5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.StoredProcedureService::.ctor(valuetype [mscorlib]System.Guid)
0x101fa  ldstr    aServer// "SERVER"
0x101ff  ldstr    aMscrm// "mscrm"
0x10204  ldloc.0
0x10205  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.InstallationSequences>::.ctor()
0x1020a  dup
0x1020b  ldc.i4.5
0x1020c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.InstallationSequences>::Add(var<u1>)
0x10211  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.StoredProcedureService::InstallStoredProceduresUpdate(string, string, string, class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.InstallationSequences>)
0x10216  ret
```
