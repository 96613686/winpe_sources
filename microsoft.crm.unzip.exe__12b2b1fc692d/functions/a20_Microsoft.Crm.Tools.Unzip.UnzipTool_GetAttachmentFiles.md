# Microsoft.Crm.Tools.Unzip.UnzipTool::GetAttachmentFiles

- ea: `0xa20`
- end: `0xb0e`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::GetAttachmentFiles`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x6f0`

## callees

- `0x50`
- `0x130`
- `0x170`
- `0x1c0`
- `0x290`
- `0xa20`
- `0xb10`

## pseudocode

```c

```

## disassembly

```asm
0xa20  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xa25  stloc.0
0xa26  ldarg.1
0xa27  callvirt instance class Microsoft.Crm.FolderItems Microsoft.Crm.Folder::Items()
0xa2c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xa31  stloc.1
0xa32  br       loc_AEE
0xa37  ldloc.1
0xa38  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa3d  castclass Microsoft.Crm.FolderItem
0xa42  stloc.2
0xa43  ldloc.2
0xa44  callvirt instance bool Microsoft.Crm.FolderItem::get_IsFolder()
0xa49  brfalse.s loc_A53
0xa4b  ldc.i4.s 9
0xa4d  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xa52  throw
0xa53  ldloc.2
0xa54  callvirt instance int32 Microsoft.Crm.FolderItem::get_Size()
0xa59  ldc.i4.0
0xa5a  blt.s    loc_A6A
0xa5c  ldloc.2
0xa5d  callvirt instance int32 Microsoft.Crm.FolderItem::get_Size()
0xa62  ldarg.0
0xa63  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0xa68  ble.s    loc_A9A
0xa6a  ldarg.0
0xa6b  ldc.i4.1
0xa6c  ldstr    aSizeOf0Content// "Size of {0} content file is more than a"...
0xa71  ldc.i4.2
0xa72  newarr   [mscorlib]System.Object
0xa77  dup
0xa78  ldc.i4.0
0xa79  ldloc.2
0xa7a  callvirt instance string Microsoft.Crm.FolderItem::get_Path()
0xa7f  stelem.ref
0xa80  dup
0xa81  ldc.i4.1
0xa82  ldarg.0
0xa83  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0xa88  box      [mscorlib]System.Int32
0xa8d  stelem.ref
0xa8e  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0xa93  ldc.i4.5
0xa94  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xa99  throw
0xa9a  ldarg.0
0xa9b  ldarg.0
0xa9c  ldfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0xaa1  ldloc.2
0xaa2  callvirt instance int32 Microsoft.Crm.FolderItem::get_Size()
0xaa7  add
0xaa8  stfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0xaad  ldarg.0
0xaae  ldfld    unsigned int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeSizeCount
0xab3  ldarg.0
0xab4  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0xab9  ble.un.s loc_AE2
0xabb  ldarg.0
0xabc  ldc.i4.1
0xabd  ldstr    aCumulativeSize// "Cumulative Size of content files is mor"...
0xac2  ldc.i4.1
0xac3  newarr   [mscorlib]System.Object
0xac8  dup
0xac9  ldc.i4.0
0xaca  ldarg.0
0xacb  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0xad0  box      [mscorlib]System.Int32
0xad5  stelem.ref
0xad6  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0xadb  ldc.i4.5
0xadc  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0xae1  throw
0xae2  ldloc.0
0xae3  ldloc.2
0xae4  callvirt instance string Microsoft.Crm.FolderItem::get_Path()
0xae9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaee  ldloc.1
0xaef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xaf4  brtrue   loc_A37
0xaf9  leave.s  loc_B0C
0xafb  ldloc.1
0xafc  isinst   [mscorlib]System.IDisposable
0xb01  stloc.3
0xb02  ldloc.3
0xb03  brfalse.s loc_B0B
0xb05  ldloc.3
0xb06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb0b  endfinally
0xb0c  ldloc.0
0xb0d  ret
```
