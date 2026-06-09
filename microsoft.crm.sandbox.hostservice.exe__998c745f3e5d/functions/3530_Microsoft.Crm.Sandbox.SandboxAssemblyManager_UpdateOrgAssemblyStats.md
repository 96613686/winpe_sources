# Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateOrgAssemblyStats

- ea: `0x3530`
- end: `0x35a5`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateOrgAssemblyStats`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3320`

## callees

- `0x3530`

## string_xrefs

- `0x3533`: `SandboxAssemblyManager.UpdateOrgAssemblyStats: Existing assembly - assembly cache hit`
- `0x3589`: `SandboxAssemblyManager.UpdateOrgAssemblyStats: IOException: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldarg.0
0x3531  ldc.i4.s 0x22
0x3533  ldstr    aSandboxassembl_46// "SandboxAssemblyManager.UpdateOrgAssembl"...
0x3538  ldc.i4.0
0x3539  newarr   [mscorlib]System.Object
0x353e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3543  ldarg.0
0x3544  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x3549  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheHit()
0x354e  ldarg.1
0x354f  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x3554  stloc.0
0x3555  ldloc.0
0x3556  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastAccessTimeUtc()
0x355b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3560  stloc.1
0x3561  ldloca.s 1
0x3563  ldc.r8   -1.0
0x356c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x3571  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3576  brfalse.s loc_3583
0x3578  ldloc.0
0x3579  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x357e  callvirt instance void [mscorlib]System.IO.FileSystemInfo::set_LastAccessTimeUtc(valuetype [mscorlib]System.DateTime)
0x3583  leave.s  loc_35A4
0x3585  stloc.2
0x3586  ldarg.0
0x3587  ldc.i4.s 0x22
0x3589  ldstr    aSandboxassembl_47// "SandboxAssemblyManager.UpdateOrgAssembl"...
0x358e  ldc.i4.1
0x358f  newarr   [mscorlib]System.Object
0x3594  dup
0x3595  ldc.i4.0
0x3596  ldloc.2
0x3597  callvirt instance string [mscorlib]System.Exception::get_Message()
0x359c  stelem.ref
0x359d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35a2  leave.s  loc_35A4
0x35a4  ret
```
