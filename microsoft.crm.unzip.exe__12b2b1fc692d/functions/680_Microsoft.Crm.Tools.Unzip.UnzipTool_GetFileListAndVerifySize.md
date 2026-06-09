# Microsoft.Crm.Tools.Unzip.UnzipTool::GetFileListAndVerifySize

- ea: `0x680`
- end: `0x6e7`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::GetFileListAndVerifySize`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x400`

## callees

- `0x290`
- `0x680`
- `0xb10`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldarg.1
0x681  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x686  stloc.0
0x687  ldloc.0
0x688  stloc.1
0x689  ldc.i4.0
0x68a  stloc.2
0x68b  br.s     loc_6DF
0x68d  ldloc.1
0x68e  ldloc.2
0x68f  ldelem.ref
0x690  stloc.3
0x691  ldloc.3
0x692  ldc.i4   0x80
0x697  call     void [mscorlib]System.IO.File::SetAttributes(string, valuetype [mscorlib]System.IO.FileAttributes)
0x69c  ldloc.3
0x69d  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x6a2  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x6a7  ldarg.0
0x6a8  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x6ad  conv.i8
0x6ae  ble.s    loc_6DB
0x6b0  ldarg.0
0x6b1  ldc.i4.1
0x6b2  ldstr    aSizeOf0FileIsM// "Size of {0} file is more than allowed {"...
0x6b7  ldc.i4.2
0x6b8  newarr   [mscorlib]System.Object
0x6bd  dup
0x6be  ldc.i4.0
0x6bf  ldloc.3
0x6c0  stelem.ref
0x6c1  dup
0x6c2  ldc.i4.1
0x6c3  ldarg.0
0x6c4  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x6c9  box      [mscorlib]System.Int32
0x6ce  stelem.ref
0x6cf  call     instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x6d4  ldc.i4.5
0x6d5  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor(int32 errorCode)
0x6da  throw
0x6db  ldloc.2
0x6dc  ldc.i4.1
0x6dd  add
0x6de  stloc.2
0x6df  ldloc.2
0x6e0  ldloc.1
0x6e1  ldlen
0x6e2  conv.i4
0x6e3  blt.s    loc_68D
0x6e5  ldloc.0
0x6e6  ret
```
