# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::CreateTempFilePath

- ea: `0x143e0`
- end: `0x144a5`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::CreateTempFilePath`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x141c0`
- `0x14280`

## callees

- `0x14090`
- `0x140d0`
- `0x143e0`

## pseudocode

```c

```

## disassembly

```asm
0x143e0  ldc.i4.1
0x143e1  stloc.0
0x143e2  br       loc_14472
0x143e7  ldstr    aTmp// ".tmp"
0x143ec  stloc.1
0x143ed  ldloc.0
0x143ee  ldc.i4.1
0x143ef  ble.s    loc_1440B
0x143f1  ldstr    aTmp0// ".tmp{0}"
0x143f6  ldc.i4.1
0x143f7  newarr   [mscorlib]System.Object
0x143fc  dup
0x143fd  ldc.i4.0
0x143fe  ldloc.0
0x143ff  box      [mscorlib]System.Int32
0x14404  stelem.ref
0x14405  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1440a  stloc.1
0x1440b  ldarg.1
0x1440c  ldc.i4.3
0x1440d  callvirt instance string [mscorlib]System.String::Substring(int32)
0x14412  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x14417  ldc.i4.s 0x25
0x14419  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x1441e  ldloc.1
0x1441f  call     string [mscorlib]System.String::Concat(string, string)
0x14424  stloc.2
0x14425  ldloc.2
0x14426  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1442b  ldarg.0
0x1442c  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_MaxTempFileNameLength()
0x14431  ble.s    loc_14457
0x14433  ldloc.2
0x14434  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14439  ldarg.0
0x1443a  call     instance int32 Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_MaxTempFileNameLength()
0x1443f  sub
0x14440  ldc.i4.1
0x14441  add
0x14442  stloc.s  4
0x14444  ldstr    asc_293E4// "~"
0x14449  ldloc.2
0x1444a  ldloc.s  4
0x1444c  callvirt instance string [mscorlib]System.String::Substring(int32)
0x14451  call     string [mscorlib]System.String::Concat(string, string)
0x14456  stloc.2
0x14457  ldarg.0
0x14458  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x1445d  ldloc.2
0x1445e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x14463  stloc.3
0x14464  ldloc.3
0x14465  call     bool [mscorlib]System.IO.File::Exists(string)
0x1446a  brtrue.s loc_1446E
0x1446c  ldloc.3
0x1446d  ret
0x1446e  ldloc.0
0x1446f  ldc.i4.1
0x14470  add
0x14471  stloc.0
0x14472  ldloc.0
0x14473  ldc.i4.s 0xA
0x14475  blt      loc_143E7
0x1447a  ldarg.0
0x1447b  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::get_LockedFileTempDirectoryPath()
0x14480  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x14485  stloc.s  5
0x14487  ldloca.s 5
0x14489  constrained. [mscorlib]System.Guid
0x1448f  callvirt instance string [mscorlib]System.Object::ToString()
0x14494  ldarg.1
0x14495  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1449a  ldstr    aTmp// ".tmp"
0x1449f  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x144a4  ret
```
