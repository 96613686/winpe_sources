# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessPatchLabels

- ea: `0x6fc0`
- end: `0x704d`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessPatchLabels`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xded0`

## callees

- `0x6fc0`
- `0x7050`

## string_xrefs

- `0x6ffd`: `Actions_Org\Install\MetadataDiffs.xml`
- `0x7002`: `Actions_Org\Install\patch_newimport.xml`
- `0x702e`: `Actions_Org_LeoOptin\Install\leo_optin_metadatadiffs.xml`
- `0x7033`: `Actions_Org_LeoOptin\Install\patch_leo_optin_newimport.xml`

## pseudocode

```c

```

## disassembly

```asm
0x6fc0  ldarg.2
0x6fc1  ldstr    aMetadatahelper// "metadataHelper"
0x6fc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6fcb  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgReleaseFilePath()
0x6fd0  stloc.0
0x6fd1  ldloc.0
0x6fd2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6fd7  brfalse.s loc_6FDF
0x6fd9  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgSlipstreamReleaseFilePath()
0x6fde  stloc.0
0x6fdf  ldloc.0
0x6fe0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6fe5  brfalse.s loc_6FE8
0x6fe7  ret
0x6fe8  ldloc.0
0x6fe9  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x6fee  stloc.1
0x6fef  ldarg.0
0x6ff0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x6ff5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSystemOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ffa  stloc.2
0x6ffb  ldarg.0
0x6ffc  ldarg.1
0x6ffd  ldstr    aActionsOrgInst// "Actions_Org\\Install\\MetadataDiffs.xml"
0x7002  ldstr    aActionsOrgInst_0// "Actions_Org\\Install\\patch_newimport.x"...
0x7007  ldloc.1
0x7008  ldarg.2
0x7009  ldarg.3
0x700a  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessPatchLabels(int32 language, string metadataDiffRelPath, string newImportRelPath, string dbUpdateReleaseDirectory, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo)
0x700f  leave.s  loc_701B
0x7011  ldloc.2
0x7012  brfalse.s loc_701A
0x7014  ldloc.2
0x7015  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x701a  endfinally
0x701b  ldarg.0
0x701c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x7021  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.OptInSolutionConstants::LeoOptInSolutionId
0x7026  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoOptInOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid)
0x702b  stloc.3
0x702c  ldarg.0
0x702d  ldarg.1
0x702e  ldstr    aActionsOrgLeoo// "Actions_Org_LeoOptin\\Install\\leo_opti"...
0x7033  ldstr    aActionsOrgLeoo_0// "Actions_Org_LeoOptin\\Install\\patch_le"...
0x7038  ldloc.1
0x7039  ldarg.2
0x703a  ldarg.3
0x703b  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessPatchLabels(int32 language, string metadataDiffRelPath, string newImportRelPath, string dbUpdateReleaseDirectory, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo)
0x7040  leave.s  loc_704C
0x7042  ldloc.3
0x7043  brfalse.s loc_704B
0x7045  ldloc.3
0x7046  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x704b  endfinally
0x704c  ret
```
