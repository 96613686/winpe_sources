# Microsoft.Crm.Sandbox.SandboxAssemblyManager::CheckAssembly

- ea: `0x3320`
- end: `0x3386`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::CheckAssembly`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4670`

## callees

- `0x3320`
- `0x3390`
- `0x3530`

## string_xrefs

- `0x333e`: `{0}-{1}.dll`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldnull
0x3321  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x3326  ldarga.s 3
0x3328  ldstr    aB// "B"
0x332d  call     instance string [mscorlib]System.Guid::ToString(string)
0x3332  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3337  stloc.0
0x3338  ldloc.0
0x3339  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x333e  ldstr    a01Dll// "{0}-{1}.dll"
0x3343  ldc.i4.2
0x3344  newarr   [mscorlib]System.Object
0x3349  dup
0x334a  ldc.i4.0
0x334b  ldarga.s 0
0x334d  ldstr    aB// "B"
0x3352  call     instance string [mscorlib]System.Guid::ToString(string)
0x3357  stelem.ref
0x3358  dup
0x3359  ldc.i4.1
0x335a  ldarg.1
0x335b  box      [mscorlib]System.Int32
0x3360  stelem.ref
0x3361  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3366  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x336b  stloc.1
0x336c  ldloc.1
0x336d  call     bool [mscorlib]System.IO.File::Exists(string)
0x3372  brfalse.s loc_337C
0x3374  ldarg.3
0x3375  ldloc.1
0x3376  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateOrgAssemblyStats(valuetype [mscorlib]System.Guid organizationId, string assemblyPath)
0x337b  ret
0x337c  ldarg.2
0x337d  ldarg.3
0x337e  ldloc.0
0x337f  ldloc.1
0x3380  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgAssemblyCache(string pluginAssemblyContents, valuetype [mscorlib]System.Guid organizationId, string cachePath, string assemblyPath)
0x3385  ret
```
