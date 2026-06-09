# Microsoft.Crm.Tools.Unzip.UnzipTool::RunUnzip

- ea: `0x400`
- end: `0x67b`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::RunUnzip`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x2e0`

## callees

- `0x10`
- `0x50`
- `0x80`
- `0xa0`
- `0x150`
- `0x170`
- `0x1f0`
- `0x200`
- `0x290`
- `0x400`
- `0x680`
- `0x6f0`
- `0xb10`
- `0xbe0`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x400  newobj   instance void Microsoft.Crm.ShellClass::.ctor()
0x405  stloc.0
0x406  ldloc.0
0x407  ldarg.0
0x408  ldfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::zipFilePath
0x40d  callvirt instance class Microsoft.Crm.Folder Microsoft.Crm.ShellClass::NameSpace([hasfieldmarshal] object)
0x412  stloc.1
0x413  ldarg.0
0x414  ldloc.1
0x415  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::GetImportableFiles(class Microsoft.Crm.Folder folder)
0x41a  stloc.2
0x41b  ldloc.2
0x41c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x421  brtrue.s loc_42A
0x423  ldc.i4.8
0x424  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x429  throw
0x42a  ldarg.0
0x42b  ldfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::unzipFolderPath
0x430  stloc.3
0x431  ldloc.1
0x432  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0x437  stloc.s  4
0x439  ldc.i4   0x3414
0x43e  stloc.s  5
0x440  ldloc.s  4
0x442  callvirt instance int32 Microsoft.Crm.FolderItems::get_Count()
0x447  ldc.i4.1
0x448  bne.un.s loc_4BD
0x44a  ldloc.s  4
0x44c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x451  stloc.s  0xC
0x453  br.s     loc_49D
0x455  ldloc.s  0xC
0x457  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x45c  castclass Microsoft.Crm.FolderItem
0x461  stloc.s  0xD
0x463  ldloc.s  0xD
0x465  callvirt instance bool Microsoft.Crm.FolderItem::get_IsFolder()
0x46a  brfalse.s loc_49D
0x46c  ldloc.s  0xD
0x46e  callvirt instance object Microsoft.Crm.FolderItem::get_GetFolder()
0x473  castclass Microsoft.Crm.Folder
0x478  stloc.s  0xE
0x47a  ldloc.3
0x47b  ldloc.s  0xE
0x47d  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x482  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x487  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x48c  stloc.3
0x48d  ldloc.3
0x48e  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x493  pop
0x494  ldloc.s  0xE
0x496  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0x49b  stloc.s  4
0x49d  ldloc.s  0xC
0x49f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a4  brtrue.s loc_455
0x4a6  leave.s  loc_4BD
0x4a8  ldloc.s  0xC
0x4aa  isinst   [mscorlib]System.IDisposable
0x4af  stloc.s  0xF
0x4b1  ldloc.s  0xF
0x4b3  brfalse.s loc_4BC
0x4b5  ldloc.s  0xF
0x4b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bc  endfinally
0x4bd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4c2  stloc.s  6
0x4c4  ldloc.s  4
0x4c6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4cb  stloc.s  0xC
0x4cd  br       loc_57B
0x4d2  ldloc.s  0xC
0x4d4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d9  castclass Microsoft.Crm.FolderItem
0x4de  stloc.s  0x10
0x4e0  ldloc.s  0x10
0x4e2  callvirt instance bool Microsoft.Crm.FolderItem::get_IsFolder()
0x4e7  brfalse  loc_57B
0x4ec  ldloc.s  0x10
0x4ee  callvirt instance object Microsoft.Crm.FolderItem::get_GetFolder()
0x4f3  castclass Microsoft.Crm.Folder
0x4f8  stloc.s  0x11
0x4fa  ldloc.s  0x11
0x4fc  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x501  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x506  ldstr    aAttachments// "Attachments"
0x50b  ldc.i4.5
0x50c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x511  brfalse.s loc_531
0x513  ldarg.0
0x514  ldc.i4.2
0x515  ldstr    aIgnoringFolder// "Ignoring folder {0} was found in zip wh"...
0x51a  ldc.i4.1
0x51b  newarr   [mscorlib]System.Object
0x520  dup
0x521  ldc.i4.0
0x522  ldloc.s  0x11
0x524  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x529  stelem.ref
0x52a  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x52f  br.s     loc_57B
0x531  ldloc.3
0x532  ldloc.s  0x11
0x534  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x539  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x53e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x543  stloc.s  0x12
0x545  ldloc.s  0x12
0x547  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x54c  pop
0x54d  ldloc.0
0x54e  ldloc.s  0x12
0x550  callvirt instance class Microsoft.Crm.Folder Microsoft.Crm.ShellClass::NameSpace([hasfieldmarshal] object)
0x555  ldloc.s  0x11
0x557  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0x55c  stloc.s  0x13
0x55e  ldloc.s  0x13
0x560  ldloc.s  5
0x562  box      [mscorlib]System.Int32
0x567  callvirt instance void Microsoft.Crm.Folder::CopyHere([in] [hasfieldmarshal] object vItem, [in] [opt] [hasfieldmarshal] object vOptions)
0x56c  ldloc.s  6
0x56e  ldarg.0
0x56f  ldloc.s  0x12
0x571  call     instance string[] Microsoft.Crm.Tools.Unzip.UnzipTool::GetFileListAndVerifySize(string directoryPath)
0x576  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x57b  ldloc.s  0xC
0x57d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x582  brtrue   loc_4D2
0x587  leave.s  loc_59E
0x589  ldloc.s  0xC
0x58b  isinst   [mscorlib]System.IDisposable
0x590  stloc.s  0xF
0x592  ldloc.s  0xF
0x594  brfalse.s loc_59D
0x596  ldloc.s  0xF
0x598  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59d  endfinally
0x59e  ldstr    asc_1150// "|"
0x5a3  ldarg.0
0x5a4  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::ValidFileTypes
0x5a9  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__12_0
0x5ae  dup
0x5af  brtrue.s loc_5C8
0x5b1  pop
0x5b2  ldsfld   class <>c <>c::<>9
0x5b7  ldftn    instance string <>c::<RunUnzip>b__12_0(string extension)
0x5bd  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x5c2  dup
0x5c3  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__12_0
0x5c8  call     T0x2B000001
0x5cd  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5d2  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.NameFilter::.ctor(string)
0x5d7  stloc.s  7
0x5d9  ldc.i4.0
0x5da  conv.i8
0x5db  ldarg.0
0x5dc  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x5e1  conv.i8
0x5e2  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.SizeFilter::.ctor(int64, int64)
0x5e7  stloc.s  8
0x5e9  ldstr    aAttachments// "Attachments"
0x5ee  ldc.i4.2
0x5ef  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.NameFilter::.ctor(string, valuetype [Xceed.FileSystem]Xceed.FileSystem.FilterScope)
0x5f4  stloc.s  9
0x5f6  ldc.i4.2
0x5f7  newarr   [mscorlib]System.Object
0x5fc  dup
0x5fd  ldc.i4.0
0x5fe  ldloc.s  9
0x600  stelem.ref
0x601  dup
0x602  ldc.i4.1
0x603  ldloc.s  7
0x605  stelem.ref
0x606  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.OrFilter::.ctor(object[])
0x60b  stloc.s  0xA
0x60d  ldc.i4.2
0x60e  newarr   [mscorlib]System.Object
0x613  dup
0x614  ldc.i4.0
0x615  ldloc.s  0xA
0x617  stelem.ref
0x618  dup
0x619  ldc.i4.1
0x61a  ldloc.s  8
0x61c  stelem.ref
0x61d  newobj   instance void [Xceed.FileSystem]Xceed.FileSystem.AndFilter::.ctor(object[])
0x622  stloc.s  0xB
0x624  newobj   instance void Microsoft.Crm.Tools.Unzip.XCeedUnzip::.ctor()
0x629  ldarg.0
0x62a  ldfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::zipFilePath
0x62f  ldarg.0
0x630  ldfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::unzipFolderPath
0x635  ldloc.s  0xB
0x637  ldsfld   string [mscorlib]System.String::Empty
0x63c  callvirt instance void Microsoft.Crm.Tools.Unzip.XCeedUnzip::ExtractZip(string zipFilename, string destFolder, class [Xceed.FileSystem]Xceed.FileSystem.Filter filter, string password)
0x641  ldloc.s  6
0x643  ldarg.0
0x644  ldloc.3
0x645  call     instance string[] Microsoft.Crm.Tools.Unzip.UnzipTool::GetFileListAndVerifySize(string directoryPath)
0x64a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x64f  ldloc.2
0x650  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x655  ldloc.s  6
0x657  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x65c  beq.s    loc_678
0x65e  ldarg.0
0x65f  ldc.i4.1
0x660  ldstr    aTheNumberOfFil// "The number of files in source zip file "...
0x665  ldc.i4.0
0x666  newarr   [mscorlib]System.Object
0x66b  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x670  ldc.i4.s 0xB
0x672  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x677  throw
0x678  ldloc.s  6
0x67a  ret
```
