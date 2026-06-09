# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractZipContents

- ea: `0x15720`
- end: `0x1581c`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractZipContents`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15610`

## callees

- `0x15720`
- `0x15820`
- `0x16360`

## string_xrefs

- `0x15797`: `Zipfile entry paths should not start with \`
- `0x157b4`: `Directory {0} does not exist -- creating directory`

## pseudocode

```c

```

## disassembly

```asm
0x15720  ldstr    aExtracting0To1// "Extracting {0} to {1}"
0x15725  ldc.i4.2
0x15726  newarr   [mscorlib]System.Object
0x1572b  dup
0x1572c  ldc.i4.0
0x1572d  ldarg.1
0x1572e  stelem.ref
0x1572f  dup
0x15730  ldc.i4.1
0x15731  ldarg.2
0x15732  stelem.ref
0x15733  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15738  ldarg.1
0x15739  ldc.i4.0
0x1573a  call     class [System.IO.Compression]System.IO.Compression.ZipArchive [System.IO.Compression.FileSystem]System.IO.Compression.ZipFile::Open(string, valuetype [System.IO.Compression]System.IO.Compression.ZipArchiveMode)
0x1573f  stloc.0
0x15740  ldloc.0
0x15741  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry> [System.IO.Compression]System.IO.Compression.ZipArchive::get_Entries()
0x15746  stloc.1
0x15747  ldarg.0
0x15748  ldstr    aZipfileContain// "Zipfile contains {0} entries"
0x1574d  ldc.i4.1
0x1574e  newarr   [mscorlib]System.Object
0x15753  dup
0x15754  ldc.i4.0
0x15755  ldloc.1
0x15756  call     T0x2B00001A
0x1575b  box      [mscorlib]System.Int32
0x15760  stelem.ref
0x15761  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x15766  ldloc.1
0x15767  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry>::GetEnumerator()
0x1576c  stloc.2
0x1576d  br       loc_157FA
0x15772  ldloc.2
0x15773  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry>::get_Current()
0x15778  stloc.3
0x15779  ldarg.2
0x1577a  ldloc.3
0x1577b  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x15780  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15785  stloc.s  4
0x15787  ldloc.s  4
0x15789  ldstr    asc_2A676// "\\"
0x1578e  ldc.i4.5
0x1578f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x15794  ldc.i4.0
0x15795  ceq
0x15797  ldstr    aZipfileEntryPa// "Zipfile entry paths should not start wi"...
0x1579c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x157a1  ldloc.s  4
0x157a3  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x157a8  stloc.s  5
0x157aa  ldloc.s  5
0x157ac  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x157b1  brtrue.s loc_157D1
0x157b3  ldarg.0
0x157b4  ldstr    aDirectory0Does// "Directory {0} does not exist -- creatin"...
0x157b9  ldc.i4.1
0x157ba  newarr   [mscorlib]System.Object
0x157bf  dup
0x157c0  ldc.i4.0
0x157c1  ldloc.s  5
0x157c3  stelem.ref
0x157c4  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x157c9  ldloc.s  5
0x157cb  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x157d0  pop
0x157d1  ldarg.0
0x157d2  ldstr    aExtractingZipE// "Extracting zip entry {0} to {1}"
0x157d7  ldc.i4.2
0x157d8  newarr   [mscorlib]System.Object
0x157dd  dup
0x157de  ldc.i4.0
0x157df  ldloc.3
0x157e0  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x157e5  stelem.ref
0x157e6  dup
0x157e7  ldc.i4.1
0x157e8  ldloc.s  4
0x157ea  stelem.ref
0x157eb  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x157f0  ldarg.0
0x157f1  ldloc.3
0x157f2  ldloc.s  4
0x157f4  ldarg.3
0x157f5  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractFile(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry zipEntry, string entryTargetPath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x157fa  ldloc.2
0x157fb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15800  brtrue   loc_15772
0x15805  leave.s  loc_1581B
0x15807  ldloc.2
0x15808  brfalse.s loc_15810
0x1580a  ldloc.2
0x1580b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15810  endfinally
0x15811  ldloc.0
0x15812  brfalse.s loc_1581A
0x15814  ldloc.0
0x15815  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1581a  endfinally
0x1581b  ret
```
