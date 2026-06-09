# Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GetDepthMask

- ea: `0x86720`
- end: `0x867b7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GetDepthMask`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x86470`

## callees

- `0x3a780`
- `0x3aa60`
- `0x86720`
- `0x867c0`

## string_xrefs

- `0x86721`: `privilegeid`
- `0x86764`: `privilegeid`
- `0x867a7`: `privilegedepthmask`

## pseudocode

```c

```

## disassembly

```asm
0x86720  ldarg.1
0x86721  ldstr    aPrivilegeid// "privilegeid"
0x86726  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8672b  unbox.any [mscorlib]System.Guid
0x86730  ldarg.0
0x86731  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::_prvReadOfficeGraphDocumentId
0x86736  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8673b  brfalse.s loc_86763
0x8673d  ldarg.0
0x8673e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::get_ExportToTargetVersionContext()
0x86743  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x86748  brfalse.s loc_86763
0x8674a  ldarg.0
0x8674b  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::get_ExportToTargetVersionContext()
0x86750  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x86755  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::NaosVersion
0x8675a  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x8675f  brfalse.s loc_86763
0x86761  ldc.i4.1
0x86762  ret
0x86763  ldarg.1
0x86764  ldstr    aPrivilegeid// "privilegeid"
0x86769  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8676e  unbox.any [mscorlib]System.Guid
0x86773  ldarg.0
0x86774  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::_prvReadSyncErrorId
0x86779  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8677e  brfalse.s loc_867A6
0x86780  ldarg.0
0x86781  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::get_ExportToTargetVersionContext()
0x86786  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x8678b  brfalse.s loc_867A6
0x8678d  ldarg.0
0x8678e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::get_ExportToTargetVersionContext()
0x86793  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x86798  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::NaosVersion
0x8679d  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x867a2  brfalse.s loc_867A6
0x867a4  ldc.i4.8
0x867a5  ret
0x867a6  ldarg.1
0x867a7  ldstr    aPrivilegedepth// "privilegedepthmask"
0x867ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x867b1  unbox.any [mscorlib]System.Int32
0x867b6  ret
```
