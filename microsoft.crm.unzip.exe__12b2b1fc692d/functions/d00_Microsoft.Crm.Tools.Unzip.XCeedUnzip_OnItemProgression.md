# Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemProgression

- ea: `0xd00`
- end: `0xd66`
- name: `Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemProgression`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xd00`

## string_xrefs

- `0xd28`: `Cannot extract outside of destination folder {0}`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarg.1
0xd01  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_TargetItem()
0xd06  brfalse.s loc_D39
0xd08  ldarg.1
0xd09  callvirt instance object [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_UserData()
0xd0e  isinst   [mscorlib]System.String
0xd13  stloc.0
0xd14  ldarg.1
0xd15  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_TargetItem()
0xd1a  callvirt instance string [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem::get_FullName()
0xd1f  ldloc.0
0xd20  ldc.i4.5
0xd21  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xd26  brtrue.s loc_D39
0xd28  ldstr    aCannotExtractO// "Cannot extract outside of destination f"...
0xd2d  ldloc.0
0xd2e  call     void [mscorlib]System.Console::WriteLine(string, object)
0xd33  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xd38  throw
0xd39  ldarg.1
0xd3a  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_CurrentItem()
0xd3f  brfalse.s loc_D65
0xd41  ldarg.1
0xd42  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.ProgressionInfo [Xceed.FileSystem]Xceed.FileSystem.ItemProgressionEventArgs::get_AllItems()
0xd47  callvirt instance unsigned int8 [Xceed.FileSystem]Xceed.FileSystem.ProgressionInfo::get_Percent()
0xd4c  ldc.i4.s 0x64
0xd4e  bge.s    loc_D65
0xd50  ldstr    aExtracting0// "Extracting {0}..."
0xd55  ldarg.1
0xd56  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_CurrentItem()
0xd5b  callvirt instance string [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem::get_FullName()
0xd60  call     void [mscorlib]System.Console::WriteLine(string, object)
0xd65  ret
```
