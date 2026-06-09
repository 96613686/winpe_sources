# Microsoft.Crm.CrmPluginAssemblyMetadata::LoadMetadataFromAssemblyFile

- ea: `0x1db30`
- end: `0x1db76`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::LoadMetadataFromAssemblyFile`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1db30`
- `0x1db80`
- `0x1dbb0`
- `0x1de90`

## string_xrefs

- `0x1db31`: `fullFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x1db30  ldarg.1
0x1db31  ldstr    aFullfilepath// "fullFilePath"
0x1db36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1db3b  ldarg.0
0x1db3c  ldarg.0
0x1db3d  ldarg.1
0x1db3e  call     instance class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::OpenScopeForAssemblyOnDisk(string fullFilePath)
0x1db43  stfld    class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaImport
0x1db48  ldarg.0
0x1db49  ldarg.0
0x1db4a  ldfld    class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaImport
0x1db4f  castclass Microsoft.Crm.IMetaDataAssemblyImport
0x1db54  stfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1db59  ldarg.0
0x1db5a  ldarg.1
0x1db5b  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1db60  stfld    string Microsoft.Crm.CrmPluginAssemblyMetadata::_appBaseDirectory
0x1db65  ldarg.0
0x1db66  ldarg.2
0x1db67  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::LoadRequiredMetadata([opt] bool loadAllMetadata)
0x1db6c  leave.s  loc_1DB75
0x1db6e  ldarg.0
0x1db6f  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::Cleanup()
0x1db74  endfinally
0x1db75  ret
```
