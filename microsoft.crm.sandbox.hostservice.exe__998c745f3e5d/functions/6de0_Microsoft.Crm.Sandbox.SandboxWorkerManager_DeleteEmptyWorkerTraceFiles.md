# Microsoft.Crm.Sandbox.SandboxWorkerManager::DeleteEmptyWorkerTraceFiles

- ea: `0x6de0`
- end: `0x6f3a`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::DeleteEmptyWorkerTraceFiles`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x6d20`

## callees

- `0x6de0`

## string_xrefs

- `0x6df6`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: trace directory does not exist: {0}`
- `0x6e12`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: trace directory found: {0}`
- `0x6e39`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: before: # trace files: {0}`
- `0x6e69`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: trace file: {0}`
- `0x6e95`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: delete trace file: {0}`
- `0x6ebd`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: trace file deleted OK: {0}`
- `0x6ee2`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: trace file delete failed: IOException: {0}`
- `0x6f1e`: `SandboxWorkerManager.DeleteEmptyWorkerTraceFiles: after: # trace files: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  ldarg.0
0x6de1  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x6de6  stloc.0
0x6de7  ldloc.0
0x6de8  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x6ded  brtrue.s loc_6E0B
0x6def  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6df4  ldc.i4.s 0x21
0x6df6  ldstr    aSandboxworkerm_30// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6dfb  ldc.i4.1
0x6dfc  newarr   [mscorlib]System.Object
0x6e01  dup
0x6e02  ldc.i4.0
0x6e03  ldarg.0
0x6e04  stelem.ref
0x6e05  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e0a  ret
0x6e0b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e10  ldc.i4.s 0x21
0x6e12  ldstr    aSandboxworkerm_31// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6e17  ldc.i4.1
0x6e18  newarr   [mscorlib]System.Object
0x6e1d  dup
0x6e1e  ldc.i4.0
0x6e1f  ldarg.0
0x6e20  stelem.ref
0x6e21  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e26  ldloc.0
0x6e27  ldstr    aMicrosoftCrmSa_1// "*Microsoft.Crm.Sandbox.WorkerProcess*.l"...
0x6e2c  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x6e31  stloc.1
0x6e32  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e37  ldc.i4.s 0x21
0x6e39  ldstr    aSandboxworkerm_32// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6e3e  ldc.i4.1
0x6e3f  newarr   [mscorlib]System.Object
0x6e44  dup
0x6e45  ldc.i4.0
0x6e46  ldloc.1
0x6e47  ldlen
0x6e48  conv.i4
0x6e49  box      [mscorlib]System.Int32
0x6e4e  stelem.ref
0x6e4f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e54  ldloc.1
0x6e55  stloc.2
0x6e56  ldc.i4.0
0x6e57  stloc.3
0x6e58  br       loc_6F02
0x6e5d  ldloc.2
0x6e5e  ldloc.3
0x6e5f  ldelem.ref
0x6e60  stloc.s  4
0x6e62  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e67  ldc.i4.s 0x21
0x6e69  ldstr    aSandboxworkerm_33// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6e6e  ldc.i4.1
0x6e6f  newarr   [mscorlib]System.Object
0x6e74  dup
0x6e75  ldc.i4.0
0x6e76  ldloc.s  4
0x6e78  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6e7d  stelem.ref
0x6e7e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e83  ldloc.s  4
0x6e85  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x6e8a  ldc.i4.0
0x6e8b  conv.i8
0x6e8c  bgt.s    loc_6EFE
0x6e8e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e93  ldc.i4.s 0x21
0x6e95  ldstr    aSandboxworkerm_34// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6e9a  ldc.i4.1
0x6e9b  newarr   [mscorlib]System.Object
0x6ea0  dup
0x6ea1  ldc.i4.0
0x6ea2  ldloc.s  4
0x6ea4  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6ea9  stelem.ref
0x6eaa  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6eaf  ldloc.s  4
0x6eb1  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x6eb6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ebb  ldc.i4.s 0x21
0x6ebd  ldstr    aSandboxworkerm_35// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6ec2  ldc.i4.1
0x6ec3  newarr   [mscorlib]System.Object
0x6ec8  dup
0x6ec9  ldc.i4.0
0x6eca  ldloc.s  4
0x6ecc  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6ed1  stelem.ref
0x6ed2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ed7  leave.s  loc_6EFE
0x6ed9  stloc.s  5
0x6edb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ee0  ldc.i4.s 0x21
0x6ee2  ldstr    aSandboxworkerm_36// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6ee7  ldc.i4.1
0x6ee8  newarr   [mscorlib]System.Object
0x6eed  dup
0x6eee  ldc.i4.0
0x6eef  ldloc.s  5
0x6ef1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6ef6  stelem.ref
0x6ef7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6efc  leave.s  loc_6EFE
0x6efe  ldloc.3
0x6eff  ldc.i4.1
0x6f00  add
0x6f01  stloc.3
0x6f02  ldloc.3
0x6f03  ldloc.2
0x6f04  ldlen
0x6f05  conv.i4
0x6f06  blt      loc_6E5D
0x6f0b  ldloc.0
0x6f0c  ldstr    aMicrosoftCrmSa_1// "*Microsoft.Crm.Sandbox.WorkerProcess*.l"...
0x6f11  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x6f16  stloc.1
0x6f17  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6f1c  ldc.i4.s 0x21
0x6f1e  ldstr    aSandboxworkerm_37// "SandboxWorkerManager.DeleteEmptyWorkerT"...
0x6f23  ldc.i4.1
0x6f24  newarr   [mscorlib]System.Object
0x6f29  dup
0x6f2a  ldc.i4.0
0x6f2b  ldloc.1
0x6f2c  ldlen
0x6f2d  conv.i4
0x6f2e  box      [mscorlib]System.Int32
0x6f33  stelem.ref
0x6f34  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6f39  ret
```
