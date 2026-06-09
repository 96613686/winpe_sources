# Microsoft.Crm.Tools.Unzip.XCeedUnzip::ExtractZip

- ea: `0xbe0`
- end: `0xcf3`
- name: `Microsoft.Crm.Tools.Unzip.XCeedUnzip::ExtractZip`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x400`

## callees

- `0x290`
- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0xbe0  ldarg.1
0xbe1  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.DiskFile::.ctor(string)
0xbe6  stloc.0
0xbe7  ldloc.0
0xbe8  callvirt instance bool [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem::get_Exists()
0xbed  brtrue.s loc_BFA
0xbef  ldstr    aTheSpecifiedZi// "The specified zip file does not exist."
0xbf4  call     void [mscorlib]System.Console::WriteLine(string)
0xbf9  ret
0xbfa  ldstr    aExtractingAllF// "Extracting all files to folder \"{0}\" "...
0xbff  ldarg.2
0xc00  call     void [mscorlib]System.Console::WriteLine(string, object)
0xc05  call     void [mscorlib]System.Console::WriteLine()
0xc0a  ldloc.0
0xc0b  newobj   instance void [Xceed.Zip]Xceed.Zip.ZipArchive::.ctor(class [Xceed.FileSystem]Xceed.FileSystem.AbstractFile)
0xc10  stloc.1
0xc11  ldloc.1
0xc12  ldarg.s  4
0xc14  callvirt instance void [Xceed.Zip]Xceed.Zip.ZipArchive::set_DefaultDecryptionPassword(string)
0xc19  ldarg.2
0xc1a  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.DiskFolder::.ctor(string)
0xc1f  stloc.2
0xc20  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.FileSystemEvents::.ctor()
0xc25  stloc.3
0xc26  ldloc.3
0xc27  ldnull
0xc28  ldftn    void Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemProgression(object sender, class [Xceed.FileSystem]Xceed.FileSystem.ItemProgressionEventArgs e)
0xc2e  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.ItemProgressionEventHandler::.ctor(object, native int)
0xc33  callvirt instance void [Xceed.FileSystem]Xceed.FileSystem.FileSystemEvents::add_ItemProgression(class [Xceed.FileSystem]Xceed.FileSystem.ItemProgressionEventHandler)
0xc38  ldloc.3
0xc39  ldnull
0xc3a  ldftn    void Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemException(object sender, class [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionEventArgs e)
0xc40  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionEventHandler::.ctor(object, native int)
0xc45  callvirt instance void [Xceed.FileSystem]Xceed.FileSystem.FileSystemEvents::add_ItemException(class [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionEventHandler)
0xc4a  ldarg.2
0xc4b  ldstr    asc_1920// "\\"
0xc50  ldc.i4.5
0xc51  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xc56  brtrue.s loc_C65
0xc58  ldarg.2
0xc59  ldstr    asc_1920// "\\"
0xc5e  call     string [mscorlib]System.String::Concat(string, string)
0xc63  br.s     loc_C66
0xc65  ldarg.2
0xc66  stloc.s  4
0xc68  ldloc.1
0xc69  ldc.i4.1
0xc6a  ldc.i4.0
0xc6b  newarr   [mscorlib]System.Object
0xc70  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.AbstractFile[] [Xceed.FileSystem]Xceed.FileSystem.AbstractFolder::GetFiles(bool, object[])
0xc75  stloc.s  5
0xc77  ldc.i4.0
0xc78  stloc.s  6
0xc7a  br.s     loc_CC0
0xc7c  ldloc.s  5
0xc7e  ldloc.s  6
0xc80  ldelem.ref
0xc81  stloc.s  7
0xc83  ldloc.s  4
0xc85  ldloc.s  7
0xc87  callvirt instance string [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem::get_FullName()
0xc8c  call     string [mscorlib]System.String::Concat(string, string)
0xc91  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0xc96  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xc9b  stloc.s  8
0xc9d  leave.s  loc_CA7
0xc9f  pop
0xca0  ldc.i4.6
0xca1  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xca6  throw
0xca7  ldloc.s  8
0xca9  ldloc.s  4
0xcab  ldc.i4.5
0xcac  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xcb1  brtrue.s loc_CBA
0xcb3  ldc.i4.6
0xcb4  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xcb9  throw
0xcba  ldloc.s  6
0xcbc  ldc.i4.1
0xcbd  add
0xcbe  stloc.s  6
0xcc0  ldloc.s  6
0xcc2  ldloc.s  5
0xcc4  ldlen
0xcc5  conv.i4
0xcc6  blt.s    loc_C7C
0xcc8  nop
0xcc9  ldloc.1
0xcca  ldloc.3
0xccb  ldloc.s  4
0xccd  ldloc.2
0xcce  ldc.i4.1
0xccf  ldc.i4.1
0xcd0  ldc.i4.1
0xcd1  newarr   [mscorlib]System.Object
0xcd6  dup
0xcd7  ldc.i4.0
0xcd8  ldarg.3
0xcd9  stelem.ref
0xcda  callvirt instance void [Xceed.FileSystem]Xceed.FileSystem.AbstractFolder::CopyFilesTo(class [Xceed.FileSystem]Xceed.FileSystem.FileSystemEvents, object, class [Xceed.FileSystem]Xceed.FileSystem.AbstractFolder, bool, bool, object[])
0xcdf  leave.s  loc_CF2
0xce1  pop
0xce2  ldc.i4.s 0xD
0xce4  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xce9  throw
0xcea  pop
0xceb  ldc.i4.6
0xcec  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xcf1  throw
0xcf2  ret
```
