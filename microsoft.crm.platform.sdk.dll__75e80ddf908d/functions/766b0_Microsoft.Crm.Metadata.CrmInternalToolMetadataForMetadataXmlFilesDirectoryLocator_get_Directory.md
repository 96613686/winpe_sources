# Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_Directory

- ea: `0x766b0`
- end: `0x76717`
- name: `Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_Directory`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x766b0`
- `0x76720`
- `0x76730`

## string_xrefs

- `0x766c0`: `rootServerInstallationDirectoryrootSrcDirectory`
- `0x766f5`: `rootServerInstallationDirectoryrootSrcDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x766b0  ldarg.0
0x766b1  ldfld    string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::_directory
0x766b6  brtrue.s loc_76710
0x766b8  ldarg.0
0x766b9  call     instance string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_CrmEnlistmentRootDirectory()
0x766be  stloc.0
0x766bf  ldloc.0
0x766c0  ldstr    aRootserverinst// "rootServerInstallationDirectoryrootSrcD"...
0x766c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x766ca  ldarg.0
0x766cb  ldloc.0
0x766cc  ldstr    aSrcCoreDataDat// "src\\Core\\Data\\Database\\MetadataForM"...
0x766d1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x766d6  stfld    string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::_directory
0x766db  ldarg.0
0x766dc  ldfld    string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::_directory
0x766e1  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x766e6  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x766eb  brtrue.s loc_76710
0x766ed  ldarg.0
0x766ee  call     instance string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_PlatformFilesRootDirectory()
0x766f3  stloc.0
0x766f4  ldloc.0
0x766f5  ldstr    aRootserverinst// "rootServerInstallationDirectoryrootSrcD"...
0x766fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x766ff  ldarg.0
0x76700  ldloc.0
0x76701  ldstr    aLibNet452Datab// "lib\\net452\\DatabaseNonBinaries\\Core"...
0x76706  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7670b  stfld    string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::_directory
0x76710  ldarg.0
0x76711  ldfld    string Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::_directory
0x76716  ret
```
