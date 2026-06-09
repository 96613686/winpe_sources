# Microsoft.Crm.Tools.Unzip.UnzipTool::GetImportableFiles

- ea: `0x6f0`
- end: `0x9d1`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::GetImportableFiles`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x400`

## callees

- `0x10`
- `0x50`
- `0xa0`
- `0x130`
- `0x150`
- `0x170`
- `0x1c0`
- `0x290`
- `0x6f0`
- `0x9e0`
- `0xa20`
- `0xb10`

## string_xrefs

- `0x75e`: `An attachment folder was found in an unsupported directory structure`
- `0x791`: `An invalid directory traversal was attempted in the zip structure`
- `0x84b`: `An invalid directory traversal was attempted in the zip structure`
- `0x92c`: `Files with extension '{0}' are not allowed for import. only 'csv' or' xml' files are allowed`
- `0x977`: `A zip file should contain all 'csv', all 'xml', or all 'xlsx' files. The given zip file for import has mix of both which is not allowed.`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldnull
0x6f1  stloc.0
0x6f2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6f7  stloc.1
0x6f8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6fd  stloc.2
0x6fe  ldarg.1
0x6ff  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0x704  stloc.3
0x705  ldloc.3
0x706  callvirt instance int32 Microsoft.Crm.FolderItems::get_Count()
0x70b  ldc.i4.1
0x70c  bne.un   loc_7D4
0x711  ldloc.3
0x712  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x717  stloc.s  4
0x719  br       loc_7B1
0x71e  ldloc.s  4
0x720  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x725  castclass Microsoft.Crm.FolderItem
0x72a  stloc.s  5
0x72c  ldloc.s  5
0x72e  callvirt instance bool Microsoft.Crm.FolderItem::get_IsFolder()
0x733  brfalse.s loc_7B1
0x735  ldloc.s  5
0x737  callvirt instance object Microsoft.Crm.FolderItem::get_GetFolder()
0x73c  castclass Microsoft.Crm.Folder
0x741  stloc.s  6
0x743  ldloc.s  6
0x745  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x74a  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x74f  ldstr    aAttachments// "Attachments"
0x754  ldc.i4.5
0x755  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x75a  brtrue.s loc_776
0x75c  ldarg.0
0x75d  ldc.i4.1
0x75e  ldstr    aAnAttachmentFo// "An attachment folder was found in an un"...
0x763  ldc.i4.0
0x764  newarr   [mscorlib]System.Object
0x769  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x76e  ldc.i4.s 0xC
0x770  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x775  throw
0x776  ldloc.s  6
0x778  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x77d  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x782  ldstr    asc_12E2// ".."
0x787  ldc.i4.5
0x788  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x78d  brtrue.s loc_7A9
0x78f  ldarg.0
0x790  ldc.i4.1
0x791  ldstr    aAnInvalidDirec// "An invalid directory traversal was atte"...
0x796  ldc.i4.0
0x797  newarr   [mscorlib]System.Object
0x79c  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x7a1  ldc.i4.s 0xC
0x7a3  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x7a8  throw
0x7a9  ldloc.s  6
0x7ab  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0x7b0  stloc.3
0x7b1  ldloc.s  4
0x7b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7b8  brtrue   loc_71E
0x7bd  leave.s  loc_7D4
0x7bf  ldloc.s  4
0x7c1  isinst   [mscorlib]System.IDisposable
0x7c6  stloc.s  7
0x7c8  ldloc.s  7
0x7ca  brfalse.s loc_7D3
0x7cc  ldloc.s  7
0x7ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d3  endfinally
0x7d4  ldloc.3
0x7d5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7da  stloc.s  4
0x7dc  br       loc_996
0x7e1  ldloc.s  4
0x7e3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7e8  castclass Microsoft.Crm.FolderItem
0x7ed  stloc.s  8
0x7ef  ldloc.s  8
0x7f1  callvirt instance bool Microsoft.Crm.FolderItem::get_IsFolder()
0x7f6  brfalse  loc_884
0x7fb  ldloc.s  8
0x7fd  callvirt instance object Microsoft.Crm.FolderItem::get_GetFolder()
0x802  castclass Microsoft.Crm.Folder
0x807  stloc.s  0xB
0x809  ldloc.s  0xB
0x80b  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x810  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x815  ldstr    aAttachments// "Attachments"
0x81a  ldc.i4.5
0x81b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x820  brtrue.s loc_830
0x822  ldarg.0
0x823  ldloc.s  0xB
0x825  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::GetAttachmentFiles(class Microsoft.Crm.Folder attachmentsFolder)
0x82a  stloc.2
0x82b  br       loc_996
0x830  ldloc.s  0xB
0x832  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x837  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x83c  ldstr    asc_12E2// ".."
0x841  ldc.i4.5
0x842  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x847  brtrue.s loc_863
0x849  ldarg.0
0x84a  ldc.i4.1
0x84b  ldstr    aAnInvalidDirec// "An invalid directory traversal was atte"...
0x850  ldc.i4.0
0x851  newarr   [mscorlib]System.Object
0x856  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x85b  ldc.i4.s 0xC
0x85d  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x862  throw
0x863  ldarg.0
0x864  ldc.i4.2
0x865  ldstr    aAFolder0WasFou// "A folder {0} was found in zip which was"...
0x86a  ldc.i4.1
0x86b  newarr   [mscorlib]System.Object
0x870  dup
0x871  ldc.i4.0
0x872  ldloc.s  0xB
0x874  callvirt instance string Microsoft.Crm.Folder::get_Title()
0x879  stelem.ref
0x87a  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x87f  br       loc_996
0x884  ldloc.s  8
0x886  callvirt instance int32 Microsoft.Crm.FolderItem::get_Size()
0x88b  ldarg.0
0x88c  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x891  ble.s    loc_8BA
0x893  ldarg.0
0x894  ldc.i4.1
0x895  ldstr    aMaxAllowedSize// "Max allowed size of content file is {0}"...
0x89a  ldc.i4.1
0x89b  newarr   [mscorlib]System.Object
0x8a0  dup
0x8a1  ldc.i4.0
0x8a2  ldarg.0
0x8a3  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x8a8  box      [mscorlib]System.Int32
0x8ad  stelem.ref
0x8ae  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x8b3  ldc.i4.5
0x8b4  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x8b9  throw
0x8ba  ldarg.0
0x8bb  ldarg.0
0x8bc  ldfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0x8c1  ldloc.s  8
0x8c3  callvirt instance int32 Microsoft.Crm.FolderItem::get_Size()
0x8c8  add
0x8c9  stfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0x8ce  ldarg.0
0x8cf  ldfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0x8d4  conv.u8
0x8d5  ldarg.0
0x8d6  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0x8db  conv.i8
0x8dc  ble.s    loc_905
0x8de  ldarg.0
0x8df  ldc.i4.1
0x8e0  ldstr    aMaxAllowedTota// "Max allowed total size of all files is "...
0x8e5  ldc.i4.1
0x8e6  newarr   [mscorlib]System.Object
0x8eb  dup
0x8ec  ldc.i4.0
0x8ed  ldarg.0
0x8ee  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0x8f3  box      [mscorlib]System.Int32
0x8f8  stelem.ref
0x8f9  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x8fe  ldc.i4.5
0x8ff  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x904  throw
0x905  ldloc.s  8
0x907  callvirt instance string Microsoft.Crm.FolderItem::get_Path()
0x90c  stloc.s  9
0x90e  ldloc.s  9
0x910  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x915  stloc.s  0xA
0x917  ldloc.s  0xA
0x919  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x91e  brtrue.s loc_95D
0x920  ldarg.0
0x921  ldloc.s  0xA
0x923  call     instance bool Microsoft.Crm.Tools.Unzip.UnzipTool::ValidateFileType(string fileExtension)
0x928  brtrue.s loc_95D
0x92a  ldarg.0
0x92b  ldc.i4.1
0x92c  ldstr    aFilesWithExten// "Files with extension '{0}' are not allo"...
0x931  ldc.i4.1
0x932  newarr   [mscorlib]System.Object
0x937  dup
0x938  ldc.i4.0
0x939  ldloc.s  0xA
0x93b  stelem.ref
0x93c  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x941  ldloc.s  0xA
0x943  ldstr    aZip// ".zip"
0x948  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94d  brfalse.s loc_956
0x94f  ldc.i4.4
0x950  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x955  throw
0x956  ldc.i4.6
0x957  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x95c  throw
0x95d  ldloc.0
0x95e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x963  brfalse.s loc_96A
0x965  ldloc.s  0xA
0x967  stloc.0
0x968  br.s     loc_98E
0x96a  ldloc.s  0xA
0x96c  ldloc.0
0x96d  ldc.i4.5
0x96e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x973  brfalse.s loc_98E
0x975  ldarg.0
0x976  ldc.i4.1
0x977  ldstr    aAZipFileShould// "A zip file should contain all 'csv', al"...
0x97c  ldc.i4.0
0x97d  newarr   [mscorlib]System.Object
0x982  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x987  ldc.i4.7
0x988  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x98d  throw
0x98e  ldloc.1
0x98f  ldloc.s  9
0x991  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x996  ldloc.s  4
0x998  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x99d  brtrue   loc_7E1
0x9a2  leave.s  loc_9B9
0x9a4  ldloc.s  4
0x9a6  isinst   [mscorlib]System.IDisposable
0x9ab  stloc.s  7
0x9ad  ldloc.s  7
0x9af  brfalse.s loc_9B8
0x9b1  ldloc.s  7
0x9b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9b8  endfinally
0x9b9  ldloc.1
0x9ba  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x9bf  brtrue.s loc_9C8
0x9c1  ldc.i4.8
0x9c2  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x9c7  throw
0x9c8  ldloc.1
0x9c9  ldloc.2
0x9ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9cf  ldloc.1
0x9d0  ret
```
