# Microsoft.Crm.Sandbox.SandboxAssemblyManager::TryRecoverDiskSpace

- ea: `0x3820`
- end: `0x3878`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::TryRecoverDiskSpace`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x36a0`

## callees

- `0x2570`
- `0x2820`
- `0x3820`

## string_xrefs

- `0x3821`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.1
0x3821  ldstr    aCache// "cache"
0x3826  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x382b  ldarg.2
0x382c  ldarg.1
0x382d  ldc.i4.1
0x382e  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxAssemblyCache::RecoverDiskSpace(bool fullScan)
0x3833  stind.i4
0x3834  ldarg.0
0x3835  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x383a  ldarg.1
0x383b  callvirt instance float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::get_CacheSize()
0x3840  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheDiskSpace(float64)
0x3845  ldarg.0
0x3846  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x384b  ldarg.2
0x384c  ldind.i4
0x384d  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheCount(int32)
0x3852  ldc.i4.1
0x3853  stloc.0
0x3854  leave.s  loc_3876
0x3856  stloc.1
0x3857  ldloc.1
0x3858  ldarg.0
0x3859  ldc.i4.s 0x21
0x385b  ldstr    aSandboxassembl_56// "SandboxAssemblyManager.TryRecoverDiskSp"...
0x3860  ldc.i4.1
0x3861  newarr   [mscorlib]System.Object
0x3866  dup
0x3867  ldc.i4.0
0x3868  ldloc.1
0x3869  stelem.ref
0x386a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x386f  ldarg.2
0x3870  ldc.i4.0
0x3871  stind.i4
0x3872  ldc.i4.0
0x3873  stloc.0
0x3874  leave.s  loc_3876
0x3876  ldloc.0
0x3877  ret
```
