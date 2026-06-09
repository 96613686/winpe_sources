# Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDActionCompleted

- ea: `0x1c80`
- end: `0x1d2c`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDActionCompleted`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3a0`

## callees

- `0xc40`
- `0xc60`
- `0xc80`
- `0xca0`
- `0x1c80`
- `0x1d30`

## string_xrefs

- `0x1cae`: `NOT AN ERROR PDActionCompleted: {0}, package: {1}, success: {2}, timed out: {3}, time taken in seconds: {4}, worker threads: {5}, io threads: {6}, active: {7}, queued: {8}, exception: {9}, log: {10}`

## pseudocode

```c

```

## disassembly

```asm
0x1c80  ldarg.2
0x1c81  callvirt instance string[] Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_Log()
0x1c86  brfalse.s loc_1C9A
0x1c88  call     string [mscorlib]System.Environment::get_NewLine()
0x1c8d  ldarg.2
0x1c8e  callvirt instance string[] Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_Log()
0x1c93  call     string [mscorlib]System.String::Join(string, string[])
0x1c98  br.s     loc_1C9B
0x1c9a  ldnull
0x1c9b  stloc.0
0x1c9c  ldloca.s 1
0x1c9e  ldloca.s 2
0x1ca0  call     void Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::GetThreadPoolStats([out] int32& activeWorkerThreads, [out] int32& activeIOThreads)
0x1ca5  ldnull
0x1ca6  ldarg.0
0x1ca7  ldc.i4.s 0x14
0x1ca9  ldc.i4   0x3E7
0x1cae  ldstr    aNotAnErrorPdac// "NOT AN ERROR PDActionCompleted: {0}, pa"...
0x1cb3  ldc.i4.s 0xB
0x1cb5  newarr   [mscorlib]System.Object
0x1cba  dup
0x1cbb  ldc.i4.0
0x1cbc  ldsfld   string Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::applicationVersion
0x1cc1  stelem.ref
0x1cc2  dup
0x1cc3  ldc.i4.1
0x1cc4  ldarg.1
0x1cc5  stelem.ref
0x1cc6  dup
0x1cc7  ldc.i4.2
0x1cc8  ldarg.2
0x1cc9  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_Successful()
0x1cce  box      [mscorlib]System.Boolean
0x1cd3  stelem.ref
0x1cd4  dup
0x1cd5  ldc.i4.3
0x1cd6  ldarg.2
0x1cd7  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_TimedOut()
0x1cdc  box      [mscorlib]System.Boolean
0x1ce1  stelem.ref
0x1ce2  dup
0x1ce3  ldc.i4.4
0x1ce4  ldarga.s 3
0x1ce6  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x1ceb  box      [mscorlib]System.Double
0x1cf0  stelem.ref
0x1cf1  dup
0x1cf2  ldc.i4.5
0x1cf3  ldloc.1
0x1cf4  box      [mscorlib]System.Int32
0x1cf9  stelem.ref
0x1cfa  dup
0x1cfb  ldc.i4.6
0x1cfc  ldloc.2
0x1cfd  box      [mscorlib]System.Int32
0x1d02  stelem.ref
0x1d03  dup
0x1d04  ldc.i4.7
0x1d05  ldarg.s  4
0x1d07  box      [mscorlib]System.Int32
0x1d0c  stelem.ref
0x1d0d  dup
0x1d0e  ldc.i4.8
0x1d0f  ldarg.s  5
0x1d11  box      [mscorlib]System.Int32
0x1d16  stelem.ref
0x1d17  dup
0x1d18  ldc.i4.s 9
0x1d1a  ldarg.2
0x1d1b  callvirt instance class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_Exception()
0x1d20  stelem.ref
0x1d21  dup
0x1d22  ldc.i4.s 0xA
0x1d24  ldloc.0
0x1d25  stelem.ref
0x1d26  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1d2b  ret
```
