# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetSolutionFileBuffer

- ea: `0x4d00`
- end: `0x4d87`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetSolutionFileBuffer`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4cb0`

## callees

- `0x4d00`

## string_xrefs

- `0x4d13`: `Actions_Org\Install`

## pseudocode

```c

```

## disassembly

```asm
0x4d00  ldc.i4.0
0x4d01  call     string[] [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetReleaseFilePaths(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x4d06  ldc.i4.0
0x4d07  ldelem.ref
0x4d08  ldsfld   string [mscorlib]System.String::Empty
0x4d0d  stloc.0
0x4d0e  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x4d13  ldstr    aActionsOrgInst// "Actions_Org\\Install"
0x4d18  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4d1d  ldstr    aSolutionsBusin// "Solutions\\BusinessProcesses.zip"
0x4d22  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4d27  stloc.0
0x4d28  ldloc.0
0x4d29  call     bool [mscorlib]System.IO.File::Exists(string)
0x4d2e  brfalse.s loc_4D82
0x4d30  ldloc.0
0x4d31  ldc.i4.3
0x4d32  ldc.i4.1
0x4d33  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x4d38  stloc.1
0x4d39  ldloc.1
0x4d3a  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x4d3f  conv.ovf.i
0x4d40  newarr   [mscorlib]System.Byte
0x4d45  stloc.2
0x4d46  ldloc.1
0x4d47  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x4d4c  conv.i4
0x4d4d  stloc.3
0x4d4e  ldc.i4.0
0x4d4f  stloc.s  4
0x4d51  br.s     loc_4D6F
0x4d53  ldloc.1
0x4d54  ldloc.2
0x4d55  ldloc.s  4
0x4d57  ldloc.3
0x4d58  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x4d5d  stloc.s  5
0x4d5f  ldloc.s  5
0x4d61  brfalse.s loc_4D73
0x4d63  ldloc.s  4
0x4d65  ldloc.s  5
0x4d67  add
0x4d68  stloc.s  4
0x4d6a  ldloc.3
0x4d6b  ldloc.s  5
0x4d6d  sub
0x4d6e  stloc.3
0x4d6f  ldloc.3
0x4d70  ldc.i4.0
0x4d71  bgt.s    loc_4D53
0x4d73  ldloc.2
0x4d74  stloc.s  6
0x4d76  leave.s  loc_4D84
0x4d78  ldloc.1
0x4d79  brfalse.s loc_4D81
0x4d7b  ldloc.1
0x4d7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d81  endfinally
0x4d82  ldnull
0x4d83  ret
0x4d84  ldloc.s  6
0x4d86  ret
```
