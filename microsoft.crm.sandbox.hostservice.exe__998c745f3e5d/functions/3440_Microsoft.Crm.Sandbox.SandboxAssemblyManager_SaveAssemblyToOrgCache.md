# Microsoft.Crm.Sandbox.SandboxAssemblyManager::SaveAssemblyToOrgCache

- ea: `0x3440`
- end: `0x34a2`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::SaveAssemblyToOrgCache`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3390`

## callees

- `0x3440`
- `0x35b0`

## string_xrefs

- `0x344b`: `SandboxAssemblyManager.SaveAssemblyToOrgCache: Existing assembly`
- `0x346f`: `SandboxAssemblyManager.SaveAssemblyToOrgCache: New assembly`

## pseudocode

```c

```

## disassembly

```asm
0x3440  ldarg.2
0x3441  call     bool [mscorlib]System.IO.File::Exists(string)
0x3446  brfalse.s loc_346C
0x3448  ldarg.1
0x3449  ldc.i4.s 0x22
0x344b  ldstr    aSandboxassembl_44// "SandboxAssemblyManager.SaveAssemblyToOr"...
0x3450  ldc.i4.0
0x3451  newarr   [mscorlib]System.Object
0x3456  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x345b  ldarg.2
0x345c  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x3461  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3466  callvirt instance void [mscorlib]System.IO.FileSystemInfo::set_LastAccessTimeUtc(valuetype [mscorlib]System.DateTime)
0x346b  ret
0x346c  ldarg.1
0x346d  ldc.i4.s 0x22
0x346f  ldstr    aSandboxassembl_45// "SandboxAssemblyManager.SaveAssemblyToOr"...
0x3474  ldc.i4.0
0x3475  newarr   [mscorlib]System.Object
0x347a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x347f  ldarg.0
0x3480  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x3485  stloc.0
0x3486  ldnull
0x3487  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x348c  ldarg.2
0x348d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3492  ldloc.0
0x3493  call     void [mscorlib]System.IO.File::WriteAllBytes(string, unsigned int8[])
0x3498  ldarg.1
0x3499  ldloc.0
0x349a  ldlen
0x349b  conv.i4
0x349c  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::StartCheckDiskSpace(valuetype [mscorlib]System.Guid organizationId, int32 assemblySize)
0x34a1  ret
```
