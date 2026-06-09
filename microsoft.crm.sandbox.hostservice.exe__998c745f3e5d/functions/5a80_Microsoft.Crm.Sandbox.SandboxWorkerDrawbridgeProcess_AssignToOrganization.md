# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::AssignToOrganization

- ea: `0x5a80`
- end: `0x5bae`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::AssignToOrganization`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x5040`
- `0x5a60`
- `0x5a80`
- `0x9730`
- `0x9770`

## string_xrefs

- `0x5aa1`: `AssemblyCache`
- `0x5af2`: `SandboxWorkerDrawbridgeProcess.AssignToOrganization: Folder {0} already exists for sandbox worker {1}`
- `0x5b20`: `SandboxWorkerDrawbridgeProcess.AssignToOrganization: Folder {0} didn't exists on host, creating it and linking it to {1}`
- `0x5b51`: `SandboxWorkerDrawbridgeProcess.AssignToOrganization: Successfully created link between {0} and {1}`
- `0x5b7e`: `SandboxWorkerDrawbridgeProcess.AssignToOrganization: Error creating link between {0} and {1}. Error id {2}, Message {3}`

## pseudocode

```c

```

## disassembly

```asm
0x5a80  ldc.i4.5
0x5a81  newarr   [mscorlib]System.String
0x5a86  dup
0x5a87  ldc.i4.0
0x5a88  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath()
0x5a8d  stelem.ref
0x5a8e  dup
0x5a8f  ldc.i4.1
0x5a90  ldarg.0
0x5a91  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5a96  stelem.ref
0x5a97  dup
0x5a98  ldc.i4.2
0x5a99  ldstr    aMscrmRo// "MSCRM_RO"
0x5a9e  stelem.ref
0x5a9f  dup
0x5aa0  ldc.i4.3
0x5aa1  ldstr    aAssemblycache// "AssemblyCache"
0x5aa6  stelem.ref
0x5aa7  dup
0x5aa8  ldc.i4.4
0x5aa9  ldarg.0
0x5aaa  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5aaf  stloc.2
0x5ab0  ldloca.s 2
0x5ab2  ldstr    aB// "B"
0x5ab7  call     instance string [mscorlib]System.Guid::ToString(string)
0x5abc  stelem.ref
0x5abd  call     string [mscorlib]System.IO.Path::Combine(string[])
0x5ac2  stloc.0
0x5ac3  ldnull
0x5ac4  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x5ac9  ldarg.0
0x5aca  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5acf  stloc.2
0x5ad0  ldloca.s 2
0x5ad2  ldstr    aB// "B"
0x5ad7  call     instance string [mscorlib]System.Guid::ToString(string)
0x5adc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5ae1  stloc.1
0x5ae2  ldloc.0
0x5ae3  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x5ae8  brfalse.s loc_5B10
0x5aea  ldarg.0
0x5aeb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5af0  ldc.i4.s 0x21
0x5af2  ldstr    aSandboxworkerd// "SandboxWorkerDrawbridgeProcess.AssignTo"...
0x5af7  ldc.i4.2
0x5af8  newarr   [mscorlib]System.Object
0x5afd  dup
0x5afe  ldc.i4.0
0x5aff  ldloc.0
0x5b00  stelem.ref
0x5b01  dup
0x5b02  ldc.i4.1
0x5b03  ldarg.0
0x5b04  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x5b09  stelem.ref
0x5b0a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5b0f  ret
0x5b10  ldloc.1
0x5b11  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x5b16  brtrue.s loc_5B3F
0x5b18  ldarg.0
0x5b19  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5b1e  ldc.i4.s 0x21
0x5b20  ldstr    aSandboxworkerd_0// "SandboxWorkerDrawbridgeProcess.AssignTo"...
0x5b25  ldc.i4.2
0x5b26  newarr   [mscorlib]System.Object
0x5b2b  dup
0x5b2c  ldc.i4.0
0x5b2d  ldloc.1
0x5b2e  stelem.ref
0x5b2f  dup
0x5b30  ldc.i4.1
0x5b31  ldloc.0
0x5b32  stelem.ref
0x5b33  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5b38  ldloc.1
0x5b39  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5b3e  pop
0x5b3f  ldloc.0
0x5b40  ldloc.1
0x5b41  ldc.i4.1
0x5b42  call     bool Microsoft.Crm.Sandbox.NativeMethods::CreateSymbolicLink(string lpSymlinkFileName, string lpTargetFileName, valuetype Microsoft.Crm.Sandbox.SymbolicLink dwFlags)
0x5b47  brfalse.s loc_5B6A
0x5b49  ldarg.0
0x5b4a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5b4f  ldc.i4.s 0x21
0x5b51  ldstr    aSandboxworkerd_1// "SandboxWorkerDrawbridgeProcess.AssignTo"...
0x5b56  ldc.i4.2
0x5b57  newarr   [mscorlib]System.Object
0x5b5c  dup
0x5b5d  ldc.i4.0
0x5b5e  ldloc.1
0x5b5f  stelem.ref
0x5b60  dup
0x5b61  ldc.i4.1
0x5b62  ldloc.0
0x5b63  stelem.ref
0x5b64  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5b69  ret
0x5b6a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5b6f  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5b74  stloc.3
0x5b75  ldnull
0x5b76  ldarg.0
0x5b77  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x5b7c  ldc.i4.s 0x21
0x5b7e  ldstr    aSandboxworkerd_2// "SandboxWorkerDrawbridgeProcess.AssignTo"...
0x5b83  ldc.i4.4
0x5b84  newarr   [mscorlib]System.Object
0x5b89  dup
0x5b8a  ldc.i4.0
0x5b8b  ldloc.1
0x5b8c  stelem.ref
0x5b8d  dup
0x5b8e  ldc.i4.1
0x5b8f  ldloc.0
0x5b90  stelem.ref
0x5b91  dup
0x5b92  ldc.i4.2
0x5b93  ldloc.3
0x5b94  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x5b99  box      [mscorlib]System.Int32
0x5b9e  stelem.ref
0x5b9f  dup
0x5ba0  ldc.i4.3
0x5ba1  ldloc.3
0x5ba2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5ba7  stelem.ref
0x5ba8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5bad  ret
```
