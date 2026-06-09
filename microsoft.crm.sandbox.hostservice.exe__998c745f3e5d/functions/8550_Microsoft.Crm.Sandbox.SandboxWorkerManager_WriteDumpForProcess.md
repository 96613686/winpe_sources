# Microsoft.Crm.Sandbox.SandboxWorkerManager::WriteDumpForProcess

- ea: `0x8550`
- end: `0x85af`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::WriteDumpForProcess`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8230`

## callees

- `0x50c0`
- `0x8550`
- `0x98e0`

## pseudocode

```c

```

## disassembly

```asm
0x8550  ldarg.2
0x8551  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x8556  brtrue.s loc_855F
0x8558  ldarg.2
0x8559  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x855e  pop
0x855f  ldarg.3
0x8560  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Create(string)
0x8565  stloc.0
0x8566  ldarg.0
0x8567  ldc.i4.1
0x8568  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_IsProcessDumpInProgress(bool value)
0x856d  ldarg.1
0x856e  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetProcessById(int32)
0x8573  callvirt instance native int [System]System.Diagnostics.Process::get_Handle()
0x8578  ldarg.1
0x8579  ldloc.0
0x857a  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle [mscorlib]System.IO.FileStream::get_SafeFileHandle()
0x857f  ldarg.s  4
0x8581  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8586  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x858b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8590  call     bool Microsoft.Crm.Sandbox.NativeMethods::MiniDumpWriteDump([hasfieldmarshal] native int, [in] unsigned int32 hProcess, class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle ProcessId, valuetype Microsoft.Crm.Sandbox.DumpTypes hFile, native int DumpType, [in] native int ExceptionParam, [in] native int UserStreamParam)
0x8595  brtrue.s loc_85A2
0x8597  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x859c  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x85a1  throw
0x85a2  leave.s  loc_85AE
0x85a4  ldloc.0
0x85a5  brfalse.s loc_85AD
0x85a7  ldloc.0
0x85a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85ad  endfinally
0x85ae  ret
```
