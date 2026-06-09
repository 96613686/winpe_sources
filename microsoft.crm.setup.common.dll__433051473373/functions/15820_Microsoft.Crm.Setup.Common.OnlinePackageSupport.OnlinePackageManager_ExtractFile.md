# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractFile

- ea: `0x15820`
- end: `0x15975`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractFile`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15720`

## callees

- `0x143d0`
- `0x14f90`
- `0x15820`
- `0x15980`
- `0x16360`

## string_xrefs

- `0x1586f`: `   File is locked (HResult=0x{0:X8}).  Scheduling for replacement on next reboot`

## pseudocode

```c

```

## disassembly

```asm
0x15820  ldarg.2
0x15821  call     bool [mscorlib]System.IO.File::Exists(string)
0x15826  brfalse.s loc_15841
0x15828  ldarg.2
0x15829  call     valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.File::GetAttributes(string)
0x1582e  stloc.0
0x1582f  ldloc.0
0x15830  ldc.i4.1
0x15831  and
0x15832  ldc.i4.1
0x15833  bne.un.s loc_15841
0x15835  ldloc.0
0x15836  ldc.i4.s 0xFE
0x15838  and
0x15839  stloc.0
0x1583a  ldarg.2
0x1583b  ldloc.0
0x1583c  call     void [mscorlib]System.IO.File::SetAttributes(string, valuetype [mscorlib]System.IO.FileAttributes)
0x15841  ldc.i4.3
0x15842  stloc.1
0x15843  br       loc_1596D
0x15848  nop
0x15849  ldarg.0
0x1584a  ldarg.1
0x1584b  ldarg.2
0x1584c  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractFile(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry zipEntry, string entryTargetPath)
0x15851  ldc.i4.0
0x15852  stloc.1
0x15853  leave    loc_15969
0x15858  stloc.2
0x15859  ldc.i4.0
0x1585a  stloc.3
0x1585b  ldloc.2
0x1585c  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x15861  stloc.s  4
0x15863  ldarg.3
0x15864  brfalse.s loc_158A8
0x15866  ldloc.s  4
0x15868  call     bool Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::DoesHResultIndicateLockedFile(int32 hResult)
0x1586d  brfalse.s loc_158A8
0x1586f  ldstr    aFileIsLockedHr// "   File is locked (HResult=0x{0:X8}).  "...
0x15874  ldc.i4.1
0x15875  newarr   [mscorlib]System.Object
0x1587a  dup
0x1587b  ldc.i4.0
0x1587c  ldloc.s  4
0x1587e  box      [mscorlib]System.Int32
0x15883  stelem.ref
0x15884  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15889  ldarg.3
0x1588a  ldarg.1
0x1588b  ldarg.2
0x1588c  ldarg.0
0x1588d  ldftn    instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractFile(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry zipEntry, string entryTargetPath)
0x15893  newobj   instance void class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PopulateHoldingFile`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry>::.ctor(object, native int)
0x15898  callvirt T0x2B00001B
0x1589d  ldarg.0
0x1589e  ldc.i4.1
0x1589f  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RebootRequired(bool value)
0x158a4  ldc.i4.1
0x158a5  stloc.3
0x158a6  ldc.i4.0
0x158a7  stloc.1
0x158a8  ldloc.3
0x158a9  brtrue   loc_15967
0x158ae  ldarg.0
0x158af  ldstr    aErrorExtractin// "Error extracting {0} -- {1}: {2}, HResu"...
0x158b4  ldc.i4.4
0x158b5  newarr   [mscorlib]System.Object
0x158ba  dup
0x158bb  ldc.i4.0
0x158bc  ldarg.1
0x158bd  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x158c2  stelem.ref
0x158c3  dup
0x158c4  ldc.i4.1
0x158c5  ldloc.2
0x158c6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x158cb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x158d0  stelem.ref
0x158d1  dup
0x158d2  ldc.i4.2
0x158d3  ldloc.2
0x158d4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x158d9  stelem.ref
0x158da  dup
0x158db  ldc.i4.3
0x158dc  ldloc.2
0x158dd  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x158e2  box      [mscorlib]System.Int32
0x158e7  stelem.ref
0x158e8  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x158ed  ldloc.1
0x158ee  ldc.i4.1
0x158ef  bgt.s    loc_1592B
0x158f1  ldarg.0
0x158f2  ldstr    aRetryLimitExce// "Retry limit exceeded"
0x158f7  ldc.i4.0
0x158f8  newarr   [mscorlib]System.Object
0x158fd  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x15902  ldstr    aErrorExtractin_0// "Error extracting file zip entry {0}: {1"...
0x15907  ldc.i4.2
0x15908  newarr   [mscorlib]System.Object
0x1590d  dup
0x1590e  ldc.i4.0
0x1590f  ldarg.1
0x15910  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x15915  stelem.ref
0x15916  dup
0x15917  ldc.i4.1
0x15918  ldloc.2
0x15919  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1591e  stelem.ref
0x1591f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x15924  ldloc.2
0x15925  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x1592a  throw
0x1592b  ldsfld   class [mscorlib]System.Random Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::random
0x15930  ldc.i4.5
0x15931  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0x15936  ldc.i4.1
0x15937  add
0x15938  conv.r8
0x15939  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1593e  stloc.s  5
0x15940  ldarg.0
0x15941  ldstr    aRetryFileExtra// "Retry file extraction in {0} ms"
0x15946  ldc.i4.1
0x15947  newarr   [mscorlib]System.Object
0x1594c  dup
0x1594d  ldc.i4.0
0x1594e  ldloca.s 5
0x15950  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x15955  box      [mscorlib]System.Int32
0x1595a  stelem.ref
0x1595b  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::Log(string format, object[] args)
0x15960  ldloc.s  5
0x15962  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x15967  leave.s  loc_15969
0x15969  ldloc.1
0x1596a  ldc.i4.1
0x1596b  sub
0x1596c  stloc.1
0x1596d  ldloc.1
0x1596e  ldc.i4.1
0x1596f  bge      loc_15848
0x15974  ret
```
