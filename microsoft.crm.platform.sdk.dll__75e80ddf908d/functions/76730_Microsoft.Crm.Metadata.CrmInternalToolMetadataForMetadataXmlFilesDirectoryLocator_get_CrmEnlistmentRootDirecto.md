# Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_CrmEnlistmentRootDirectory

- ea: `0x76730`
- end: `0x767d3`
- name: `Microsoft.Crm.Metadata.CrmInternalToolMetadataForMetadataXmlFilesDirectoryLocator::get_CrmEnlistmentRootDirectory`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x766b0`

## callees

- `0x76730`

## string_xrefs

- `0x76764`: `directoryInfo`
- `0x767c2`: `directoryInfo`

## pseudocode

```c

```

## disassembly

```asm
0x76730  ldstr    aInetroot// "INETROOT"
0x76735  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x7673a  stloc.0
0x7673b  ldloc.0
0x7673c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x76741  brtrue.s loc_76745
0x76743  ldloc.0
0x76744  ret
0x76745  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x7674a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x7674f  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x76754  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x76759  stloc.1
0x7675a  br.s     loc_7676E
0x7675c  ldloc.1
0x7675d  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x76762  stloc.1
0x76763  ldloc.1
0x76764  ldstr    aDirectoryinfo// "directoryInfo"
0x76769  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7676e  ldstr    aSrc// "src"
0x76773  ldloc.1
0x76774  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x76779  ldc.i4.5
0x7677a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x7677f  brtrue.s loc_767BA
0x76781  ldstr    aDrop_0// "drop"
0x76786  ldloc.1
0x76787  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x7678c  ldc.i4.5
0x7678d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x76792  brtrue.s loc_767BA
0x76794  ldstr    aTarget// "target"
0x76799  ldloc.1
0x7679a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x7679f  ldc.i4.5
0x767a0  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x767a5  brtrue.s loc_767BA
0x767a7  ldstr    aBin// "bin"
0x767ac  ldloc.1
0x767ad  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x767b2  ldc.i4.5
0x767b3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x767b8  brfalse.s loc_7675C
0x767ba  ldloc.1
0x767bb  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x767c0  stloc.1
0x767c1  ldloc.1
0x767c2  ldstr    aDirectoryinfo// "directoryInfo"
0x767c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x767cc  ldloc.1
0x767cd  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x767d2  ret
```
