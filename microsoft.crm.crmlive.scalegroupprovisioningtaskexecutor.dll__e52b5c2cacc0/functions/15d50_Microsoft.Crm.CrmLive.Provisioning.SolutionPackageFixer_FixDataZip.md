# Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::FixDataZip

- ea: `0x15d50`
- end: `0x15dbb`
- name: `Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::FixDataZip`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15bd0`

## callees

- `0x15d50`
- `0x15dc0`

## string_xrefs

- `0x15d56`: `TempSPFDataFile.xml`
- `0x15d81`: `data.xml`
- `0x15da0`: `data.xml`

## pseudocode

```c

```

## disassembly

```asm
0x15d50  ldarg.0
0x15d51  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x15d56  ldstr    aTempspfdatafil// "TempSPFDataFile.xml"
0x15d5b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15d60  stloc.0
0x15d61  ldloc.0
0x15d62  call     void [mscorlib]System.IO.File::Delete(string)
0x15d67  ldarg.1
0x15d68  ldstr    aFixdatazipForF// "FixDataZip for File : "
0x15d6d  ldarg.0
0x15d6e  call     string [mscorlib]System.String::Concat(string, string)
0x15d73  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x15d78  ldarg.0
0x15d79  ldc.i4.2
0x15d7a  call     class [System.IO.Compression]System.IO.Compression.ZipArchive [System.IO.Compression.FileSystem]System.IO.Compression.ZipFile::Open(string, valuetype [System.IO.Compression]System.IO.Compression.ZipArchiveMode)
0x15d7f  stloc.1
0x15d80  ldloc.1
0x15d81  ldstr    aDataXml// "data.xml"
0x15d86  callvirt instance class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry [System.IO.Compression]System.IO.Compression.ZipArchive::GetEntry(string)
0x15d8b  dup
0x15d8c  ldloc.0
0x15d8d  call     void [System.IO.Compression.FileSystem]System.IO.Compression.ZipFileExtensions::ExtractToFile(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, string)
0x15d92  ldloc.0
0x15d93  call     class Microsoft.Crm.CrmLive.Provisioning.ImportedRecord[] Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::FixDataInFile(string fileName)
0x15d98  stloc.2
0x15d99  callvirt instance void [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::Delete()
0x15d9e  ldloc.1
0x15d9f  ldloc.0
0x15da0  ldstr    aDataXml// "data.xml"
0x15da5  call     class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry [System.IO.Compression.FileSystem]System.IO.Compression.ZipFileExtensions::CreateEntryFromFile(class [System.IO.Compression]System.IO.Compression.ZipArchive, string, string)
0x15daa  pop
0x15dab  ldloc.2
0x15dac  stloc.3
0x15dad  leave.s  loc_15DB9
0x15daf  ldloc.1
0x15db0  brfalse.s loc_15DB8
0x15db2  ldloc.1
0x15db3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15db8  endfinally
0x15db9  ldloc.3
0x15dba  ret
```
