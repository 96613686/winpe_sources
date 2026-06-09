# Microsoft.Crm.OnlineOnlyFileManager::ProcessFiles

- ea: `0x162e0`
- end: `0x16448`
- name: `Microsoft.Crm.OnlineOnlyFileManager::ProcessFiles`
- size: `360`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16210`
- `0x162c0`
- `0x162e0`

## callees

- `0x162e0`

## string_xrefs

- `0x16368`: `backupPath`
- `0x16385`: `Copying backup file to : {0}`
- `0x163a9`: `Copying file to : {0}`
- `0x163cb`: `Error copying to [`

## pseudocode

```c

```

## disassembly

```asm
0x162e0  ldarg.1
0x162e1  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x162e6  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x162eb  brtrue.s loc_162F9
0x162ed  ldarg.1
0x162ee  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x162f3  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x162f8  pop
0x162f9  ldarg.2
0x162fa  brfalse.s loc_16315
0x162fc  ldarg.2
0x162fd  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x16302  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x16307  brtrue.s loc_16315
0x16309  ldarg.2
0x1630a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1630f  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x16314  pop
0x16315  ldarg.0
0x16316  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x1631b  stloc.0
0x1631c  ldc.i4.0
0x1631d  stloc.1
0x1631e  br       loc_163ED
0x16323  ldloc.0
0x16324  ldloc.1
0x16325  ldelem.ref
0x16326  stloc.2
0x16327  ldarg.1
0x16328  callvirt instance string [mscorlib]System.Object::ToString()
0x1632d  ldloc.2
0x1632e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x16333  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16338  stloc.3
0x16339  ldloc.3
0x1633a  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x1633f  stloc.s  4
0x16341  ldloc.s  4
0x16343  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x16348  brfalse.s loc_1635B
0x1634a  ldloc.s  4
0x1634c  callvirt instance bool [mscorlib]System.IO.FileInfo::get_IsReadOnly()
0x16351  brfalse.s loc_1635B
0x16353  ldloc.s  4
0x16355  ldc.i4.0
0x16356  callvirt instance void [mscorlib]System.IO.FileInfo::set_IsReadOnly(bool)
0x1635b  ldloc.s  4
0x1635d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x16362  ldarg.s  5
0x16364  and
0x16365  brfalse.s loc_163A5
0x16367  ldarg.2
0x16368  ldstr    aBackuppath// "backupPath"
0x1636d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16372  ldarg.2
0x16373  callvirt instance string [mscorlib]System.Object::ToString()
0x16378  ldloc.2
0x16379  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x1637e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16383  stloc.s  5
0x16385  ldstr    aCopyingBackupF// "Copying backup file to : {0}"
0x1638a  ldc.i4.1
0x1638b  newarr   [mscorlib]System.Object
0x16390  dup
0x16391  ldc.i4.0
0x16392  ldloc.s  5
0x16394  stelem.ref
0x16395  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1639a  ldloc.s  4
0x1639c  ldloc.s  5
0x1639e  ldc.i4.1
0x1639f  callvirt instance class [mscorlib]System.IO.FileInfo [mscorlib]System.IO.FileInfo::CopyTo(string, bool)
0x163a4  pop
0x163a5  ldarg.s  4
0x163a7  brfalse.s loc_163C6
0x163a9  ldstr    aCopyingFileTo0// "Copying file to : {0}"
0x163ae  ldc.i4.1
0x163af  newarr   [mscorlib]System.Object
0x163b4  dup
0x163b5  ldc.i4.0
0x163b6  ldloc.3
0x163b7  stelem.ref
0x163b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x163bd  ldloc.2
0x163be  ldloc.3
0x163bf  ldc.i4.1
0x163c0  callvirt instance class [mscorlib]System.IO.FileInfo [mscorlib]System.IO.FileInfo::CopyTo(string, bool)
0x163c5  pop
0x163c6  leave.s  loc_163E9
0x163c8  stloc.s  6
0x163ca  ldarg.3
0x163cb  ldstr    aErrorCopyingTo// "Error copying to ["
0x163d0  ldloc.3
0x163d1  ldstr    asc_62F2E// "] : "
0x163d6  ldloc.s  6
0x163d8  callvirt instance string [mscorlib]System.Object::ToString()
0x163dd  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x163e2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x163e7  leave.s  loc_163E9
0x163e9  ldloc.1
0x163ea  ldc.i4.1
0x163eb  add
0x163ec  stloc.1
0x163ed  ldloc.1
0x163ee  ldloc.0
0x163ef  ldlen
0x163f0  conv.i4
0x163f1  blt      loc_16323
0x163f6  ldarg.0
0x163f7  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x163fc  stloc.s  7
0x163fe  ldc.i4.0
0x163ff  stloc.1
0x16400  br.s     loc_16440
0x16402  ldloc.s  7
0x16404  ldloc.1
0x16405  ldelem.ref
0x16406  stloc.s  8
0x16408  ldarg.1
0x16409  ldloc.s  8
0x1640b  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x16410  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::CreateSubdirectory(string)
0x16415  stloc.s  9
0x16417  ldnull
0x16418  stloc.s  0xA
0x1641a  ldarg.2
0x1641b  brfalse.s loc_1642C
0x1641d  ldarg.2
0x1641e  ldloc.s  8
0x16420  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x16425  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::CreateSubdirectory(string)
0x1642a  stloc.s  0xA
0x1642c  ldloc.s  8
0x1642e  ldloc.s  9
0x16430  ldloc.s  0xA
0x16432  ldarg.3
0x16433  ldarg.s  4
0x16435  ldarg.s  5
0x16437  call     void Microsoft.Crm.OnlineOnlyFileManager::ProcessFiles(class [mscorlib]System.IO.DirectoryInfo source, class [mscorlib]System.IO.DirectoryInfo target, class [mscorlib]System.IO.DirectoryInfo backupPath, class [mscorlib]System.Collections.Generic.List`1<string> errorList, bool performCopy, bool performBackup)
0x1643c  ldloc.1
0x1643d  ldc.i4.1
0x1643e  add
0x1643f  stloc.1
0x16440  ldloc.1
0x16441  ldloc.s  7
0x16443  ldlen
0x16444  conv.i4
0x16445  blt.s    loc_16402
0x16447  ret
```
